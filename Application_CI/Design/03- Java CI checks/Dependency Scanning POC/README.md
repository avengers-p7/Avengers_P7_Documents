# Proof of Concept (POC) for Dependency-Check

|   Authors        |  Created on   |  Version   | Last updated by | Last edited on |
| -----------------| --------------| -----------|---------------- | -------------- |
| Vidhi Yadav      | 25 Jan 2024   |     v1     | Vidhi Yadav     | 29 Jan 2024    |

<img width="475" alt="Screenshot 2024-02-02 at 11 49 48 AM" src="https://github.com/avengers-p7/Documentation/assets/156056349/89bfd376-b8eb-445f-85c7-30699b35d46d">


## Table of Contents
+ [Introduction](#Introduction)
+ [OWASP](#owasp-dependency-check)
+ [Proof of Concept](#Pre-requisite)
+ [Suppressing dependencies](#dependency-suppression)
+ [Conclusion](#conclusion)
+ [Contact Information](#contact-information)
+ [References](#references)

***
## Introduction 
* Dependency scanning is a crucial aspect of modern software development, ensuring the security and reliability of your projects. This process involves identifying and managing the third-party libraries and frameworks your project depends on. By scanning for known vulnerabilities in these dependencies, you can proactively address potential security risks and keep your applications robust and secure. This document will guide you through a Proof of Concept (PoC) for setting up and utilizing OWASP Dependency-Check to perform comprehensive dependency scanning in your projects.

***
## OWASP Dependency-Check
OWASP is an open-source tool widely utilized for identifying known vulnerabilities in project dependencies. This tool automatically analyzes dependencies and checks them against a comprehensive database of security vulnerabilities, including the National Vulnerability Database (NVD). It supports various programming languages and build tools, making it a versatile choice for enhancing the security of software projects. 

*** 
Flow Diagram

<img width="1168" alt="Screenshot 2024-02-02 at 3 41 52 PM" src="https://github.com/avengers-p7/Documentation/assets/156056349/52eb5029-c332-4395-8445-a4e8f55cb9f4">

***
## Proof of Concept (PoC) - Setting Up Dependency Scanning
### 1. Pre-requisite

**1.1) Java**

* Ensure that you have Java installed on your system. The project requires Java version 17. If you don't have it installed, you can download and install it from the official Java website: [Java Downloads](https://www.oracle.com/java/technologies/downloads/) or use your preferred package manager.

<img width="785" alt="Screenshot 2024-01-31 at 5 04 51 PM" src="https://github.com/avengers-p7/Documentation/assets/156056349/c53fd0f0-8a0d-4e7f-95ce-dfe1da987713">

* Set the `JAVA_HOME` environment variable to the installation directory of your JDK. This variable is essential for Maven to locate the Java runtime.

**1.2) Maven**
* Make sure to have Maven installed on your system. It is a powerful tool used for managing project dependencies. If you don't have Maven installed, please follow the installation instructions for your operating system, which can be found on the official Apache Maven website: [Maven Installation Guide](https://maven.apache.org/install.html).

<img width="1001" alt="Screenshot 2024-01-31 at 5 13 59 PM" src="https://github.com/avengers-p7/Documentation/assets/156056349/f617c048-1754-4e6f-a011-c84d72db00c1">


**1.3) Internet Access to retreive NVD Data**

* The NVD is a comprehensive source of vulnerability information. Dependency-Check can use this data to identify known vulnerabilities in your project's dependencies. It can be configured to fetch data from the NVD's Common Vulnerabilities and Exposures (CVE) database during the analysis process. This helps ensure that the tool has up-to-date information about known vulnerabilities. 

* If your environment does not have internet access or if there are restrictions on accessing external resources, Dependency-Check may still function, but it won't be able to fetch the latest vulnerability data from the NVD.
  
### 2. Configuration

* To enable the `OWASP Dependency-Check` plugin in your Maven project, add the following configuration to your pom.xml file. Ensure this configuration is placed within the `<build>` section

```xml
            <!-- Add the OWASP Dependency-Check plugin -->
            <plugin>
                <groupId>org.owasp</groupId>
                <artifactId>dependency-check-maven</artifactId>
                <version>9.0.9</version>
                <executions>
                    <execution>
                        <goals>
                            <goal>check</goal>
                        </goals>
                    </execution>
                </executions>
            </plugin>
```



### 3. Generate Reports

* This ensures a clean build of your project before checking for vulnerabilities, run the following Maven command to ensure a clean build:
```shell
mvn clean install
```

* To generate a comprehensive report for your project, run the following Maven command in your terminal:

```shell
mvn clean install dependency-check:check -Dformat=ALL
```

> [!NOTE]
> You can use dependency check arguments based on your requirements. These arguments allow you to customize the behavior of the tool according to your project's needs. They can be used to control aspects such as output format, updating data feeds, etc. You can find detailed information by visiting the following link: [Dependency-Check Arguments](https://jeremylong.github.io/DependencyCheck/dependency-check-cli/arguments.html).

### 4. Verification

* Navigate to the build artifacts or workspace. Locate the generated Dependency-Check reports in the `target` folder. They are typically available in multiple formats (JSON, HTML, XML). Ensure that vulnerabilities are correctly identified. If you configured multiple report formats , explore each format to understand the data presentation.


<img width="722" alt="Screenshot 2024-01-31 at 6 18 35 PM" src="https://github.com/avengers-p7/Documentation/assets/156056349/98a80636-753a-4cb6-b39e-5454472ada01">

***
## Dependency Suppression
* Suppression of a vulnerability in a dependency is typically done when you have assessed the specific context of your application and determined that a reported vulnerability doesn't pose a significant risk in your particular scenario.

Here's a step-by-step guide on how to suppress a vulnerability using the OWASP Dependency-Check tool:

**Step 1: Locate the Vulnerability** - Identify the specific vulnerability in your project by running the Dependency-Check tool. The tool will generate a report highlighting vulnerabilities in your dependencies.

**Step 2: Create a Suppression XML File** - Create a suppression XML file adhering to the OWASP Dependency-Check guidelines. This XML file will define which vulnerabilities should be ignored during subsequent scans. The file name can be anything (eg., `suppression.xml`, `dependency-suppression.xml`)

*Example dependency-suppression.xml:*

```xml
<?xml version="1.0" encoding="UTF-8"?>
<suppressions xmlns="https://jeremylong.github.io/DependencyCheck/dependency-suppression.1.3.xsd">
    <suppress>
        <notes>Suppress vulnerabilities for h2-2.2.224.jar</notes>
        <gav>com.h2database:h2:2.2.224</gav>
        <cpe>CPE:/a:h2database:h2:2.2.224</cpe>
        <cve>CVE-2018-14335</cve>
    </suppress>
</suppressions>
```

**Step 3: Save the Suppression File** - Save the suppression XML file in a location accessible to your project.

**Step 4: Add Configuration to pom.xml**
* Open your project's pom.xml file and locate the <plugins> section. Add the following configuration for the dependency-check-maven plugin:

```xml
            <plugin>
                <groupId>org.owasp</groupId>
                <artifactId>dependency-check-maven</artifactId>
                <version>9.0.9</version>
                <configuration>
                    <suppressionFile>/path/to/dependency-suppression.xml</suppressionFile>
                </configuration>
                <executions>
                    <execution>
                        <goals>
                            <goal>check</goal>
                        </goals>
                    </execution>
                </executions>
            </plugin>

```

* Replace /path/to/dependency-suppression.xml with the actual path to your suppression file.

**Step 5: Execute Dependency-Check** - Rerun the Dependency-Check tool as part of your Maven build. The suppression file will be automatically included, and the specified vulnerabilities will be ignored.

**Step 6: Confirm Suppression** - Review the Dependency-Check report to ensure that the suppressed vulnerability no longer appears in the list of identified security issues.

*Example Output:* 

* In the example screenshot, the vulnerability associated with h2-2.2.224.jar has been successfully excluded. This exclusion is achieved by adding a suppression entry in the dependency-suppression.xml file.


<img width="955" alt="Screenshot 2024-02-01 at 6 53 06 PM" src="https://github.com/avengers-p7/Documentation/assets/156056349/2c5c51c7-fc33-4a15-a371-5dde36316cad">

***
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
| Dependency-Check User Guide           | https://jeremylong.github.io/DependencyCheck/    |
| OWASP Dependency-Check GitHub Repository    | https://github.com/jeremylong/DependencyCheck  |



