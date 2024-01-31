# Ansible Role to setup Jenkins


|   Authors        |  Created on   |  Version   | Last updated by | Last edited on |
| -----------------| --------------| -----------|---------------- | -------------- |
| Vidhi Yadav      |  31 Jan 2024   |     v1     | Vidhi Yadav     | 31 Jan 2024    |


## Table of Contents
+ [Introduction](#Introduction)
+ [Key Components](#key-points)
+ [Popular Tools](#popular-tools)
+ [Tool Comparison](#tool-comparison)
+ [Guide to Installation](#Installing-OWASP-Dependency-Check)
+ [Best Practices](#best-practices)
+ [Security Compliance](#security-compliance)
+ [Contact Information](#contact-information)
+ [References](#references)

# Introduction
This role is designed to automate the installation and configuration of Jenkins on target servers. Whether you're setting up Jenkins for continuous integration, continuous delivery, or other purposes, this role aims to simplify the process.

## Prerequisites

Before using this Ansible role to set up Jenkins, ensure that the following prerequisites are met:

1. **Ansible:**
   - Ansible must be installed on the control machine from which you plan to run the playbook. If Ansible is not installed, you can install it using this [link](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html)

2. **SSH Access to Target Servers:**
   - Ensure that you have SSH access to the target servers where Jenkins will be installed.

4. **Jenkins Repository Key URL:**
   - You will need the URL of the Jenkins repository key. Specify the URL when running the playbook by setting the `jenkins_repo_key_url` variable in the variables folder.

5. **Jenkins Repository URL:**
   - You will also need the URL of the Jenkins APT repository. Specify the URL when running the playbook by setting the `jenkins_repo_url` variable.

# Steps 
* Before going further check the link for Ansible Code:

**Step 1 - Dynamic Inventory Setup** 

```yaml
[defaults]

# some basic default values...

inventory      = aws_ec2.yml
host_key_checking = False
private_key_file = /home/ubuntu/vd.pem
remote_user = ubuntu

[inventory]
# enable inventory plugins, default: 'host_list', 'script', 'auto', 'yaml', 'ini', 'toml'
enable_plugins = aws_ec2, host_list, virtualbox, yaml, constructed, script, auto, ini, toml
```


