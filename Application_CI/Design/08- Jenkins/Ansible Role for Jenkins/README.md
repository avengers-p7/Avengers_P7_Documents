# Ansible Role to setup Jenkins


|   Authors        |  Created on   |  Version   | Last updated by | Last edited on |
| -----------------| --------------| -----------|---------------- | -------------- |
| Vidhi Yadav      |  31 Jan 2024   |     v1     | Vidhi Yadav     | 31 Jan 2024    |

***
## Table of Contents
+ [Introduction](#Introduction)
+ [Pre-requisites](#pre-requisites)
+ [Setup Ansible Role](#steps)
+ [Output Verification](#output)
+ [Conclusion](#conclusion)
+ [Contact Information](#contact-information)
+ [References](#references)

***
# Introduction
This role is designed to automate the installation and configuration of Jenkins on target servers. Whether you're setting up Jenkins for continuous integration, continuous delivery, or other purposes, this role aims to simplify the process.

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


# Use AWS EC2 dynamic inventory for managing hosts
inventory      = aws_ec2.yml

# Disable SSH host key checking for convenience.
host_key_checking = False

# Specify the path to the private key file for SSH connections.
private_key_file = /home/ubuntu/vd.pem

Sets the remote user for SSH connections to 'ubuntu'
remote_user = ubuntu

[inventory]
# enable inventory plugins, default: 'host_list', 'script', 'auto', 'yaml', 'ini', 'toml'
enable_plugins = aws_ec2, host_list, virtualbox, yaml, constructed, script, auto, ini, toml
```

> [!NOTE]
>Ensure that the dynamic inventory script is properly configured with the necessary AWS credentials and filters to fetch the desired hosts.

**Step 2:  AWS EC2 Inventory**

```yaml
---
plugin: aws_ec2
regions:
  - eu-north-1

groups: 
  ubuntu: "'ubuntu' in tags.OS"
```

1. `plugin: aws_ec2`: Specifies the use of the aws_ec2 plugin as the dynamic inventory source. This plugin is designed to fetch information about EC2 instances in AWS.
2. `regions: - eu-north-1`: Indicates the AWS region(s) from which the dynamic inventory should fetch information. In this case, it's set to the eu-north-1 region.
3. `groups`: Defines Ansible groups based on certain criteria. Groups are a way to organize and categorize hosts in the inventory.
4. `ubuntu: "'ubuntu' in tags.OS"`: Creates an Ansible group named ubuntu. This group includes EC2 instances where the tag named OS has a value of 'ubuntu'.

**Step 3: playbook.yml**
* This file is defining a set of tasks to be executed on hosts belonging to the ubuntu group.

```yaml
---
- hosts: ubuntu
  become: yes
  gather_facts: yes 
  roles:
    - jenkins      #includes role
```
**Step 4: Tasks**
1. `main.yml`: This main.yml file is acting as an orchestrator, importing tasks from the `install_jenkins.yml` file. This separation of tasks into different files is a good practice for better organization, especially when dealing with complex configurations or roles.

```yaml
---
# importing task files
- name: Include file to install softwares
  import_tasks: install_jenkins.yml
```

2. `install_jenkins.yml`: Ansible task folder for setting up Jenkins. It is split into several tasks. Let's break down each part.

```yaml
---
# Update APT cache
- name: Update APT cache
  apt:
    update_cache: yes

# Installs jdk if not installed already
- name: Ensure jdk is installed
  apt:
    name: default-jre
    state: present

# Adds the Jenkins repository's GPG key to the APT keyring
- name: Add Jenkins apt key in system.
  apt_key:
    url: "{{ jenkins_repo_key_url }}"
    state: present

# Add Jenkins apt repository
- name: Add Jenkins apt repository.
  apt_repository:
    repo: "{{ jenkins_repo_url }}"
    state: present
    update_cache: yes

# Install Jenkins
- name: Install jenkins 
  apt:
    name: jenkins
    state: present 

# Start Jenkins service
- name: Start service 
  service:
    name: jenkins 
    state: started 
    enabled: yes 

# Check Jenkins service status
- name: Check Jenkins service status
  systemd:
    name: jenkins
    state: started
  ignore_errors: yes
  register: jenkins_service_status

# Display Jenkins service status
- name: Display Jenkins service status
  debug:
    var: jenkins_service_status
```

**Explanation:**

* `Update APT cache`: This task updates the local package cache on the target system. It ensures that the system has the latest information about available.

* `Ensure JDK is installed`: This task ensures that the default Java Runtime Environment (JRE) is installed on the target system. It installs the package default-jre if it's not already installed.

* `Add Jenkins apt key to the system`: Adds the Jenkins repository's GPG key to the APT keyring on the target system. `The jenkins_repo_key_url` variable should contain the URL of the Jenkins repository's GPG key.

* `Add Jenkins apt repository`: Adds the Jenkins APT repository to the system's list of package sources. The jenkins_repo_url variable should contain the URL of the Jenkins APT repository. `The update_cache: yes` option ensures that the APT cache is updated after adding the repository.

* `Install Jenkins`: Installs the Jenkins package on the target system.

* `Start Jenkins service`: This task starts the Jenkins service and ensures that it is enabled to start on boot.

* `Check Jenkins service status` : Checks the status of the Jenkins service. The `ignore_errors: yes` option allows the playbook to continue even if there is an error (e.g. if the service is not found). The result is registered in the jenkins_service_status variable.

---
* `Display Jenkins service status` : This task simply displays the status of the Jenkins service. It can be helpful for debugging and understanding the result of the previous task.


3. `Default` variables: This role comes with default values for the Jenkins repository URL and key URL. You can find these defaults in the `defaults/main.yml` file within the role directory.

```yaml
---
# defaults file for jenkins
jenkins_repo_url:  deb https://pkg.jenkins.io/debian-stable binary/ 
jenkins_repo_key_url:  https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key 
```

> [!NOTE]
> To customize the Jenkins version based on your specific requirements, you can override these default values in your playbook. This is particularly useful when you want to install a different version of Jenkins.

**Step 4: Playbook Execution**

* To set up Jenkins on your target servers, you will execute the Ansible playbook using the following command:

```bash
ansible-playbook -i aws_ec2.yml playbook.yml
```

1. `ansible-playbook`: To run Ansible playbook

2. `-i aws_ec2.yml` : The -i option specifies the inventory file. In this case, it points to the aws_ec2.yml file, which contains information about your AWS EC2 instances.

3. `playbook.yml`: This is the main playbook file containing the instructions for setting up Jenkins. You can customize this playbook according to your requirements.

> Additional Option
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

<img width="734" alt="Screenshot 2024-02-01 at 2 19 37 AM" src="https://github.com/avengers-p7/Documentation/assets/156056349/8aeacd73-d81f-474e-b81a-63d80ee03d3d">


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







