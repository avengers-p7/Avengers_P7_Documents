# Ansible Role to setup Jenkins (Debian and Redhat)


|   Authors        |  Created on   |  Version   | Last updated by | Last edited on |
| -----------------| --------------| -----------|---------------- | -------------- |
| Vidhi Yadav      |  31 Jan 2024   |     v1     | Vidhi Yadav     | 31 Jan 2024    |

***
## Table of Contents
+ [Introduction](#Introduction)
+ [Ansible and Jenkins](#Ansible-jenkins)
+ [Flow Diagram](#Flow-diagram)
+ [Pre-requisites](#pre-requisites)
+ [Setup Ansible Role](#steps)
+ [Output Verification](#output)
+ [Jenkins Setup](#post-installation-setup)
+ [Conclusion](#conclusion)
+ [Contact Information](#contact-information)
+ [References](#references)

***
# Introduction
This role is designed to automate the installation and configuration of Jenkins on target servers. Whether you're setting up Jenkins for continuous integration, continuous delivery, or other purposes, this role aims to simplify the process.

***
## Ansible and Jenkins

Here, we harness the efficiency of Ansible, an open-source automation tool streamlining configuration management and application deployment. In parallel, Jenkins excels in facilitating continuous integration and delivery, ensuring a seamless and automated pipeline for software development processes.

***
## Flow Diagram

* This diagram should help you visualize the sequence of tasks in your Ansible playbook for installing Jenkins.

<img width="1197" alt="Screenshot 2024-02-01 at 4 19 50 PM" src="https://github.com/avengers-p7/Documentation/assets/156056349/73aef5f2-f1ce-402f-8015-c44e7b14236b">

***
## Pre-requisites

Before using this Ansible role to set up Jenkins, ensure that the following prerequisites are met:

1. **Ansible:**
   - Ansible must be installed on the control machine from which you plan to run the playbook. If Ansible is not installed, you can install it using this [link](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html)

2. **SSH Access to Target Servers:**
   - Ensure that you have SSH access to the target servers where Jenkins will be installed.

***
# Steps 
* Before going further check the link for Ansible Role: https://github.com/vyadavP7/Jenkins-AnsibleRole

**Step 1: Dynamic Inventory Setup** 

```yaml
[defaults]

# some basic default values...

inventory      = aws_ec2.yml

[inventory]
# enable inventory plugins, default: 'host_list', 'script', 'auto', 'yaml', 'ini', 'toml'
enable_plugins = aws_ec2, host_list, virtualbox, yaml, constructed, script, auto, ini, toml

```

> [!NOTE]
>Ensure that for dynamic inventory you have the necessary AWS credentials configured in AWS CLI and attach an IAM role on the master node. 

**Step 2:  AWS EC2 Inventory**

```yaml
---
plugin: aws_ec2
regions:
  - eu-north-1

groups: 
  debian: "'debian' in tags.OS"
  redhat: "'redhat' in tags.OS"

group_vars:
  debian: group_vars/debian.yml
  redhat: group_vars/redhat.yml
```

1. `plugin: aws_ec2`: Specifies the use of the aws_ec2 plugin as the dynamic inventory source. This plugin is designed to fetch information about EC2 instances in AWS.
2. `regions: - eu-north-1`: Indicates the AWS region(s) from which the dynamic inventory should fetch information.
3. `debian: "'debian' in tags.OS"`: Creates an Ansible group named debian and redhat. This group includes EC2 instances where the tag named OS has a value of 'debian' and 'redhat'.

**Step 3: Create Ansible Role**
* Create a new Ansible role which should follow this directory structure:

<img width="714" alt="Screenshot 2024-02-19 at 8 45 45 PM" src="https://github.com/avengers-p7/Documentation/assets/156056349/0d6f54c9-6b3a-4ce9-b35f-900e7353aae5">


**Step 4: playbook.yml**
* This file is defining a set of tasks to be executed on hosts belonging to the debian group.

```yaml
---
- hosts: debian,redhat
  become: yes
  gather_facts: yes 
  roles:
    - jenkins      #includes role
```
**Step 5: Tasks**
1. `main.yml`: This main.yml file is acting as an orchestrator, importing tasks from the `install_debian.yml` and `install_redhat` files. This separation of tasks into different files is a good practice for better organization, especially when dealing with complex configurations or roles.

```yaml
---
# importing task files
- name: Jenkins Installation on Debian
  import_tasks: install_debian.yml
  tags:
    - debian

- name: Jenkins Installation on Redhat
  import_tasks: install_redhat.yml
  tags:
    - redhat
```

2. `Default` variables: This role comes with default values for the Jenkins repository URL and key URL. You can find these defaults in the `defaults/main.yml` file within the role directory.

```yaml
---
# defaults file for debian and redhat

# Debian
java: "default-jre"
debian_repo_url:  deb https://pkg.jenkins.io/debian-stable binary/ 
debian_repo_key_url:  https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key 

# Redhat
java_yum_package: java-17-openjdk
redhat_repo_key_url: "https://pkg.jenkins.io/redhat-stable/jenkins.io.key"
redhat_repo_url: "https://pkg.jenkins.io/redhat-stable/jenkins.repo"
```

> [!NOTE]
> To customize the Jenkins version based on your specific requirements, you can override these default values in your playbook. This is particularly useful when you want to install a different version of Jenkins.


3. `install_debian.yml`: This file is included in the jenkins/tasks/main.yml file

```yaml
---
- name: Update APT cache
  apt:
    update_cache: yes
  when: ansible_os_family == 'Debian'
  tags:
    - debian

# Installs jdk if not installed already
- name: Ensure Java is installed
  apt:
    name: "{{ java }}"
    state: present
    update_cache: true
  when: ansible_os_family == 'Debian'
  tags:
    - debian

- name: Add Jenkins apt key in system.
  apt_key:
    url: "{{ debian_repo_key_url }}"
    state: present
  when: ansible_os_family == 'Debian'
  tags:
    - debian

- name: Add Jenkins apt repository.
  apt_repository:
    repo: "{{ debian_repo_url }}"
    state: present
    update_cache: yes
  when: ansible_os_family == 'Debian'
  tags:
    - debian

- name: Install jenkins 
  apt:
    name: jenkins
    state: present
    update_cache: yes
  when: ansible_os_family == 'Debian'
  tags:
    - debian

- name: Start service 
  service:
    name: jenkins 
    state: started 
    enabled: yes
  when: ansible_os_family == 'Debian'
  tags:
    - debian


- name: Check Jenkins service status
  systemd:
    name: jenkins
    state: started
  ignore_errors: yes
  register: jenkins_service_status
  when: ansible_os_family == 'Debian'
  tags:
    - debian

- name: Display Jenkins service status
  debug:
    var: jenkins_service_status
  when: ansible_os_family == 'Debian'
  tags:
    - debian
```

4. `install_redhat.yml`: This file is included in the jenkins/tasks/main.yml file. It contains tasks related to Jenkins installation on redhat servers.
```yaml
---
- name: Ensure Java is installed
  yum:
    name: "{{ java_yum_package }}"
    state: present
    update_cache: true
  when: ansible_os_family == 'RedHat'
  tags:
    - redhat

- name: Add Jenkins key in system
  ansible.builtin.rpm_key:
    state: present
    key:  "{{ redhat_repo_key_url }}"
  when: ansible_os_family == 'RedHat'
  tags:
    - redhat

- name: Getting Jenkins.repo file...
  ansible.builtin.get_url:
    url: "{{ redhat_repo_url }}"
    dest: /etc/yum.repos.d/jenkins.repo
  when: ansible_os_family == 'RedHat'
  tags:
    - redhat

- name: Install jenkins 
  yum:
    name: jenkins
    state: present
    update_cache: true
  when: ansible_os_family == 'RedHat'
  tags:
    - redhat

- name: Start service in redhat
  service:
    name: jenkins 
    state: started 
    enabled: yes
  when: ansible_os_family == 'RedHat'
  tags:
    - redhat
  

- name: Check Jenkins service status (redhat)
  systemd:
    name: jenkins
    state: started
  ignore_errors: yes
  register: jenkins_service_status
  when: ansible_os_family == 'RedHat'
  tags:
    - redhat

- name: Display Jenkins service status (redhat)
  debug:
    var: jenkins_service_status
  when: ansible_os_family == 'RedHat'
  tags:
    - redhat
```

**Step 6: Playbook Execution**

* To set up Jenkins on your target servers, you will execute the Ansible playbook using the following command:

```bash
ansible-playbook playbook.yml --tags debian,redhat
```

> Additional Options
> Tags can be provided based on the user's preference
> 
> --limit: You can use this option to specify a subset of hosts from the inventory on which the playbook should be executed.
> 
> -e or --extra-vars: You can pass extra variables to the playbook using this option.


<img width="925" alt="Screenshot 2024-02-01 at 2 07 56 AM" src="https://github.com/avengers-p7/Documentation/assets/156056349/38f31390-31ff-4591-a34d-8a23d96eaf49">

<img width="947" alt="Screenshot 2024-02-01 at 2 07 24 AM" src="https://github.com/avengers-p7/Documentation/assets/156056349/9e7fd3a7-5ac9-476c-8b55-35f969e0121b">

***
## Output
1.  **Host-level output**: Output for each host would indicate whether the playbook execution was successful or not.

<img width="1352" alt="Screenshot 2024-02-01 at 2 41 57 AM" src="https://github.com/avengers-p7/Documentation/assets/156056349/d69954c0-6182-4c73-883d-ea7e21fe323d">

2. **Colorized Output**: Ansible uses colorized output to make it easier to identify successful, changed, or failed tasks. Successful tasks are often displayed in green, changed tasks in yellow, and failed tasks in red.

<img width="947" alt="Screenshot 2024-02-01 at 2 07 24 AM" src="https://github.com/avengers-p7/Documentation/assets/156056349/17399616-2a58-406d-affd-ca529e5ed158">

3. **Verify Tags**: Verify that the Jenkins installation is on the instance with the mentioned tags.

<img width="764" alt="Screenshot 2024-02-01 at 9 26 33 AM" src="https://github.com/avengers-p7/Documentation/assets/156056349/aa56992e-6702-40f8-a80c-39c49f53856a">

***
## Post-Installation Setup
* Open your web browser and navigate to `http://your-jenkins-server:8080`.

<img width="1365" alt="Screenshot 2024-02-03 at 5 45 17 PM" src="https://github.com/avengers-p7/Documentation/assets/156056349/37be3eed-33ed-48fb-b2e3-d0a2977b0924">

> [!IMPORTANT]
>
>  Ensure that port `8080` is open on your Ansible host.

* Retrieve the initial administrator password from the Jenkins server.

<img width="1122" alt="Screenshot 2024-02-03 at 5 49 48 PM" src="https://github.com/avengers-p7/Documentation/assets/156056349/1c22aa91-343c-4761-9464-f9955ed7d1ad">

* Customize jenkins based on your requirements and you're all set!

<img width="809" alt="Screenshot 2024-02-03 at 5 53 08 PM" src="https://github.com/avengers-p7/Documentation/assets/156056349/e542a049-956c-4085-962c-93dde46440d8">


***
## Conclusion 

* This guide illustrates the process of deploying Jenkins in a development environment through Ansible. By adhering to these instructions, you can effectively provision and set up Jenkins within your AWS infrastructure.

***
## Contact Information

|Vidhi Yadav                     | vidhi.yadhav.snaatak@mygurukulam.co                                                                                      
|---------------------------------|------------------------------------------------------------|

***
## References

| Title                                      | URL                                           |
|--------------------------------------------|-----------------------------------------------|
| Ansible documentation           | https://docs.ansible.com/ansible/latest/index.html    |
| Jenkins Installation    | https://www.jenkins.io/doc/book/installing/linux/  |
| Dyanmic Inventory               | https://www.youtube.com/watch?v=junPdh2yvbU&t=454s | 







