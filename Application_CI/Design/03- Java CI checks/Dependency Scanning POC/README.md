# Proof of Concept (POC) for Dependency-Check

|   Authors        |  Created on   |  Version   | Last updated by | Last edited on |
| -----------------| --------------| -----------|---------------- | -------------- |
| Vidhi Yadav      | 25 Jan 2024   |     v1     | Vidhi Yadav     | 29 Jan 2024    |


## Table of Contents
+ [Introduction](#Introduction)
+ [OWASP](#owasp-dependency-check)
+ [Proof of Concept](#Pre-requisite)
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

* To ensure compatibility and take advantage of the latest improvements, update the Maven Enforcer Plugin version to 3.6.3 in your project's pom.xml file. This change aligns the project with your system's Maven version.

<img width="847" alt="Screenshot 2024-01-31 at 5 45 54 PM" src="https://github.com/avengers-p7/Documentation/assets/156056349/37707338-8903-4145-8568-edd9f395ebcf">


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
> You can use dependency check arguments based on your requirements. These arguments allow you to customize the behavior of the tool according to your project's needs. You might use these arguments to control aspects such as output format, updating data feeds, etc. You can find detailed information by visiting the following link: [Dependency-Check Arguments](https://jeremylong.github.io/DependencyCheck/dependency-check-cli/arguments.html).

### 4. Verification

* Navigate to the build artifacts or workspace. Locate the generated Dependency-Check reports in the `target` folder. They are typically available in multiple formats (JSON, HTML, XML). Ensure that vulnerabilities are correctly identified. If you configured multiple report formats , explore each format to understand the data presentation.


<img width="722" alt="Screenshot 2024-01-31 at 6 18 35 PM" src="https://github.com/avengers-p7/Documentation/assets/156056349/98a80636-753a-4cb6-b39e-5454472ada01">

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



