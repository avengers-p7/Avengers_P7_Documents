# Dependency Scanning 

|   Authors        |  Created on   |  Version   | Last updated by | Last edited on |
| -----------------| --------------| -----------|---------------- | -------------- |
| Vidhi Yadav      | 25 Jan 2024   |     v1     | Vidhi Yadav     | 29 Jan 2024    |

***
## Table of Contents 
+ [Introduction](#Introduction)
+ [Guide to Installation](#Getting-started)
+ [Jenkins Job Configuration](#jenkins-job-setup)
+ [Pre requisites](#pre-requisites)
+ [System Requirements](#system-requirements)
+ [Dependencies](#dependencies)
+ [API Setup](#api-setup)
+ [Security](#best-practices-for-api-security)
+ [Troubleshoot](#troubleshoot)
+ [Contact Information](#contact-information)
+ [References](#references)

***
## Introduction
Dependency scanning is a process used in software development to identify and analyze the external dependencies or third-party components that a project relies on. These dependencies can include libraries, frameworks, modules, packages, or other code modules that are utilized to build and run the software. 

The scanning process is typically automated and integrated into the development workflow, often as part of continuous integration or continuous delivery (CI/CD) pipelines. It serves as a crucial post-build process examines the project's dependencies to identify any known vulnerabilities, outdated versions, or security issues.

*** 
## Getting Started

### 1. Pre-requisite

**Internet Access to retreive NVD Data**

* The NVD is a comprehensive source of vulnerability information. Dependency-Check can use this data to identify known vulnerabilities in your project's dependencies. It can be configured to fetch data from the NVD's Common Vulnerabilities and Exposures (CVE) database during the analysis process. This helps ensure that the tool has up-to-date information about known vulnerabilities. 

* If your environment does not have internet access or if there are restrictions on accessing external resources, Dependency-Check may still function, but it won't be able to fetch the latest vulnerability data from the NVD.

### 2. Installation

* OWASP Dependency-Check is a standalone tool, and it doesn't have additional prerequisites for its core functionality. You can download the Dependency-Check tool plugin in jenkins without requiring any specific plugins or additional installations.

* In your Jenkins dashboard, navigate to `Manage Jenkins` -> `Manage Plugins` Search for `OWASP Dependency-Check` in the available plugins and install it.

<img width="1334" alt="Screenshot 2024-01-30 at 1 49 04 PM" src="https://github.com/avengers-p7/Documentation/assets/156056349/7cee9449-7b7c-40e7-9bc1-08f20fc041f9">


### 3. Configuration

To set up the configuration, navigate to `tools` in `Manage Jenkins` and select `Dependency-Check Installations`. Within this section, opt for the option to install from GitHub.com. Next, pick the desired version, preferably the latest one available.

<img width="1317" alt="Screenshot 2024-01-30 at 2 00 59 PM" src="https://github.com/avengers-p7/Documentation/assets/156056349/f2936822-ff27-4e3c-b1cb-fede4d066d65">

***
## Jenkins Job Setup

### 1. Configure Job

* Create a `Jenkins job` (freestyle/pipeline). Ensure that you have configured the source code management section with your GitHub repository details.

<img width="1556" alt="Screenshot 2024-01-30 at 9 43 14 PM" src="https://github.com/avengers-p7/Documentation/assets/156056349/04a22c3f-0957-4513-bdeb-895b992a8591">

* Add the `Invoke OWASP Dependency-Check` build step to your job configuration. This step is responsible for running the OWASP Dependency-Check analysis on your project.

> Note: You can use dependency check arguments based on your requirements. These arguments allow you to customize the behavior of the tool according to your project's needs. You might use these arguments to control aspects such as output format, suppression of vulnerabilities, updating data feeds, etc. You can find detailed information by visiting the following link: [Dependency-Check Command-Line Arguments](https://jeremylong.github.io/DependencyCheck/dependency-check-cli/arguments.html)."

<img width="1407" alt="Screenshot 2024-01-31 at 12 15 51 AM" src="https://github.com/avengers-p7/Documentation/assets/156056349/ef2fe711-3add-4462-bade-d7fc4d3cfe40">

* 

