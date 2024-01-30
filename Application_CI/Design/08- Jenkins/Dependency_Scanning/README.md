# Dependency Scanning 

|   Authors        |  Created on   |  Version   | Last updated by | Last edited on |
| -----------------| --------------| -----------|---------------- | -------------- |
| Vidhi Yadav      | 25 Jan 2024   |     v1     | Vidhi Yadav     | 29 Jan 2024    |

***
## Table of Contents 
+ [Introduction](#Introduction)
+ [Guide to Installation](#Getting-started)
+ [Architecture](#architecture)
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

The scanning process is typically automated and integrated into the development workflow, often as part of continuous integration or continuous delivery (CI/CD) pipelines. It serves as a crucial pre-build process examines the project's dependencies to identify any known vulnerabilities, outdated versions, or security issues.

*** 
## Getting Started

### 1. Pre-requisite

**Internet Access to retreive NVD Data**

* The NVD is a comprehensive source of vulnerability information. Dependency-Check can use this data to identify known vulnerabilities in your project's dependencies. It can be configured to fetch data from the NVD's Common Vulnerabilities and Exposures (CVE) database during the analysis process. This helps ensure that the tool has up-to-date information about known vulnerabilities. 

* If your environment does not have internet access or if there are restrictions on accessing external resources, Dependency-Check may still function, but it won't be able to fetch the latest vulnerability data from the NVD.

### 2. Installation

* OWASP Dependency-Check is a standalone tool, and it doesn't have additional prerequisites for its core functionality. You can download the Dependency-Check tool plugin in jenkins without requiring any specific plugins or additional installations.

* In your Jenkins dashboard, navigate to `Manage Jenkins` -> `Manage Plugins` Search for `OWASP Dependency-Check` in the available plugins and install it.

<img width="1334" alt="Screenshot 2024-01-30 at 1 49 04 PM" src="https://github.com/avengers-p7/Documentation/assets/156056349/cb44d7cc-d7a5-4699-a061-78e1cf24303f">

### 3. Configuration

To set up the configuration, navigate to `tools` in `Manage Jenkins` and select `Dependency-Check Installations`. Within this section, opt for the option to install from GitHub.com. Next, pick the desired version, preferably the latest one available.

<img width="1317" alt="Screenshot 2024-01-30 at 2 00 59 PM" src="https://github.com/avengers-p7/Documentation/assets/156056349/17500595-eb07-4bdf-ab6d-eb4c8a605083">


