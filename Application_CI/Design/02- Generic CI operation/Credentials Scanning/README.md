# Credential Scanning
![5_Best_Practices_for_Credentialed-Scanning_Header](https://github.com/avengers-p7/Documentation/assets/156056344/893d53ce-758a-418d-905c-07d30749e83c)

***
## Table Of Contents 
+ [Introduction](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/Credential%20Scanning.md#introduction)
+ [Why Credential Scanning]()
+ [Types Of Credentials]()
+ [Credential Scanning Tools]()
+ [Tool Comparison]()
+ [When To Scan For Credentials]()
***
## Introduction 
Credential scanning is the practice of automatically inspecting a project to ensure that no secrets are included in the project's source code. Secrets include database passwords, storage connection strings, admin logins, service principals, etc.

## Why Credential Scanning ?
+ Including secrets in a project's source code is a significant risk, as it might make those secrets available to unwanted parties.
+ Spreading secrets in different places makes them harder to manage, access control, and revoke efficiently.
+ Secrets that are committed to source control are also harder to discard of, since they will persist in the source's history.
+ Coupling the project's code to its infrastructure and deployment specifics is limiting and considered a bad practice.

From a software design perspective, the code should be independent of the runtime configuration that will be used to run it, and that runtime configuration includes secrets.As such, there should be a clear boundary between code and secrets: secrets should be managed outside of the source code and *credential scanning* should be employed to ensure that this boundary is never violated.

## Types Of Credentials 
Different types of credentials my be hardcoded in the code and may be inadvertantly pushed to the git repository. These credetials may be :
+ Usernames and Passwords: Often used for accessing private repositories and services.
+ API Tokens: Many services, like GitHub, GitLab, or AWS, use API tokens for authentication and access control.
+ SSH Keys: Used for secure communication between repositories and servers.
+ OAuth Tokens: Used for integrating third-party services.
+ Access Tokens: Employed to control access to services and APIs.
+ Certificates: Used for SSL/TLS connections and code signing.

## When To Scan For Credentials
Ideally, credential scanning should be run as part of a developer's workflow (e.g. via a git pre-commit hook), however, to protect against developer error, credential scanning must also be enforced as part of the continuous integration process to ensure that no credentials ever get merged to a project's main branch.

## Credential Scanning Tools 
Credential scanning tools are used to identify and prevent the exposure of sensitive information, such as usernames, passwords, API keys, and other credentials, within source code, configuration files, or other repositories. Here are some popular credential scanning tools:

| **Tool** | **Description** |
| -------- | --------------- |
| **TruffleHog** | TruffleHog is a Python-based tool that scans Git repositories for high-severity security issues, including potential exposure of credentials. |
| **GitLeaks** | GitLeaks is an open-source tool designed to search through Git repositories for secrets and sensitive information. It supports various file types and allows you to customize the rules for finding credentials. |
| **RepoPeek** | RepoPeek is a lightweight Python tool that scans repositories on GitHub, GitLab, and Bitbucket to find sensitive information, including credentials, API keys, and more. |
| **GitGuardian** | GitGuardian is a commercial tool that specializes in scanning for sensitive data, secrets, and credentials in both public and private repositories. It supports various version control systems and integrates with CI/CD pipelines. |
| **Spectre** | Spectre is an open-source secrets scanner that supports various file types and can be integrated into CI/CD pipelines. It is designed to find secrets such as passwords, API keys, and other sensitive information. |
| **Hawkeye** | Hawkeye is a security tool that scans for secrets, API keys, and other sensitive information in source code repositories. It supports multiple file formats and can be integrated into CI workflows. |
| **Detect-Secrets** | *detect-secrets* is an open-source Python tool that scans code repositories, using regex-based patterns to identify and prevent the accidental inclusion of sensitive information like passwords or API keys. It's easily integrated into CI/CD pipelines and supports customizable configuration for reduced false positives. |

***

## Tool Comparison

| Feature                     | Gitleaks                           | detect-secrets                    | TruffleHog                        |
|-----------------------------|------------------------------------|-----------------------------------|-----------------------------------|
| **Purpose**                 | Scans git repositories for secrets | Searches for secrets in codebases | Searches for secrets in repositories |
| **Installation**            | Simple, binary installation        | Python package, pip install      | Python package, pip install      |
| **Configurability**         | Configurable through rulesets      | Configurable with regex patterns | Limited configuration options   |
| **Supported Repositories**  | Git repositories                   | Any code repository              | Git repositories                 |
| **Performance**             | Fast and lightweight               | Fast                              | Can be slow for large repositories |
| **Integration with CI/CD**  | Yes                                | Yes                               | Yes                               |
| **Custom Rulesets**         | Yes                                | Yes                               | Limited                           |
| **Ease of Use**             | Straightforward CLI usage          | Straightforward CLI usage         | Straightforward CLI usage        |
| **Output Formats**          | JSON, CSV, and others              | JSON, plain text                  | JSON, plain text                  |
| **Open Source**             | Yes, open-source                   | Yes, open-source                  | Yes, open-source                  |
| **Community Support**       | Active community                   | Active community                  | Limited                           |
***

## Advantages 

| **Advantages of Credential Scanning Tools**                   |    **Description**                                   |
|-------------------------------------------------------------|---------------------------------------|
| **Security Improvement:** |  Prevent exposure of sensitive credentials in repositories & reduce attack surface and unauthorized access | 
| **Compliance and Regulatory Compliance:** | Ensure adherence to security standards and regulations & address industry-specific and regional compliance |
| **Early Detection of Vulnerabilities:** | Integrate with CI/CD for early detection in development & reduces time to remediate and mitigate vulnerabilities |      
| **Cost Savings:** | Prevent financial and reputational costs of security incidents & minimizes remediation costs through early detection |                        
| **Maintaining Trust:** | Build customer and user trust through commitment to security as we avoid fallout from data breaches |
***

