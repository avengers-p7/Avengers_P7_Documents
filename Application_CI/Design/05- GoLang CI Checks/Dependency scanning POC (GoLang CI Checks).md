# Dependency scanning POC (GoLang CI Checks)

![image](https://github.com/avengers-p7/Documentation/assets/156056570/0f4cf96f-42db-4548-9cbd-c475fd9aba6e)


| Author                 | Created On | Last Updated | Document Version | Last Updated By |
| ---------------------- | ---------- | ------------ | ---------------- | --------------- |
| **Samir Kesare** | 04-02-2024 | 04-02-2024   | v1               |  **Samir**        |
***
## Table of Contents

+ [OWASP Dependency-Check Introduction](#OWASP-Dependency-Check-Introduction)
+ [Key Features](#Key-Features)
+ [Pre-requisite](#Pre-requisite)
+ [OWASP Dependency-check Installation](#OWASP-Dependency-check-Installation)
+ [Proof of Concept (POC)](#Proof-of-Concept-(POC))
+ [HTML Report](#HTML-Report)
+ [ Dependency Scan Report Analysis](#Dependency-Scan-Report-Analysis)
+ [Contact Information](#Contact-Information)
+ [References](#References)
***
## OWASP Dependency-Check Introduction
OWASP Dependency-Check is an open-source security tool that helps identify and mitigate security vulnerabilities in software by analyzing its dependencies. It scans project dependencies for known vulnerabilities and provides actionable insights to developers and security professionals.

***
## Key Features

| Feature               | Description                                                                                           |
|-----------------------|-------------------------------------------------------------------------------------------------------|
| Dependency Analysis   | Conducts thorough analysis of project dependencies, including direct and transitive dependencies.     |
| Vulnerability Detection| Identifies known vulnerabilities in dependencies by comparing component versions against CVE databases.|
| Multiple Ecosystems   | Supports various software ecosystems including Java, .NET, Python, Ruby, JavaScript, and more.         |
| Command-Line Interface| Provides a command-line interface (CLI) for easy integration into CI/CD pipelines and automation scripts.|
| Build Tool Integration| Integrates with popular build tools such as Maven, Gradle, Ant, Jenkins, and others for seamless usage. |
| Extensible Reporting  | Generates comprehensive reports in various formats (HTML, XML, JSON, CSV) for detailed analysis and auditing. |
| Continuous Updates    | Regularly updated with the latest vulnerability databases to ensure accurate detection of security issues.|
| Custom Policies       | Allows users to define custom policies and thresholds for vulnerability severity and reporting.         |
| False Positive Suppression| Offers mechanisms to suppress false positives and customize reporting to reduce noise in scan results.|
| Open Source           | Maintained as an open-source project under the OWASP Foundation, fostering community contribution and collaboration. |

***
## Pre-requisites

* Golang 1.20
* OWASP Dependency-check
* java

***
## OWASP Dependency-check Installation

![image](https://github.com/avengers-p7/Documentation/assets/156056570/e6e405dc-9929-4edd-82f1-e51ce0c5ae42)

```shell
unzip dependency-check-9.0.9-release.zip
```
***
## Proof of Concept

```shell
export JAVA_HOME=/usr/lib/jvm/java-1.17.0-openjdk-amd64
```
```shell
cd dependemcy-check/bin/
```
```shell
./dependency-check.sh --scan /home/ubuntu/employee-api/ --out dep-check.html
```
![image](https://github.com/avengers-p7/Documentation/assets/156056570/8a15332b-c718-4219-bc28-1091f1c87ce8)
![Screenshot 2024-02-05 122407](https://github.com/avengers-p7/Documentation/assets/156056570/69d00f72-1637-4963-9552-67e693259ee7)

***
## HTML Report

![image](https://github.com/avengers-p7/Documentation/assets/156056570/7cb122de-dbcd-4a91-afdb-531b820aee0a)


***
## Dependency Scan Report Analysis

### Overview

Dependency scanning is a crucial step in assessing the security posture of software projects. It involves analyzing the dependencies used in an application to identify known vulnerabilities and potential risks.

### Interpreting Dependency Scan Reports

Dependency scan reports typically include the following information:

- **Dependency Information**: Details about each dependency including name, version, and source.
- **Vulnerability Details**: Information about known vulnerabilities associated with each dependency, including severity levels, CVE IDs, and descriptions.
- **Dependency Licensing**: Information about the licenses associated with each dependency, ensuring compliance with licensing requirements.
- **Policy Compliance**: Evaluation of dependencies against predefined policies and security standards.

### Common Elements in Dependency Scan Reports

1. **Vulnerability Severity**: Dependencies are often categorized by severity levels such as Low, Medium, and High based on the potential risks they pose.
2. **Vulnerability Descriptions**: Reports provide descriptions of vulnerabilities, including information on how they can be exploited and their potential impact.
3. **Remediation Recommendations**: Guidance on how to remediate identified vulnerabilities, such as updating to a patched version or applying workarounds.
4. **Policy Violations**: Identification of dependencies that violate predefined policies or licensing requirements, necessitating corrective actions.

### Actionable Steps

When analyzing dependency scan reports, it's essential to take the following actions:

1. **Prioritize Remediation**: Prioritize addressing high-severity vulnerabilities and policy violations that pose significant risks to the application.
2. **Review Licensing**: Review dependencies with licensing issues to ensure compliance with legal requirements and organizational policies.
3. **Apply Updates**: Implement updates or patches provided by dependency maintainers to mitigate known vulnerabilities.
4. **Monitor Dependencies**: Establish processes for ongoing monitoring of dependencies and regular scans to identify new vulnerabilities as they emerge.
5. **Documentation**: Document findings, remediation actions taken, and any exceptions or mitigations applied for future reference and auditing purposes.
***
## Conclusion

Dependency scanning is a critical component of proactive security practices, helping organizations identify and mitigate potential risks introduced by third-party dependencies. By regularly scanning and addressing vulnerabilities in dependencies, organizations can strengthen the security posture of their software projects and reduce the risk of security breaches.
***
## Contact Information

| Name | Email address |
| ---- | ------------- |
| Samir | samir.kesare.snaatak@mygurukulam.co |

***
## References
[OWASP Dependency Check ](https://owasp.org/www-project-dependency-check/)

[Report Analysis ](https://jeremylong.github.io/DependencyCheck/index.html)



