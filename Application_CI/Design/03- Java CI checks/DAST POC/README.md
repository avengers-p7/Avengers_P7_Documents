
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
### Pre-requisites
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
tar -xf ZAP_2.14.0_Linux.tar.gz
```

### 2. Run ZAP
* Now, to run our zap for analysis process.  Now running zap via zap.sh via -cmd or in daemon mode as it run the zap in Cli mode as shown below

```
<path to zap.sh> -port <port_no> -cmd -quickurl <url of website>
```

* <path to zap.sh> This is the executable file for OWASP ZAP
* The -port specifies the port on which ZAP will listen.
* -cmd indicates that the command should be executed in command-line mode.
* The -quickurl flag followed by the <url_of_website> parameter starts ZAP with the specified target URL.

### 3. Scanning API url

* The API and ZAP tool have been deployed on a virtual server. It has been ensured that the API is functioning correctly, and we can now proceed with the testing phase. For this process the following command was used:

```
/home/ubuntu/ZAP_2.14.0/zap.sh -cmd -quickurl http://34.69.125.44:8080/swagger-ui/index.html -port 8082 -quickout /home/ubuntu/zap_reports/results.html
```

### 4. Verify Reports 

* Navigate to the location where you saved your reports. Locate the generated `.html` reports. Ensure that vulnerabilities are correctly identified.

<img width="869" alt="Screenshot 2024-02-04 at 4 15 57 PM" src="https://github.com/avengers-p7/Documentation/assets/156056349/dfd7b50d-3579-45b5-8d0e-62697abf456d">

* The reports include information about the risk level and the number of alerts categorized. Following this overview, the reports provide specific details on each alert, presenting the alert name along with a concise description

<img width="1332" alt="Screenshot 2024-02-04 at 4 17 10 PM" src="https://github.com/avengers-p7/Documentation/assets/156056349/ab99ce71-b473-4632-acd2-09143560b548">


## Conclusion

* In conclusion, ZAP to check the security of our Java application, and it helped us find and fix some problems. But, it's important to know that keeping the application secure is an ongoing task. The information we got from this test is like a good starting point to make the application even more secure. It is advised to treat these findings seriously and implement appropriate remediation measures for overall security of our application.

* Since, security risks are always changing, it's really important to keep paying attention and regularly test and fix any issues in our applications. This ongoing effort is key to making sure our application stays strong and secure.

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



