# Documentation of static code analysis

***

|Author  | Created on |version | last updated on|
|--------|------------|---------|----------------|
|Nidhi Bhardwaj | 28-01-2024  | V1 | 28-01-2024 |

***

# Table of Content

1. Introduction
2. What
3. Different Tools for static code compilation
4. Comparison
5. Best Practices
6. conclusion
7. Contact Information
8. References

***

# Introduction 

Static code analysis in Java CI (Continuous Integration) involves the automated examination of source code without executing it, aiming to identify potential issues, enforce coding standards, and improve overall code quality. This process is an integral part of the CI/CD (Continuous Integration/Continuous Deployment) pipeline, helping developers catch and rectify issues early in the development lifecycle.

***


# What is Java static code analysis 

Static code analysis in Java CI (Continuous Integration) refers to the automated process of examining source code for potential issues, adherence to coding standards, and other best practices without actually executing the code. This analysis occurs during the development pipeline and is typically triggered by code changes pushed to a version control system like Git. The goal is to catch and address issues early in the development process, facilitating the creation of high-quality and maintainable Java applications.

***

# Different Tools for static code compilation

Static code analysis tools help developers analyze source code for potential issues, coding standard violations, and other problems without executing the code. Here are some popular static code analysis tools used for various programming languages, including Java:

***

| Name |Language Support |Purpose|
|------|-----------------|-------|
|Checkstyle |  Primarily for Java |  Enforces coding standards and conventions, such as naming conventions, code formatting, and other style-related rules|
|PMD | java, JavaScript, Salesforce.com Apex, PLSQL, XML| Identifies issues like suboptimal code, unused variables, and potential bugs. Offers a set of rules that can be customized|
| FindBugs | Java | Identifies common programming errors, potential bugs, and performance issues in Java code. No longer actively maintained, but its successor is the SpotBugs tool|
| SpotBugs | Java | A successor to FindBugs, SpotBugs is a static analysis tool for Java bytecode. It can identify bugs and other issues in compiled Java code |
| SonarQube | Multi-language support, including Java, JavaScript, C#, and many others |  Provides a comprehensive platform for continuous inspection of code quality, security vulnerabilities, and code smells. Integrates with various build tools and CI servers|
|ESLint |  JavaScript, TypeScript | static analysis tool for identifying and fixing problems in JavaScript and TypeScript code. Primarily used for enforcing coding standards and identifying common programming errors |
| TSLint | TypeScript | Deprecated in favor of ESLint for TypeScript. TSLint was a static analysis tool for TypeScript that checked for code quality and style issues |

***

# Comparison 





