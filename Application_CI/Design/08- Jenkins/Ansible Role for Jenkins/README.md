# Ansible Role to setup Jenkins


|   Authors        |  Created on   |  Version   | Last updated by | Last edited on |
| -----------------| --------------| -----------|---------------- | -------------- |
| Vidhi Yadav      |  31 Jan 2024   |     v1     | Vidhi Yadav     | 31 Jan 2024    |

***
## Table of Contents
+ [Introduction](#Introduction)
+ [Pre-requisites](#pre-requisites)
+ [Setup Ansible Role](#steps)
+ [Tool Comparison](#tool-comparison)
+ [Guide to Installation](#Installing-OWASP-Dependency-Check)
+ [Best Practices](#best-practices)
+ [Security Compliance](#security-compliance)
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

4. **Jenkins Repository Key URL:**
   - You will need the URL of the Jenkins repository key. Specify the URL when running the playbook by setting the `jenkins_repo_key_url` variable in the variables folder.

5. **Jenkins Repository URL:**
   - You will also need the URL of the Jenkins APT repository. Specify the URL when running the playbook by setting the `jenkins_repo_url` variable.

***
# Steps 
* Before going further check the link for Ansible Code: 

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

3. `default` variables: This role comes with default values for the Jenkins repository URL and key URL. You can find these defaults in the `defaults/main.yml` file within the role directory.

```yaml
---
# defaults file for jenkins
jenkins_repo_url:  deb https://pkg.jenkins.io/debian-stable binary/ 
jenkins_repo_key_url:  https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key 
```

> [!NOTE]
> To customize the Jenkins version based on your specific requirements, you can override these default values in your playbook. This is particularly useful when you want to install a different version of Jenkins.


