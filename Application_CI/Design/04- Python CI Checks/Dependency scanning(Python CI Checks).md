# Dependency Scanning ( Python CI Checks ) (POC)
| Author                 | Created On | Last Updated | Document Version | Last Updated By |
| ---------------------- | ---------- | ------------ | ---------------- | --------------- |
| Vishal Kumar Kesarwani | 30-01-2024 | 01-02-2024   | v1               |  Vishal         |
***

## Table of Contents 
+ [Introduction](#Introduction)
+ [Dependency scanning](#Dependency-scanning)
+ [OWASP](#OWASP-Dependency-Check )
+ [Proof of Concept](#Pre-requisite)
+ [Conclusion](#Conclusion)
+ [Contact Information](#contact-information)
+ [References](#references)

***
## Introduction
Dependency scanning is vital in contemporary software development for securing and stabilizing your projects. This involves recognizing and handling the external libraries and frameworks your project relies on. By checking for known vulnerabilities in these dependencies, you can preemptively tackle security threats and maintain the strength and security of your applications. This guide will walk you through a Proof of Concept (PoC) for implementing and utilizing OWASP Dependency-Check to conduct thorough dependency scanning in your Go projects.
***
## Dependency scanning

* Dependency scanning is a process used in software development to identify and analyze the external dependencies or third-party components that a project relies on. These dependencies can include libraries, frameworks, modules, packages, or other code modules that are utilized to build and run the software. 

* The scanning process is typically automated and integrated into the development workflow, often as part of continuous integration or continuous delivery (CI/CD) pipelines. It serves as a crucial post-build process examines the project's dependencies to identify any known vulnerabilities, outdated versions, or security issues. 

* For more detail click [**here**](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/03-%20Java%20CI%20checks/Dependency%20Scanning/%20README.md)      
***
## OWASP Dependency-Check    
<img width="360" length="300" alt="OWASP" src="https://github.com/avengers-p7/Documentation/assets/156056413/4b0dadd1-816c-49d1-8436-b8d68ebe1c4c">  

OWASP is an open-source tool widely utilized for identifying known vulnerabilities in project dependencies. This tool automatically analyzes dependencies and checks them against a comprehensive database of security vulnerabilities, including the National Vulnerability Database (NVD). It supports various programming languages and build tools, making it a versatile choice for enhancing the security of software projects.
***

## Proof of Concept
### Pre-requisite
***
## Conclusion
Implementing dependency scanning with OWASP for Python CI checks strengthens our security posture by proactively identifying and mitigating vulnerabilities in project dependencies. By integrating OWASP tools into our CI pipeline, we enhance our ability to deliver secure and reliable software to our users.
***
## Contact Information

| Name | Email address |
| ---- | ------------- |
| Vishal | vishal.kesarwani.snaatak@mygurukulam.co |

***

## References

| Source | Description |
| ------ | ----------- |
| [Link](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/03-%20Java%20CI%20checks/Dependency%20Scanning/%20README.md) | Introduction of Dependency scanning |
