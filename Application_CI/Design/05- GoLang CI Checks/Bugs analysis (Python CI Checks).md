# Dependency scanning POC (GoLang CI Checks)

![image](https://github.com/avengers-p7/Documentation/assets/156056570/0e6c6f87-893b-4103-8229-52d57d14e73c)

| Author                 | Created On | Last Updated | Document Version | Last Updated By |
| ---------------------- | ---------- | ------------ | ---------------- | --------------- |
| **Samir Kesare** | 04-02-2024 | 04-02-2024   | v1               |  **Samir**        |
***
## Table of Contents

+ [OWASP ZAPIntroduction](#OWASP-ZAP-Introduction)
+ [Key Features](#Key-Features)
+ [Pre-requisite](#Pre-requisite)
+ [OWASP ZAP Installation](#OWASP-ZAP-Installation)
+ [Proof of Concept (POC)](#Proof-of-Concept-(POC))
+ [HTML Report](#HTML-Report)
+ [Analyzing the report ](#Analyzing-the-report )
+ [Contact Information](#Contact-Information)
+ [References](#References)
***
## Nancy Introduction
Nancy, as you may know by reputation, is a detective. She uses Sonatype’s OSS Index to check for vulnerabilities in your Go dependencies.

Named after the fictional detective, Nancy works by scanning your Gopkg.lock file (if you use dep) or go.sum (if you use Go modules). From these files, Nancy consults the OSS Index for known vulnerabilities in your dependencies, and if any are found, an error message is reported.

***
## Key Features

| Feature                | Description                                                                                          |
|------------------------|------------------------------------------------------------------------------------------------------|
| Vulnerability Scanning | Conducts comprehensive vulnerability scanning of dependencies to identify known security issues.     |
| Dependency Analysis    | Analyzes dependencies in software projects, providing insights into their origin, licenses, and risks.|
| Component Inventory    | Maintains a detailed inventory of components used in applications, facilitating tracking and management.|
| Continuous Monitoring  | Offers continuous monitoring of dependencies, detecting and alerting on newly discovered vulnerabilities. |
| Policy Enforcement     | Enforces policies to ensure compliance with organizational standards and best practices for dependencies. |
| Remediation Guidance   | Provides actionable guidance on how to remediate identified vulnerabilities and manage dependency risks. |
| Integration            | Integrates seamlessly with popular CI/CD pipelines and development tools, enabling automated security checks. |
| Custom Policies        | Allows the creation of custom policies tailored to specific organizational requirements and security standards. |
| Reporting              | Generates comprehensive reports highlighting vulnerabilities, dependencies, and policy compliance status. |
| Open Source            | Built as an open-source tool, fostering community contribution, transparency, and collaboration. |
| Scalability            | Scales effectively to support projects of various sizes, from small applications to large enterprise systems. |
| Extensibility          | Offers extensibility through APIs and plugin architecture, enabling integration with additional tools and services. |

***
## Nancy Installation 
As Nancy is a tool written in Go, and Go compiles to a static binary, installation is quite simple. In most cases, it’s a simple matter of downloading the pre-compiled binary to your local system.

The following commands will download version 0.1.17 into /usr/local/bin on your local system, then make it executable:
```shell
sudo curl -L -o /usr/local/bin/nancy https://github.com/sonatype-nexus-community/nancy/releases/download/v0.1.17/nancy-linux.amd64-v0.1.17
```
```shell
sudo chmod +x /usr/loca/bin/nancy
```
If you prefer to compile from source, that is of course also possible, and the instructions for this can be found in the project repository on GitHub.
***

## 
