# Proof of Concept (POC) for Dependency-Check

## Table of Contents
+ [Introduction](#Introduction)
+ [Key Components](#key-points)
+ [Popular Tools](#popular-tools)
+ [Guide to Installation](#Installing-OWASP-Dependency-Check)
+ [Jenkins Job Configuration](#jenkins-job-setup)
+ [Best Practices](#best-practices)
+ [Security Compliance](#security-compliance)
+ [Contact Information](#contact-information)
+ [References](#references)

### 1. Pre-requisite

**1.1) Java**

* Ensure that you have Java installed on your system. The project requires Java version 17. If you don't have it installed, you can download and install it from the official Java website: [Java Downloads](https://www.oracle.com/java/technologies/downloads/) or use your preferred package manager.

<img width="785" alt="Screenshot 2024-01-31 at 5 04 51 PM" src="https://github.com/avengers-p7/Documentation/assets/156056349/c53fd0f0-8a0d-4e7f-95ce-dfe1da987713">

* Set the `JAVA_HOME` environment variable to the installation directory of your JDK. This variable is essential for Maven to locate the Java runtime.

<img width="920" alt="Screenshot 2024-01-31 at 5 20 14 PM" src="https://github.com/avengers-p7/Documentation/assets/156056349/a3767e84-aa45-4fb8-9168-15cec81cd15e">


**1.2) Maven**
* Make sure to have Maven installed on your system. It is a powerful tool used for managing project dependencies. If you don't have Maven installed, please follow the installation instructions for your operating system, which can be found on the official Apache Maven website: [Maven Installation Guide](https://maven.apache.org/install.html).

<img width="1001" alt="Screenshot 2024-01-31 at 5 13 59 PM" src="https://github.com/avengers-p7/Documentation/assets/156056349/f617c048-1754-4e6f-a011-c84d72db00c1">


**1.3) Internet Access to retreive NVD Data**

* The NVD is a comprehensive source of vulnerability information. Dependency-Check can use this data to identify known vulnerabilities in your project's dependencies. It can be configured to fetch data from the NVD's Common Vulnerabilities and Exposures (CVE) database during the analysis process. This helps ensure that the tool has up-to-date information about known vulnerabilities. 

* If your environment does not have internet access or if there are restrictions on accessing external resources, Dependency-Check may still function, but it won't be able to fetch the latest vulnerability data from the NVD.
  
### 2. Configuration

* To enable the `OWASP Dependency-Check` plugin in your Maven project, add the following configuration to your pom.xml file. Ensure this configuration is placed within the `<build>` section

<img width="832" alt="Screenshot 2024-01-31 at 5 35 00 PM" src="https://github.com/avengers-p7/Documentation/assets/156056349/039a152a-8a25-4fef-b012-c87171be6d37">

***

* To ensure compatibility and take advantage of the latest improvements, update the Maven Enforcer Plugin version to 3.6.3 in your project's pom.xml file. This change aligns the project with your system's Maven version.

<img width="847" alt="Screenshot 2024-01-31 at 5 45 54 PM" src="https://github.com/avengers-p7/Documentation/assets/156056349/37707338-8903-4145-8568-edd9f395ebcf">


### 3. Generate Reports

* This ensures a clean build of your project before checking for vulnerabilities, run the following Maven command to ensure a clean build:
```shell
mvn clean install
```

* To generate a comprehensive report for your project, run the following Maven command in your terminal:

```shell
mvn dependency-check:aggregate -Dformat=ALL -Dscan -Dname="OWASP DP Check"
```

> [!NOTE]
> You can use dependency check arguments based on your requirements. These arguments allow you to customize the behavior of the tool according to your project's needs. You might use these arguments to control aspects such as output format, updating data feeds, etc. You can find detailed information by visiting the following link: [Dependency-Check Arguments](https://jeremylong.github.io/DependencyCheck/dependency-check-cli/arguments.html)."

### 4. Verification

* Initiate the job in Jenkins that includes the OWASP Dependency-Check configuration. Monitor the console output and review results

<img width="1317" alt="Screenshot 2024-01-30 at 3 06 06 PM" src="https://github.com/avengers-p7/Documentation/assets/156056349/3c14c164-faa7-4b28-b43d-3d4c063fb156">

* Navigate to the build artifacts or workspace. Locate the generated Dependency-Check reports in the `target` folder. They are typically available in multiple formats (JSON, HTML, XML). 

* Open the reports in your preferred format and verify the content. Ensure that vulnerabilities are correctly identified, and severity levels align with expectations. If you configured multiple report formats , explore each format to understand the data presentation.

