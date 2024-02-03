# DAST_POC ( Golang CI Checks)

<img width="360" length="100" alt="Golang" src="https://github.com/avengers-p7/Documentation/assets/156056413/56e9dd64-9654-449c-be6d-4212de6aca71">


| Author                 | Created On | Last Updated | Document Version | Last Updated By |
| ---------------------- | ---------- | ------------ | ---------------- | --------------- |
| **Samir Kesare** | 02-02-2024 | 02-02-2024   | v1               |  **Samir**        |
***
## Table of Contents

+ [OWASP ZAPIntroduction](#OWASP-ZAP-Introduction)
+ [Key Features](#Key-Features)
+ [Pre-requisite](#Pre-requisite)
+ [OWASP ZAP Installation](#OWASP-ZAP-Installation)
+ [Proof of Concept (POC)](#Proof-of-Concept-(POC))
+ [html Report](#html-Report)
+ [Analyzing the report ](#Analyzing-the-report )
+ [Contact Information](#Contact-Information)
+ [References](#References)
***
## OWASP ZAP Introduction
OWASP ZAP (Zed Attack Proxy) is an open-source web application security testing tool maintained by the Open Web Application Security Project (OWASP). It is designed to help developers, testers, and security professionals find security vulnerabilities in web applications during development and testing phases.

***
## Key Features

| Feature                | Description                                                                      |
|------------------------|----------------------------------------------------------------------------------|
| Proxy Functionality    | Acts as an intercepting proxy between the user's browser and the target server. |
| Active Scanning        | Conducts automated security scans on web applications to identify vulnerabilities. |
| Passive Scanning       | Observes traffic passively to identify potential security issues.                |
| Fuzzer                 | Provides automated tools for generating malicious input to test application responses. |
| Spider                 | Crawls through web applications to discover and map out its structure.          |
| WebSockets Support     | Capable of intercepting and analyzing WebSocket communication.                  |
| REST API               | Exposes functionality via a REST API for integration with other tools and scripts. |
| Authentication Support | Offers support for various forms of authentication to test protected areas.      |
| Custom Scripts         | Allows users to create and execute custom scripts for specific testing scenarios. |
| Reporting              | Generates comprehensive reports detailing identified vulnerabilities and issues. |
| Community Support      | Supported by an active community providing updates, plugins, and documentation.  |

***
## Pre-requisite

OWASP ZAP, is written in Java. It relies on the Java Runtime Environment (JRE) to work. In other words, we need Java installed on your computer to run ZAP effectively.

***

## OWASP ZAP Installation

Run the following command to download zap linux Package on local machine.
```shell
wget https://github.com/zaproxy/zaproxy/releases/download/v2.14.0/ZAP_2.14.0_Linux.tar.gz
``` 
then to extract the package 
```shell
tar -xf ZAP_2.14.0_Linux.tar.gz
```
***
## Proof of Concept (POC)

Below command consist of running zap via zap.sh via -cmd or in daemon mode as it run the zap in Cli mode as shown below

```shell
./zap.sh -cmd -port 8090-quickurl http://35.188.170.25:8080/api/v1/employee/health -quickprogress -quickout ~/out2.html
```
 let's break down the command:

```shell
./zap.sh
```
This part of the command invokes a script named zap.sh. The ./ at the beginning tells the shell to look for the script in the current directory.

```shell
-cmd
```
This flag specifies that the subsequent argument (-quickurl, -quickprogress, -quickout) should be treated as a command to be executed by zap.sh.

```shell
-quickurl http://54.169.248.202:8080/api/v1/employee/health
```
This flag indicates the URL that the script zap.sh should interact with. In this case, the URL is http://54.169.248.202:8080/api/v1/employee/health.

```shell
-quickprogress
```
This flag likely instructs zap.sh to provide progress updates quickly or in a condensed format during its execution.

```shell
-quickout ~/out2.html
```
This flag specifies the output file for the results of the operation. In this case, the output is redirected to ~/out2.html, where ~ represents the user's home directory.

![image](https://github.com/avengers-p7/Documentation/assets/156056570/c25c04e7-b485-4548-a34f-aba3131372c3)

![image](https://github.com/avengers-p7/Documentation/assets/156056570/45e4597b-f06e-41c6-b7b7-7dd38055d122)

***
## html Report

 the output reprt is redirected to ~/out2.html
```shell
-quickout ~/out2.html
```
![image](https://github.com/avengers-p7/Documentation/assets/156056570/6458591f-a3ad-440e-aa70-72bf4c404450)

***
## Analyzing the report 

So we found issues like Cross-Domain Misconfiguration and X-Content-Type-Options Header Missing, now down below we going to explain them and explore some remediation steps.this report highlights a low-severity security issue related to the missing "X-Content-Type-Options" header in the HTTP response. The recommended solution is to set the appropriate headers to prevent MIME-sniffing, which is especially important for older web browsers.

* Severity: Low

Description: The issue is related to the absence of the "X-Content-Type-Options" header in the HTTP response. This header is used to prevent MIME-sniffing, which is a security feature that browsers employ to determine the content type of a response. Without this header, older versions of Internet Explorer and Chrome may perform MIME-sniffing, potentially causing the response to be interpreted and displayed as a different content type than what was declared.

* URL: This is the URL of the web application where the issue was detected.

* Method: The HTTP method used for the request, in this case, it's a GET request.

* Parameter: The parameter associated with the issue, in this case, "x-content-type-options."

* Attack: This section typically describes how an attacker could potentially exploit the issue, but in this case, it's not specified.

* Evidence: There's no specific evidence mentioned in the report.

Other Info: This note explains that the issue still applies to error pages (e.g., 401, 403, 500) as they can also be affected by injection issues, potentially causing browsers to interpret the content type incorrectly.

***
## Contact Information

| Samir Kesare                    | samir.kesare.snaatak@mygurukulam.co                                                                                  
|---------------------------------|------------------------------------------------------------|

***

## References


|     Description                  | References  
| ---------------------------------| ------------------------------------------------------------------- |
|     OWASP ZAP Download      | https://www.zaproxy.org/download/ |
|     Analysis Report        | https://security.docs.wso2.com/en/latest/security-guidelines/secure-engineering-guidelines/dynamic |  


