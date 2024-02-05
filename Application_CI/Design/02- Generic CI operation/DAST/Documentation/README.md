# Dynamic Application Security Testing (DAST)

<img width="360" length="100" alt="Golang" src="https://github.com/avengers-p7/Documentation/assets/156056413/56e9dd64-9654-449c-be6d-4212de6aca71">


| Author                 | Created On | Last Updated | Document Version | Last Updated By |
| ---------------------- | ---------- | ------------ | ---------------- | --------------- |
| **Samir Kesare** | 30-01-2024 | 31-01-2024   | v1               |  **Samir**        |
***
## Table of Contents

+ [Introduction](#Introduction)
+ [What is dynamic application security testing?](#What-is-dynamic-application-security-testing?)
+ [How Does DAST Work](#How-Does-DAST-Work)
+ [Advantages and disadvantages of DAST](#Advantages-and-disadvantages-of-DAST)
+ [Types of Dynamic Application Security Testing](#Types-of-Dynamic-Application-Security-Testing)
+ [How to Use DAST](#How-to-Use-DAST)
+ [SAST VS DAST](#SAST-VS-DAST)
+ [Tools for Golang DAST](#Tools-for-Golang-DAST)
+ [Contact Information](#Contact-Information)
+ [References](#References)
***
## Introduction
Dynamic Application Security Testing (DAST) is the process of analyzing a web application through the front-end to find vulnerabilities through simulated attacks. This type of approach evaluates the application from the “outside in” by attacking an application like a malicious user would. After a DAST scanner performs these attacks, it looks for results that are not part of the expected result set and identifies security vulnerabilities.
***
## What is dynamic application security testing?
- **Dynamic Application Security Testing (DAST) Overview:**
  - Refers to security testing conducted on a running application, not static code.
  - Aims to identify and list security vulnerabilities and misconfigurations.
  - The term "DAST" can apply to both the testing methodology and tools utilizing this approach.

- **Characteristics of DAST:**
  - Typically used for web applications, though in theory applicable to legacy desktop apps.
  - Recent advancements have made DAST tools available for mobile applications.
  - DAST solutions are designed to integrate into automation processes.

- **Application Types and Tools:**
  - DAST primarily targets web applications due to their accessibility.
  - Limited availability for legacy desktop applications due to diverse UIs.
  - Emerging support for mobile applications in DAST tools.

- **Automation and Methodology:**
  - DAST tools are designed to operate as part of automated processes.
  - Manual DAST testing is often considered part of penetration testing.
  - Other terms for DAST include black-box testing, vulnerability scanning, and outside-in testing.

  ***
  ## How Does DAST Work?
  - Dynamic application security testing tools simulate the actions of a black-hat hacker in a safe environment.
  - DAST scanners first map out the application at runtime using a web crawler.
    - This includes identifying all application pages, following links, and discovering functions (for single-page web apps).
    - In API testing, DAST follows an API definition document to identify available entry points.
  - After mapping the application, the vulnerability scanner accesses each input location found (e.g., form fields, API parameters) and performs security checks.
    - Security checks involve sending data to the application and analyzing responses for vulnerabilities.
    - Test data mimics malicious content sent by a black-hat hacker.
  - When the DAST scan identifies a response suggesting or proving a vulnerability, it records the location and response for user presentation.
    - This allows manual reenactment of testing scenarios if necessary.
  - DAST solutions focus on identifying security issues like SQL injection or cross-site scripting (XSS) vulnerabilities.
    - They do not perform remediation; fixing identified risks is the responsibility of development teams.
***
## Advantages and disadvantages of DAST

| **Advantages of Dynamic Application Security Testing (DAST)** | **Disadvantages of Dynamic Application Security Testing (DAST)** |
|-------------------------------------------------------------|-------------------------------------------------------------------|
| - Can be conducted at various stages of the software development lifecycle. | - Limited to testing parts of the application that are already runnable. |
| - Does not require modification of deployed applications, beneficial for legacy systems. | - Difficulty accessing sections of the application not yet deployed. |
| - Language-independent; can test applications with web user interfaces. | - Challenges with non-standard authentication and authorization mechanisms. |
| - Capable of testing application APIs. | - Difficulty in following complex business logic without careful tuning. |
| - Typically has lower false positive and false negative rates compared to SAST tools. | - Testing may interfere with normal application operation if not carefully tuned. |
| - Simulates user actions, enhancing accuracy in identifying vulnerabilities. | - Preferable to run DAST tools in non-live environments to avoid disruptions. |

***
## Types of Dynamic Application Security Testing

While there are no formal subtypes of DAST, security experts informally classify DAST tools into two groups: modern DAST and legacy DAST. Here are the main characteristics used to distinguish between them:

=== Automation and Integration ===
- **Legacy DAST:**
  - Designed for ad-hoc manual scanning.
  - Limited automation beyond scanning; results are manually reviewed.
- **Modern DAST:**
  - Integrated into the Software Development Lifecycle (SDLC) with tools like Jenkins.
  - Scan results are automated and integrated into developers' issue trackers.

=== Vulnerability Confirmation/Validation ===
- **Legacy DAST:**
  - Performs basic testing, lacking confirmation methods beyond response analysis.
- **Modern DAST:**
  - Conducts checks to confirm vulnerabilities with high certainty.
  - Provides proof of exploitation, reducing the need for manual confirmation.

Most DAST tools are commercial products, although open-source alternatives exist. Open-source solutions like OWASP Zed Attack Proxy (ZAP) are often categorized as legacy DAST due to limited functionality. Many open-source projects are manual penetration testing tools rather than application security scanners.

Some modern DAST tools meeting the criteria outlined above include Invicti and Acunetix by Invicti. These solutions offer full automation, integration, and vulnerability confirmation.
***
## How to Use DAST 

The traditional approach to using DAST involved manual scanning of web assets on an ad-hoc basis or conducting vulnerability scans in the final stages of application development, such as on staging servers or production clones. However, this is no longer the recommended method. Modern DAST solutions offer interfaces that facilitate usage at various stages of application development:

=== Early Development (Shift Left) ===
- Modern DAST tools are intended for use in DevOps/DevSecOps environments to test applications as early as possible, even from the initial builds.
- It's advisable to conduct DAST scans on a runtime app at the earliest stage to eliminate vulnerabilities before they progress to later stages.
- Security testing should be integrated into the CI/CD pipeline, similar to functional testing.

=== Staging/Pre-release ===
- Security testing should be incorporated into the pre-release process, where application functionality is fully accessible.
- The application should be fully deployed as it will be in production and thoroughly tested independently of earlier development-time testing.

=== Regular Post-release (Shift Right) ===
- Modern DAST tools offer less invasive scanning compared to legacy tools and can be fine-tuned for safe usage, even in live production environments.
- Tuning includes ensuring no test data is introduced or deleted from the production system, no test emails are sent, and request volumes do not disrupt normal app operation.
- If security testing in a live production environment is uncomfortable, consider creating a clone of the production environment for regular testing.
- Recommended scanning schedules include daily checks for high-severity vulnerabilities and weekly full scans.

Regular scans help detect unexpected modifications or new vulnerabilities resulting from changes in deployment configurations or updates to DAST tools to address newly discovered vulnerabilities and exploits.
***
## SAST VS DAST

| Aspect               | SAST                                                | DAST                                                |
|----------------------|-----------------------------------------------------|-----------------------------------------------------|
| Testing Approach     | Analyzes source code or binaries without execution  | Tests the application in its running state          |
| Timing               | Performed during development phase                  | Conducted post-development, in runtime              |
| Scope                | Concentrates on source code analysis                | Focuses on runtime behavior                          |
| Vulnerability Detection | Identifies potential vulnerabilities based on code analysis | Identifies vulnerabilities while interacting with the application |
| False Positives      | May generate more false positives due to static analysis | Tends to have fewer false positives, simulating real user interactions |
| Coverage             | Scans entire codebase regardless of execution paths | Provides coverage for implemented features and application logic |
| Integration          | Often integrated into development environments or IDEs | Can integrate with CI/CD pipelines for automated testing |
| Types of Vulnerabilities | Proficient at identifying code-level vulnerabilities such as injection flaws, buffer overflows, etc. | Better at identifying certain types of vulnerabilities like session management issues, authentication flaws, etc. |
| Ease of Use          | May require expertise to configure and interpret results | Generally easier to set up and execute scans |
| Runtime Impact       | Does not affect the runtime performance of the application | May have minimal impact on application performance |
| Scalability          | May face challenges with large codebases or complex applications | Well-suited for dynamic and frequently changing applications |
| Cost                 | Costs may vary based on tooling and licensing      | Costs may vary based on tooling and licensing      |

***
## Tools for Golang DAST
 | Tool          | Description                                             | Features                                                      | Integration         | License       |
|---------------|---------------------------------------------------------|---------------------------------------------------------------|---------------------|---------------|
| OWASP ZAP     | Open-source web application security scanner            | - Automated scanning for common security vulnerabilities     | CLI, CI/CD          | Apache 2.0    |
| Burp Suite    | Integrated platform for security testing of web apps    | - Advanced scanning, proxy, and vulnerability assessment     | GUI, API            | Commercial    |
| GoSec         | Golang security checker                                 | - Static analysis for security vulnerabilities                | CLI, CI/CD          | MIT           |
| Gosec Scanner | Golang security checker                                 | - Scans for common security vulnerabilities                    | CLI, CI/CD          | Apache 2.0    |
| Safe          | Go library for security-related issues                  https://www.invicti.com/learn/dynamic-application-security-testing-dast/| - Scans for common security vulnerabilities                    | Library             | MIT           |
| Staticcheck   | Go static analysis tools                                | - Detects bugs, performance problems, and much more            | CLI, CI/CD          | GPLv3         |

***
## Conclusion:

- **OWASP ZAP**:
                Offers powerful automated scanning for web applications, suitable for GoLang apps with integration options for CLI and CI/CD pipelines. Licensed 
  under Apache 2.0.

***
## Contact Information

| Name | Email address |
| ---- | ------------- |
| Samir | samir.kesare.snaatak@mygurukulam.co |

***
## References
[What is dynamic application security testing?](https://www.invicti.com/learn/dynamic-application-security-testing-dast/)

[How to Use DAST](https://www.invicti.com/learn/dynamic-application-security-testing-dast/)

[DAST Tools for golang](https://owasp.org/www-community/Free_for_Open_Source_Application_Security_Tools)
