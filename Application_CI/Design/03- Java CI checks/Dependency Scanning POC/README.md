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

* **Internet Access to retreive NVD Data**

* The NVD is a comprehensive source of vulnerability information. Dependency-Check can use this data to identify known vulnerabilities in your project's dependencies. It can be configured to fetch data from the NVD's Common Vulnerabilities and Exposures (CVE) database during the analysis process. This helps ensure that the tool has up-to-date information about known vulnerabilities. 

* If your environment does not have internet access or if there are restrictions on accessing external resources, Dependency-Check may still function, but it won't be able to fetch the latest vulnerability data from the NVD.

### 2. Installation



### 3. Configuration

To set up the configuration, navigate to `tools` in `Manage Jenkins` and select `Dependency-Check Installations`. Within this section, opt for the option to install from GitHub.com. Next, pick the desired version, preferably the latest one available.

<img width="1317" alt="Screenshot 2024-01-30 at 2 00 59 PM" src="https://github.com/avengers-p7/Documentation/assets/156056349/f2936822-ff27-4e3c-b1cb-fede4d066d65">

***


> Note: You can use dependency check arguments based on your requirements. These arguments allow you to customize the behavior of the tool according to your project's needs. You might use these arguments to control aspects such as output format, updating data feeds, etc. You can find detailed information by visiting the following link: [Dependency-Check Arguments](https://jeremylong.github.io/DependencyCheck/dependency-check-cli/arguments.html)."


### 2. Verification

* Initiate the job in Jenkins that includes the OWASP Dependency-Check configuration. Monitor the console output and review results

<img width="1317" alt="Screenshot 2024-01-30 at 3 06 06 PM" src="https://github.com/avengers-p7/Documentation/assets/156056349/3c14c164-faa7-4b28-b43d-3d4c063fb156">

* Navigate to the build artifacts or workspace. Locate the generated Dependency-Check reports in the `target` folder. They are typically available in multiple formats (JSON, HTML, XML). 



* Open the reports in your preferred format and verify the content. Ensure that vulnerabilities are correctly identified, and severity levels align with expectations. If you configured multiple report formats , explore each format to understand the data presentation.

