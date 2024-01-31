|   Author        |  Created on   |  Version   | Last updated by  | Last edited on |
| --------------- | --------------| -----------|----------------- | -------------- |
| Khushi Malhotra |  30 Jan 2024  |  Version 1 | Khushi Malhotra  | 31 Jan 2024    |
***
# Static Code Analysis - Go Language 

# Table of Contents
- [What is Static Code Analysis](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/05-%20GoLang%20CI%20Checks/Static_Code_Analysis_Go_Language.md#what-is-static-code-analysis)
- [Why we need Static Code Analysis](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/05-%20GoLang%20CI%20Checks/Static_Code_Analysis_Go_Language.md#why-we-need-static-code-analysis)
- [Different tool used in Static Code Analysis](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/05-%20GoLang%20CI%20Checks/Static_Code_Analysis_Go_Language.md#different-tool-used-in-static-code-analysis)
- [Comparison between static-lint, SonarQube and gosec](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/05-%20GoLang%20CI%20Checks/Static_Code_Analysis_Go_Language.md#comparison-between-static-lint-sonarqube-and-gosec)
- [Choosing gosec](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/05-%20GoLang%20CI%20Checks/Static_Code_Analysis_Go_Language.md#choosing-gosec)
- [POC of Static Code Analysis](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/05-%20GoLang%20CI%20Checks/Static_Code_Analysis_Go_Language.md#poc-of-static-code-analysis)
- [gosec Report File](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/05-%20GoLang%20CI%20Checks/Static_Code_Analysis_Go_Language.md#gosec-report-file)
- [Conclusion](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/05-%20GoLang%20CI%20Checks/Static_Code_Analysis_Go_Language.md#conclusion)
- [Contact Information](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/05-%20GoLang%20CI%20Checks/Static_Code_Analysis_Go_Language.md#contact-information)
- [Resources and References](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/05-%20GoLang%20CI%20Checks/Static_Code_Analysis_Go_Language.md#resources-and-references)
***
# What is Static Code Analysis
Static code analysis is a method of debugging that is done by automatically examining the source code without having to execute the program. 
Static code analysis tools attempt to highlight possible vulnerabilities within 'static' (non-dynamic) code. 
These tools are useful as they provide immediate feedback to the developer on issues they might be introducing into the code, which is very useful as compared to finding vulnerabilities much later in the development process. 

# Why we need Static Code Analysis

| Aspects                        | Description                                                                                              |
|--------------------------------|----------------------------------------------------------------------------------------------------------|
| **Early Issue Identification**   | Static code analysis helps in identifying potential issues early in the development process, preventing costly debugging efforts later on. |
| **Code Quality Assurance**      | It ensures code quality by identifying and addressing potential vulnerabilities, security issues, and non-compliance with coding standards. |
| **Improved Security**           | By detecting security vulnerabilities early in the software development life cycle, it helps prevent security breaches and reduces the risk and cost of a security breach. |
| **Efficiency and Cost Savings** | It increases efficiency by reducing the time and effort required for debugging and fixing defects later in the development cycle, leading to productivity gains and cost savings. |
| **Comprehensive Code Evaluation**| It evaluates all the code in an application, increasing code quality and providing a more in-depth analysis compared to manual code review. |
| **Automated and Thorough Analysis** | Static code analysis is usually an automated process that can find vulnerabilities in even the most remote and unattended parts of the code, providing a more thorough analysis. |

# Different tool used in Static Code Analysis
| Tool         | Focus                                                                        |
|--------------|-------------------------------------------------------------------------------|
| **static-lint** | Primarily focuses on security-related issues, detecting potential vulnerabilities and insecure coding practices in Go code. |
| **SonarQube**   | Provides a broader scope, encompassing static code analysis, code coverage, code duplication, security scans, and code smells. It offers a holistic platform for overall code quality assessment. |
| **gosec**       | Similar to static-lint, specializes in security analysis of Go code but with a specific focus on known vulnerabilities listed in the Go Vulnerability Database (GoVD). |


# Comparison between static-lint, SonarQube and gosec
| Aspect            | static-lint                                                   | SonarQube                                                      | gosec                                                            |
|-------------------|---------------------------------------------------------------|-----------------------------------------------------------------|------------------------------------------------------------------|
| **Focus**         | Primarily focuses on security-related issues in Go code.       | Provides a broader scope, covering static code analysis, code coverage, code duplication, security scans, and code smells. | Specializes in security analysis of Go code, focusing on known vulnerabilities listed in the Go Vulnerability Database (GoVD). |
| **Features**      | Offers a curated set of security-focused rules, supports integration with CI/CD pipelines, and provides detailed reports with remediation suggestions. | Features a vast range of rules for various aspects of code quality, customizable dashboards and reports, plugin integrations (including static-lint), and project and team-level analysis. | Leverages the GoVD for comprehensive vulnerability detection, integrates with CI/CD pipelines, and generates reports highlighting insecure coding practices. |
| **Ease of Use**   | Relatively lightweight and simple to set up, requiring minimal configuration. | More complex to set up and configure, often requiring server installation and configuration. However, it offers a user-friendly interface and extensive documentation. | Easy to integrate into existing workflows, requiring minimal configuration beyond specifying the codebase to scan. |
| **Cost**          | Open-source and free to use.                                  | Offers both free and paid tiers with varying features and functionalities. The free Community Edition provides basic code quality analysis. | Open-source and free to use.                                      |
| **Overall**       | Ideal for developers primarily concerned with security vulnerabilities in their Go code. Its simplicity and focus on security make it a good choice for quick scans and CI/CD integration. | Suitable for teams seeking a comprehensive code quality analysis platform. Its extensive features and flexibility cater to various code quality aspects beyond just security. | A valuable tool for developers and organizations prioritizing secure coding practices in Go. Its focus on the GoVD and ease of use make it a strong choice for vulnerability detection. |

# Choosing gosec
Our primary concern is detecting and mitigating security vulnerabilities in my Go code, gosec is a compelling choice. Its focus, ease of use, and free availability make it an efficient and cost-effective tool for ensuring secure coding practices.

# POC of Static Code Analysis

# Prerequisites
1. Install go 
2. Install gosec

**Step-1** Install go
``` Shell
sudo snap install go --classic
```
![WhatsApp Image 2024-01-31 at 19 50 08_4281265c](https://github.com/avengers-p7/Documentation/assets/156056460/c8b08dad-aecf-4f02-a7e7-0938b4075c0b)
``` shell
sudo snap install gosec
```
![WhatsApp Image 2024-01-31 at 18 29 49_ad9184ce](https://github.com/avengers-p7/Documentation/assets/156056460/db86ed1c-60c7-46ca-a9f3-77881921dd4e)
***
**Step-2** Run Gosec
- Run gosec on your project. This will perform static code analysis and generate a report.
``` Shell
gosec ./...
```
![WhatsApp Image 2024-01-31 at 18 32 35_22af5693](https://github.com/avengers-p7/Documentation/assets/156056460/1c0ff99f-4177-444f-aed3-dd5cea9fdf02)
***
![WhatsApp Image 2024-01-31 at 18 32 48_b096c587](https://github.com/avengers-p7/Documentation/assets/156056460/192174c5-3316-4f44-a189-a1ccf9c86943)

![WhatsApp Image 2024-01-31 at 18 32 59_afa1689f](https://github.com/avengers-p7/Documentation/assets/156056460/37322234-bb24-4619-a479-c8ab876bb3fe)
***
**Step-3** Review the Report:
- After running gosec, it will generate a report highlighting any security issues it finds. The report will include information about the issues, their severity, and the affected files. Open the report in a text editor or browser.

- By default, gosec outputs the report in the console. If you want to generate a report in JSON or other formats, you can use the -fmt flag.
``` shell
gosec -fmt=json -out=gosec-report.json ./...
```
![WhatsApp Image 2024-01-31 at 18 33 43_6e7f4263](https://github.com/avengers-p7/Documentation/assets/156056460/966d3263-5618-4a6f-b2b6-be0e80cf6253)
***
# gosec Report File
[gosec-report.json](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/05-%20GoLang%20CI%20Checks/gosec-report.json)


# Conclusion
Gosec is a powerful tool for enhancing Go code security through static analysis. Its integration into development workflows and careful attention to its findings can significantly reduce vulnerabilities and strengthen application resilience.

# Contact Information
| Name            | Email Address                        |
|-----------------|--------------------------------------|
| Khushi Malhotra | khushi.malhotra.snaatak@mygurukulam.co |

# Resources and References
[What is Static Code Analysis](https://owasp.org/www-community/controls/Static_Code_Analysis)

[Why we need Static Code Analysis](https://softwareengineering.stackexchange.com/questions/27682/what-are-the-real-benefits-of-static-code-analysis)

[gosec](https://opensource.com/article/20/9/gosec)
