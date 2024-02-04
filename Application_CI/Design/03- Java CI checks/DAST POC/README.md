
# Proof of Concept (POC) for DAST

|   Authors        |  Created on   |  Version   | Last updated by | Last edited on |
| -----------------| --------------| -----------|---------------- | -------------- |
| Vidhi Yadav      | 25 Jan 2024   |     v1     | Vidhi Yadav     | 29 Jan 2024    |


<img width="475" alt="Screenshot 2024-02-04 at 1 43 55 PM" src="https://github.com/avengers-p7/Documentation/assets/156056349/0fb70c67-ed18-491e-87cb-7a54953ab6c2">

## Table of Contents
+ [Introduction](#Introduction)
+ [OWASP ZAP](#owasp-zap)
+ [Proof of Concept](#Pre-requisite)
+ [Conclusion](#conclusion)
+ [Contact Information](#contact-information)
+ [References](#references)

***
## Introduction 
* Dependency scanning is a crucial aspect of modern software development, ensuring the security and reliability of your projects. This process involves identifying and managing the third-party libraries and frameworks your project depends on. By scanning for known vulnerabilities in these dependencies, you can proactively address potential security risks and keep your applications robust and secure. This document will guide you through a Proof of Concept (PoC) for setting up and utilizing OWASP Dependency-Check to perform comprehensive dependency scanning in your projects.

***
## OWASP ZAP
OWASP is an open-source tool widely utilized for identifying known vulnerabilities in project dependencies. This tool automatically analyzes dependencies and checks them against a comprehensive database of security vulnerabilities, including the National Vulnerability Database (NVD). It supports various programming languages and build tools, making it a versatile choice for enhancing the security of software projects. 

*** 
Flow Diagram




***
## Proof of Concept (PoC) - Setting Up Dependency Scanning
### Pre-requisite
|   Tool        |  Description   |
| -----------------| --------------|
| OWASP ZAP (version: 2.14)     | Tool required to perform DAST   |   

|   Runtime         |  Description   |
| -----------------| --------------|
| JRE (Java runtime environment     | Zap is coded in Java, and its fundamental operations require a Java runtime environment for execution.    |

### 1. Setup ZAP

* Visit zap [website](https://www.zaproxy.org/docs/) and check the different installation packages for different OS

* Run the following command to download zap linux package using `wget`, then to extract the package.

```
wget https://github.com/zaproxy/zaproxy/releases/download/v2.14.0/ZAP_2.14.0_Linux.tar.gz
```

### 4. Verify Reports 

* Navigate to the build artifacts or workspace. Locate the generated Dependency-Check reports in the `target` folder. They are typically available in multiple formats (JSON, HTML, XML). Ensure that vulnerabilities are correctly identified. If you configured multiple report formats , explore each format to understand the data presentation.


<img width="722" alt="Screenshot 2024-01-31 at 6 18 35 PM" src="https://github.com/avengers-p7/Documentation/assets/156056349/98a80636-753a-4cb6-b39e-5454472ada01">


## Conclusion

* In conclusion, integrating OWASP Dependency-Check into your development process offers a proactive approach to identifying and mitigating potential security risks associated with third-party dependencies. By regularly scanning and analyzing your project dependencies, you can stay ahead of known vulnerabilities, ensuring the overall security and reliability of your software applications


***
## Contact Information

|Vidhi Yadav                     | vidhi.yadhav.snaatak@mygurukulam.co                                                                                      
|---------------------------------|------------------------------------------------------------|

***
## References

| Title                                      | URL                                           |
|--------------------------------------------|-----------------------------------------------|
| owasp documentation           | https://www.zaproxy.org/    |
| OWASP Dependency-Check GitHub Repository    | https://github.com/jeremylong/DependencyCheck  |



