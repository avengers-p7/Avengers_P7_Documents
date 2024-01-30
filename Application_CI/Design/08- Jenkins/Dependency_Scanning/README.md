# Dependency Scanning 

|   Authors        |  Created on   |  Version   | Last updated by | Last edited on |
| -----------------| --------------| -----------|---------------- | -------------- |
| Vidhi Yadav      | 25 Jan 2024   |     v1     | Vidhi Yadav     | 29 Jan 2024    |

***
## Table of Contents 
+ [Introduction](#Introduction)
+ [Key Components](#key-points)
+ [Popular Tools](#popular-tools)
+ [Guide to Installation](#Getting-started)
+ [Jenkins Job Configuration](#jenkins-job-setup)
+ [Pre requisites](#pre-requisites)
+ [Dependencies](#dependencies)
+ [API Setup](#api-setup)
+ [Security](#best-practices-for-api-security)
+ [Troubleshoot](#troubleshoot)
+ [Contact Information](#contact-information)
+ [References](#references)

***
## Introduction

* Dependency scanning is a process used in software development to identify and analyze the external dependencies or third-party components that a project relies on. These dependencies can include libraries, frameworks, modules, packages, or other code modules that are utilized to build and run the software. 

* The scanning process is typically automated and integrated into the development workflow, often as part of continuous integration or continuous delivery (CI/CD) pipelines. It serves as a crucial post-build process examines the project's dependencies to identify any known vulnerabilities, outdated versions, or security issues.

*** 
## Key Points

* **Automated Security Checks:** - Dependency check facilitates the automated detection of vulnerabilities within project dependencies, seamlessly integrating this crucial security check into CI/CD pipelines.
* **Efficiency and Accuracy:** - It reduces the need for manual effort, significantly improving accuracy and efficiency compared to traditional manual checks.
* **Awareness and Reporting** - Developers gain awareness of potential vulnerabilities through reports at an early stage, providing insights into the identified issues and their respective severity levels.

***
## Popular Tools

Explore a variety of widely used tools for scanning dependencies and enhancing the security of your projects. These tools can be integrated into Jenkins or used independently, providing diverse options for identifying and addressing vulnerabilities:

1. [OWASP Dependency-Check](https://jeremylong.github.io/DependencyCheck/): OWASP Dependency-Check is a mature and widely adopted tool that identifies project dependencies and checks if there are any known, publicly disclosed, vulnerabilities.
2. [Synk](https://snyk.io/): Snyk is a comprehensive security platform that helps developers find and fix vulnerabilities in open-source libraries. It provides insights into dependencies, container images, and infrastructure as code.
3. [Retire.js](https://retirejs.github.io/retire.js/): Retire.js is a tool for detecting vulnerable JavaScript libraries. It can be used as a command-line tool or integrated into various build tools.
4. [Bundler Audit](https://github.com/rubysec/bundler-audit#readme): Bundler Audit is a tool for checking RubyGem dependencies for known security vulnerabilities. It integrates with Ruby projects using Bundler and can be utilized in Jenkins for secure Ruby application development.


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

* You may use `Dependency-Check Publisher`, configured as a post-build action, independently processes the 'dependency-check-report.xml' file. It generates metrics, trends, and findings, with the ability to set configurable thresholds. This includes the option to mark the build as failed or in a warning state based on specified criteria.

<img width="1358" alt="Screenshot 2024-01-31 at 12 32 38 AM" src="https://github.com/avengers-p7/Documentation/assets/156056349/7b65ba1c-f4b5-4097-95a0-2584f33702ad">


### 2. Verification

* Initiate the job in Jenkins that includes the OWASP Dependency-Check configuration. Monitor the console output and review results

<img width="1317" alt="Screenshot 2024-01-30 at 3 06 06 PM" src="https://github.com/avengers-p7/Documentation/assets/156056349/3c14c164-faa7-4b28-b43d-3d4c063fb156">

* Navigate to the job's build artifacts or workspace. Locate the generated Dependency-Check reports. They are typically available in multiple formats (JSON, HTML, XML). 

<img width="1128" alt="Screenshot 2024-01-31 at 12 45 22 AM" src="https://github.com/avengers-p7/Documentation/assets/156056349/d5a23677-4118-4c4e-b03d-2bfd8894e00f">

* Open the reports in your preferred format and verify the content. Ensure that vulnerabilities are correctly identified, and severity levels align with expectations. If you configured multiple report formats , explore each format to understand the data presentation.

<img width="870" alt="Screenshot 2024-01-31 at 12 49 25 AM" src="https://github.com/avengers-p7/Documentation/assets/156056349/ae18d45c-af46-43ec-ab00-e2a9d28a058b">

<img width="1073" alt="Screenshot 2024-01-31 at 12 50 53 AM" src="https://github.com/avengers-p7/Documentation/assets/156056349/ee6596ef-bc8a-428a-bdf1-7957dd2b90ce">



