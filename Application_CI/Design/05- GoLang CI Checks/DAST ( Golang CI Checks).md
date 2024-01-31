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
+ [Steps of unit testing](#Steps-of-unit-testing)
  + [Cloning the Go Application](#Within-the-directory,-make-a-clone-of-the-repository)
  + [Install Prerequisites](#Install-Prerequisites)
  + [Run the Tests](#Run-the-Tests)
  + [Generating the report](#Generating-the-report)
+ [Unit Testing in Other Languages](#Unit-Testing-in-Other-Languages)
+ [Conclusion](#Conclusion)
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


