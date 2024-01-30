# Dependency Scanning 

|   Authors        |  Created on   |  Version   | Last updated by | Last edited on |
| -----------------| --------------| -----------|---------------- | -------------- |
| Vidhi Yadav      | 25 Jan 2024   |     v1     | Vidhi Yadav     | 29 Jan 2024    |

***
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

***
## Introduction

* Dependency scanning is a process used in software development to identify and analyze the external dependencies or third-party components that a project relies on. These dependencies can include libraries, frameworks, modules, packages, or other code modules that are utilized to build and run the software. 

* The scanning process is typically automated and integrated into the development workflow, often as part of continuous integration or continuous delivery (CI/CD) pipelines. It serves as a crucial post-build process examines the project's dependencies to identify any known vulnerabilities, outdated versions, or security issues.

*** 
## Key Points

* **Automated Security Checks** - Dependency check facilitates the automated detection of vulnerabilities within project dependencies, seamlessly integrating this crucial security check into CI/CD pipelines.
  
* **Efficiency and Accuracy** - It reduces the need for manual effort, significantly improving accuracy and efficiency compared to traditional manual checks.
  
* **Awareness and Reporting** - Developers gain awareness of potential vulnerabilities through reports at an early stage, providing insights into the identified issues and their respective severity levels.

***
## Popular Tools

Explore a variety of widely used tools for scanning dependencies and enhancing the security of your projects. These tools can be integrated into Jenkins or used independently, providing diverse options for identifying and addressing vulnerabilities:

