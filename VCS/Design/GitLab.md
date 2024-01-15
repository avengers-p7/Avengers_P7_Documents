| Author | Created on | Last Updated | Document Version |
| ------ | ---------- | ------------ | ---------------- |
| Shantanu | 10-01-2024 | 15-01-2024   |         v1     |
***
![image](https://github.com/avengers-p7/Documentation/assets/156056364/487d819d-c1e2-4dd8-a463-c2a980d9c930)

# Introduction
GitLab is a web-based Git repository that provides free open and private repositories, issue-following capabilities, and wikis. It is a complete DevOps platform that enables professionals to perform all the tasks in a project—from project planning and source code management to monitoring and security. Additionally, it allows teams to collaborate and build better software. 

***

# Purpose
* Collaborative Development

* Continuous Integration/Continuous Deployment (CI/CD)

* Agile Project Management

* Security Scanning and Compliance

* Container Orchestration

* Code Review and Quality Assurance

* Scalable Infrastructure as Code (IaC)

* Multi-Branch Development

* Integrated Monitoring and Performance Analytics


***

# Key Features
* Integrated DevOps Platform

* Built-In CI/CD

* Scalable Version Control

* Kubernetes Integration

* Built-In Container Registry

* Code Review and Collaboration

* Comprehensive Project Management

* Security Features

* Infrastructure as Code (IaC)

* Monitoring and Performance Analytics


***
# Getting Started

## Overview

| License Type |                Description                 |  Open Source   |
| ------------ | ------------------------------------------ | -------------- |
| GitLab CE    | Distributed under an open-source license   |     Yes        |
| GitLab EE    | Requires subscription or license purchase  |     No         |

## System Requirements

| Requirement  |                Minimum Recommendation      |
| ------------ | ------------------------------------------ |
|    CPU       |                    4 Cores                 |    
|    RAM       | 4GB RAM minimum, 8GB or more recommended   |     
|    ROM       |          25GB of free disk space           |
|    OS        |       Compatible Linux distribution        |

## Important Ports

|     Ports    |                Description                 |
| ------------ | ------------------------------------------ |
|     22       | Port 22 is used to establish an SSH connection to an EC2 instance and access a shell.         |                      
|    443       | It is a standard port for secure communication over the internet between client and server.   | 

***

# Dependencies

## Run Time Dependency

|     Dependency    |  Version |
| ------------ | -------------|
|     Ruby       |  2.7 or later      |                      
|    Git       | Latest stable version  | 
| PostgresSQL | Version supported by Gitlab that is being installed |
| Redis | Latest stable version |
 
***

# How to Setup/Install Gitlab

## Step-by-Step Installation Instruction

**Step 1 — Installing the Dependencies**

`sudo apt update`

`sudo apt install ca-certificates curl openssh-server postfix tzdata perl`

**Step 2 — Installing GitLab**

`cd /tmp`

`curl -LO https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh`

`less /tmp/script.deb.sh`

`sudo bash /tmp/script.deb.sh`

`sudo apt install gitlab-ce`

**Step 3 — Adjusting the Firewall Rules**

`sudo ufw status`

`sudo ufw allow http`
`sudo ufw allow https`
`sudo ufw allow OpenSSH`

`sudo ufw status`

## Configuration 

**Step 4 — Editing the GitLab Configuration File**

`sudo nano /etc/gitlab/gitlab.rb`

Search for the external_url configuration line. Update it to match your domain and make sure to change http to https to automatically redirect users to the site protected by the Let’s Encrypt certificate.


Next, find the `letsencrypt['contact_emails']` setting. If you’re using `nano`, you can enable a search prompt by pressing `CTRL+W`. Write `letsencrypt['contact_emails']` into the prompt, then press `ENTER`. This setting defines a list of email addresses that the Let’s Encrypt project can use to contact you if there are problems with your domain. It’s recommended to uncomment and fill this out to inform yourself of any issues that may occur.

`letsencrypt['contact_emails'] = ['sammy@example.com']`

Once you’re done making changes, save and close the file. If you’re using nano, you can do this by pressing `CTRL+X`, then `Y`, then `ENTER`.

`sudo gitlab-ctl reconfigure`


**Step 5 — Performing Initial Configuration Through the Web Interface**

Logging In for the First Time

GitLab generates an initial secure password for you. It is stored in a folder that you can access as an administrative sudo user:
`sudo nano /etc/gitlab/initial_root_password`

## Contact Information
| Name | Email Address |
| -----| --------------|
| Shantanu | shantanu.chauhan.snaatak@mygurukulam.co |

## References

| Source | Description |
| ------ | ----------- |
| https://about.gitlab.com/features/ | GitLab Features |
| https://www.digitalocean.com/community/tutorials/how-to-install-and-configure-gitlab-on-ubuntu-20-04 | Prerequisites, Installation & Configuration |

