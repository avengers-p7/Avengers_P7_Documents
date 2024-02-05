# Dependency scanning (GoLang CI Checks)

<img width="360" length="100" alt="Golang" src="https://github.com/avengers-p7/Documentation/assets/156056413/56e9dd64-9654-449c-be6d-4212de6aca71">


| Author                 | Created On | Last Updated | Document Version | Last Updated By |
| ---------------------- | ---------- | ------------ | ---------------- | --------------- |
| **Samir Kesare** | 30-01-2024 | 31-01-2024   | v1               |  **Samir**        |
***
## Table of Contents

+ [Introduction](#Introduction)
+ [What is Dependency Scanning?](#What-is-Dependency-Scanning?)
+ [Purpose](#Purpose)
+ [Advanatages of Dependency Scanning](#Advanatages-of-Dependency-Scanning)
+ [Implementation](#Implementation)
+ [Best Practices](#Best-Practices)
+ [SAST VS DAST](#SAST-VS-DAST)
+ [Tools for Golang DAST](#Tools-for-Golang-DAST)
+ [Contact Information](#Contact-Information)
+ [References](#References)
***
## Introduction
Dependency scanning is a critical security practice in software development aimed at identifying and managing dependencies within a codebase to mitigate potential security risks. This documentation provides an in-depth overview of dependency scanning, its importance, various tools available, advantages, best practices, recommendations, and references.
***
## What is Dependency Scanning?
Dependency Scanning analyzes your application's dependencies for known vulnerabilities. All dependencies are scanned, including transitive dependencies, also known as nested dependencies. Dependency Scanning is often considered part of Software Composition Analysis (SCA).

Dependency scanning is a crucial aspect of software development that involves analyzing and managing the dependencies within a project's codebase. This process helps developers understand the relationships and interactions between different components, libraries, modules, or packages used in the project.
***
## Purpose

- **Identification of Dependencies:** Dependency scanning helps identify all the dependencies that a project relies on, including third-party libraries, frameworks, and internal modules.
- **Version Management:** It assists in managing the versions of dependencies to ensure compatibility and prevent conflicts.
- **Security Analysis:** Dependency scanning helps identify potential security vulnerabilities in third-party libraries or components, allowing developers to take appropriate actions to mitigate risks.
- **License Compliance:** It helps ensure that the project complies with licensing requirements associated with the dependencies used.
***
## Advanatages of Dependency Scanning

| Advantages of Dependency Scanning                                  |
|--------------------------------------------------------------------|
| **Enhanced Security**: Identifies and alerts about vulnerabilities in dependencies, reducing the risk of exploitation. |
| **Automated Detection**: Automates the process of identifying vulnerable dependencies, saving time and effort. |
| **Early Detection**: Helps in identifying vulnerabilities early in the development lifecycle, allowing for timely remediation. |
| **Comprehensive Coverage**: Scans dependencies across the entire application stack, ensuring thorough vulnerability detection. |
| **Integration**: Can be integrated into CI/CD pipelines for continuous and automated security checks. |
| **Risk Mitigation**: Enables developers to proactively mitigate security risks by addressing vulnerabilities in dependencies. |
| **Regulatory Compliance**: Assists in meeting compliance requirements by ensuring the security of dependencies. |
| **Open Source Support**: Many dependency scanning tools are open source, providing flexibility and cost-effectiveness. |
| **Community Support**: Benefits from community contributions and updates, ensuring up-to-date vulnerability databases. |

***
## Implementation

Dependency scanning can be implemented using various tools and techniques, including:

- **Static Analysis Tools:** Static code analysis tools can be used to analyze the source code and identify dependencies based on import statements, module references, or package definitions.
- **Dependency Management Tools:** Dependency management tools such as Maven, npm, pip, or Gradle can automatically manage and resolve dependencies based on project requirements and configuration files.
- **Dependency Scanning Services:** There are specialized dependency scanning services and tools available that can scan project dependencies for security vulnerabilities, licensing issues, and other concerns.
***
## Best Practices

To effectively manage dependencies and ensure the integrity and security of the project, developers should consider the following best practices:

- Regularly update dependencies to the latest stable versions to leverage new features and security patches.
- Conduct thorough dependency scans and security assessments during the development lifecycle.
- Monitor dependency vulnerabilities and subscribe to vulnerability databases or alerts for timely updates.
- Document and maintain an inventory of project dependencies, including version information and licensing details.
- Follow established coding standards and practices to minimize the risk of introducing incompatible or vulnerable dependencies.

By implementing robust dependency scanning practices, developers can enhance the reliability, security, and maintainability of their software projects.
***
## Tools Comparison for Golang Dependency Scanner

| Tool                   | Description                                           | Features                                                          | Integration         | License       |
|------------------------|-------------------------------------------------------|-------------------------------------------------------------------|---------------------|---------------|
| Nancy                  | Dependency scanning tool for Golang                    | - Identifies and checks for vulnerabilities in GoLang dependencies | CLI, CI/CD          | Apache 2.0    |
| OWASP Dependency-Check | Open-source dependency scanning tool                  | - Supports scanning of dependencies for known vulnerabilities    | CLI, CI/CD          | Apache 2.0    |
| GoSec                  | Golang security checker                               | - Static analysis for security vulnerabilities                    | CLI, CI/CD          | MIT           |
| GoDepend               | Golang dependency analysis tool                       | - Identifies dependencies and their versions                      | CLI                 | Apache 2.0    |
| GoReportCard           | Golang code quality checking tool                     | - Analyzes code quality and dependencies                          | CLI, Web            | MIT           |

### Conclusion - Nancy:

- OWASP Dependency-Check is a software composition analysis tool that helps identify and report known vulnerabilities in project dependencies. It is a crucial component in ensuring the security of software applications by scanning dependencies for known security issues and vulnerabilities.
***
## Contact Information

| Name | Email address |
| ---- | ------------- |
| Samir | samir.kesare.snaatak@mygurukulam.co |

***
## References
[What is Dependency Scanning??](https://learn.microsoft.com/en-us/azure/devops/repos/security/github-advanced-security-dependency-scanning?view=azure-devops#:~:text=Dependency%20scanning%20generates%20an%20alert,software%20that%20direct%20dependencies%20use.)

[Best Practices](https://blog.sonatype.com/best-practices-in-dependency-management-cooking-a-meal-of-gourmet-code)

[Tools for Golang Dependency Scanner](https://jcdan3.medium.com/scanning-go-dependencies-for-vulnerabilities-b82db3d56b27)