| Tool                  | Description                                                                                                    |
|---------------------------|----------------------------------------------------------------------------------------------------------------|
| [OWASP Dependency-Check](https://jeremylong.github.io/DependencyCheck/) | OWASP Dependency-Check is a mature and widely adopted tool that identifies project dependencies and checks if there are any known, publicly disclosed vulnerabilities.    |
| [Synk](https://snyk.io/)  | Synk is a comprehensive security platform that helps developers find and fix vulnerabilities in open-source libraries. It provides insights into dependencies, container images, and infrastructure as code. |
| [Retire.js](https://retirejs.github.io/retire.js/) | Retire.js is a tool for detecting vulnerable JavaScript libraries. It can be used as a command-line tool or integrated into various build tools. |
| [Bundler Audit](https://github.com/rubysec/bundler-audit#readme) | Bundler Audit is a tool for checking RubyGem dependencies for known security vulnerabilities. It integrates with Ruby projects using Bundler and can be utilized in Jenkins for secure Ruby application development. |

***
## Why Choose OWASP

OWASP Dependency-Check stands out as a robust and widely adopted tool for identifying vulnerabilities in project dependencies. Here are key reasons to consider using OWASP Dependency-Check in your CI/CD pipeline:

1. **Identification of Vulnerabilities** - OWASP Dependency-Check utlizes a combination of public and private vulnerability databases to identify known vulnerabilities in project dependencies, ensuring a thorough security assessment.
   
2. **Integration with Build Tools** - It seamlessly integrates into the project's build process, enabling developers to effortlessly incorporate regular vulnerability checks as part of their development workflow. It offers compatibility with popular build tools like Maven, Gradle, Ant, and others.
   
3. **Versatile Language and Ecosystem Support** - With support for multiple programming languages and ecosystems including Java, .NET, Node.js, Ruby, Python, and more, OWASP Dependency-Check proves to be versatile and adaptable, catering to a diverse range of projects.
   
4. **Flexible Report Generation** - The tool provides flexibility in report generation, offering outputs in various formats such as HTML, XML, JSON, and CSV. These detailed reports empower developers and security teams with comprehensive information about identified vulnerabilities, facilitating prompt and informed decision-making.
   
5. **Active and Collaborative Community** - OWASP thrives on an active and collaborative community. This community-driven approach ensures continuous updates, improvements, and the introduction of new features, enhancing the tool's effectiveness and relevance.
    
6. **Integration with Security Tools** - It can be seamlessly combined with other security tools to deliver a holistic security analysis of a project. This collaborative approach enhances the overall security posture and provides a more comprehensive understanding of potential risks.
  
***
## OWASP Installation

### 1. Pre-requisite

**Internet Access to retreive NVD Data**

* The NVD is a comprehensive source of vulnerability information. Dependency-Check can use this data to identify known vulnerabilities in your project's dependencies. It can be configured to fetch data from the NVD's Common Vulnerabilities and Exposures (CVE) database during the analysis process. This helps ensure that the tool has up-to-date information about known vulnerabilities. 

* If your environment does not have internet access or if there are restrictions on accessing external resources, Dependency-Check may still function, but it won't be able to fetch the latest vulnerability data from the NVD.

### 2. Installation

* OWASP Dependency-Check is a standalone tool, and it doesn't have additional prerequisites for its core functionality. You can download the Dependency-Check tool plugin in jenkins without requiring any specific plugins or additional installations.

* In your Jenkins dashboard, navigate to `Manage Jenkins` -> `Manage Plugins` Search for `OWASP Dependency-Check` in the available plugins and install it.

<img width="1334" alt="Screenshot 2024-01-30 at 1 49 04 PM" src="https://github.com/avengers-p7/Documentation/assets/156056349/7cee9449-7b7c-40e7-9bc1-08f20fc041f9">


### 3. Configuration

To set up the configuration, navigate to `tools` in `Manage Jenkins` and select `Dependency-Check Installations`. Within this section, opt for the option to install from GitHub.com. Next, pick the desired version, preferably the latest one available.

<img width="1317" alt="Screenshot 2024-01-30 at 2 00 59 PM" src="https://github.com/avengers-p7/Documentation/assets/156056349/f2936822-ff27-4e3c-b1cb-fede4d066d65">

***


> Note: You can use dependency check arguments based on your requirements. These arguments allow you to customize the behavior of the tool according to your project's needs. You might use these arguments to control aspects such as output format, suppression of vulnerabilities, updating data feeds, etc. You can find detailed information by visiting the following link: [Dependency-Check Arguments](https://jeremylong.github.io/DependencyCheck/dependency-check-cli/arguments.html)."

<img width="1407" alt="Screenshot 2024-01-31 at 12 15 51 AM" src="https://github.com/avengers-p7/Documentation/assets/156056349/ef2fe711-3add-4462-bade-d7fc4d3cfe40">

* You may use `Dependency-Check Publisher`, configured as a post-build action, independently processes the 'dependency-check-report.xml' file. It generates metrics, trends, and findings, with the ability to set configurable thresholds. This includes the option to mark the build as failed or in a warning state based on specified criteria.

<img width="1358" alt="Screenshot 2024-01-31 at 12 32 38 AM" src="https://github.com/avengers-p7/Documentation/assets/156056349/7b65ba1c-f4b5-4097-95a0-2584f33702ad">


### 2. Verification

* Initiate the job in Jenkins that includes the OWASP Dependency-Check configuration. Monitor the console output and review results

<img width="1317" alt="Screenshot 2024-01-30 at 3 06 06 PM" src="https://github.com/avengers-p7/Documentation/assets/156056349/3c14c164-faa7-4b28-b43d-3d4c063fb156">

* Navigate to the job's build artifacts or workspace. Locate the generated Dependency-Check reports. They are typically available in multiple formats (JSON, HTML, XML). 

<img width="1128" alt="Screenshot 2024-01-31 at 12 45 22 AM" src="https://github.com/avengers-p7/Documentation/assets/156056349/d5a23677-4118-4c4e-b03d-2bfd8894e00f">

* Open the reports in your preferred format and verify the content. Ensure that vulnerabilities are correctly identified, and severity levels align with expectations. If you configured multiple report formats , explore each format to understand the data presentation.

<img width="870" alt="Screenshot 2024-01-31 at 12 49 25 AM" src="https://github.com/avengers-p7/Documentation/assets/156056349/ae18d45c-af46-43ec-ab00-e2a9d28a058b">

<img width="1073" alt="Screenshot 2024-01-31 at 12 50 53 AM" src="https://github.com/avengers-p7/Documentation/assets/156056349/ee6596ef-bc8a-428a-bdf1-7957dd2b90ce">

***
## Best Practices

1. **Regular Scanning Frequency** - Regular scanning of project dependencies is essential for maintaining a secure development environment. Conduct dependency scans at key points in the development lifecycle, such as during the build process, before major releases, and after significant changes.
   
2. **Integration with Other Security Tools** - Enhance the effectiveness of your security strategy by integrating OWASP Dependency-Check with other security tools. This synergistic approach provides a more comprehensive security analysis. (eg, DAST , Container security )
   
3. **Handling False Positives** - False positives in dependency scanning results can occasionally occur. Here's how to handle them effectively. Leverage Dependency-Check's suppression mechanism to manage false positives, ensuring accurate reporting and engage with the Dependency-Check community to share and verify findings, improving the accuracy of future scans.

***
## Security and Compliance

1. **Security Measures**  - Set appropriate vulnerability thresholds to trigger alerts or fail the build based on severity levels.
  
2. **Compliance Standards** - Identify and understand compliance standards relevant to your industry and project.
   
3. **Continuous Monitoring** - Implement tools and processes for automated monitoring of dependencies to ensure ongoing compliance. You may also conduct periodic audits to review and validate compliance measures, making adjustments as necessary.

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
| OWASP Dependency-Check benefits                 | https://medium.com/@sudheer.barakers/integrate-owasp-dependency-check-in-jenkins-pipeline-748d8aefc2b7 |
| Installation                                 | https://www.youtube.com/watch?v=bImOWD4b6o8 |




