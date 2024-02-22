## Scripted Pipeline GoLang Dependency Scanning
![download](https://github.com/avengers-p7/Documentation/assets/156056570/a292f2dd-4795-4566-bfb6-014b634f76bf)

***

| Author | Created on | Last updated by | Last edited on |
|--------|------------|-----------------|----------------|
|Shikha Tripathi| 9-02-2024 | Shikha Tripathi | 9-02-2024|

***
## Table of Contents
+ [Introduction](#Introduction)
+ [Why Scripted Pipeline GoLang Dependency Scanning](#ScriptedPipelineGoLangDependencyScanning)
+ [Features](#Features)
+ [Jenkins Architecture](#JenkinsArchitecture)
+ [Advantages](#Advantages)
+ [Disadvantages](#Disadvantages)
+ [Jenkinsfile](#Jenkinsfile)
+ [Setup](#Setup)
+ [Conclusion](#Conclusion)
+ [Contact Information](#Contact-Information)
+ [Resources and References](#Resources-and-References)

***
## Introduction
This document outlines the integration of GoLang dependency scanning into a Jenkins scripted pipeline, crucial for identifying vulnerabilities. By automating this process, we enhance the security of our GoLang projects within CI/CD workflows. We'll explore using tools like GoSec and Trivy, discussing their benefits and how to implement them effectively. Let's streamline our security practices and safeguard our code with this scripted pipeline solution.

***
## Pre-requisites

| Tool   | Description                          | 
|--------|--------------------------------------|
| OWASP ZAP | A tool for bug analysis in Python | 
| Jenkins | CICD Tool                          |  
| JAVA   |
***
## Why Scripted Pipeline GoLang Dependency Scanning
| Benefits | Explanation |
|----------|-------------|
| **Early Detection of Vulnerabilities**|	Dependency scanning identifies security vulnerabilities in third-party dependencies early, aiding prompt remediation.|
| **Continuous Security Monitoring**| Scanning integrated into pipelines ensures consistent security checks with every build, offering ongoing protection.|
| **Reduced Risk of Exploitation**| Proactively addressing vulnerabilities lowers the risk of exploitation by malicious entities, safeguarding data.|
| **Compliance Requirements** |	Meeting regulatory standards necessitates thorough security measures, easily achievable through scripted pipelines.|
| **Streamlined Development Processes**	| Automation in scripted pipelines optimizes efficiency by seamlessly integrating security practices into workflows.|

***
## Features
| Feature |	Description |
|---------|-------------|
| **Integration with GoLang Tools**	| Seamlessly integrates with popular GoLang dependency scanning tools like GoSec and Trivy.|
| **Customizable Configuration** |	Offers flexibility to tailor the scanning process according to project requirements. |
| **Automated Security Checks**	| Automates the scanning process within CI/CD pipelines, ensuring consistent security validation with each build.|
|**Early Vulnerability Detection**|	Enables early identification of vulnerabilities in third-party dependencies, facilitating prompt remediation.|
| **Compliance Support** |	Facilitates compliance with regulatory standards by implementing thorough security measures.|
| **Streamlined Workflow** |	Enhances efficiency by integrating security practices into development workflows without compromising speed or reliability.|
| **Archiving Scan Results** | Archives scan reports for traceability and auditing purposes, facilitating post-analysis and compliance documentation.|
| **Continuous Monitoring**	| Provides ongoing protection against emerging threats through continuous security monitoring.|
| **Reduced Risk** | Mitigates the risk of exploitation by malicious actors, safeguarding sensitive data and maintaining user trust.|
| **Comprehensive Security** |	Offers comprehensive scanning capabilities to identify and address a wide range of vulnerabilities in GoLang dependencies.|

***
## Jenkins Architecture
![image](https://github.com/avengers-p7/Documentation/assets/156056746/85be06bb-b800-4844-b4d3-7389506e1918)
**Note**: Jenkins follows a master-slave architecture, with the master coordinating tasks and distributing them to one or more slave nodes for execution. Plugins extend its functionality, enabling integration with various tools and systems. Jobs, defined tasks or processes, are executed based on triggers such as code commits or time schedules. The master manages the web interface and schedules builds, while slaves execute build tasks on different environments. Jenkins' architecture facilitates scalable and distributed automation in continuous integration and delivery pipelines.

***
## Advantages
| Advantages |	Explanation |
|------------|--------------|
| **Early Identification of Vulnerabilities** |	Enables the detection of security vulnerabilities in third-party dependencies early in the development process, allowing for prompt remediation.|
| **Continuous Security Monitoring** |	Integrating scanning into CI/CD pipelines ensures that security checks are performed consistently with every build, providing ongoing protection.|
| **Compliance with Regulatory Standards** |	Facilitates compliance with regulatory standards by implementing thorough security measures, helping organizations meet legal and industry requirements.|
| **Enhanced Development Efficiency**	| Streamlines development workflows by automating security practices within the pipeline, optimizing efficiency without compromising speed or reliability.|
| **Customizable Configuration**|	Offers flexibility to tailor the scanning process according to project requirements, allowing for customized security checks and configurations.|
| **Comprehensive Security Coverage**	| Provides comprehensive scanning capabilities to identify and address a wide range of vulnerabilities in GoLang dependencies, ensuring robust security.|
| **Reduced Risk of Exploitation**	| Proactively addressing vulnerabilities mitigates the risk of exploitation by malicious actors, safeguarding sensitive data and user trust.|

***
## Disadvantages
| Disadvantages	| Explanation |
|---------------|-------------|
| **Complexity** |	Scripted pipelines may require advanced Groovy scripting knowledge, potentially increasing complexity and maintenance overhead.|
| **Resource Intensive**|	Depending on the size of the project and scanning tool used, dependency scanning may consume additional computational resources and time.|
| **Tool Dependencies** |	Integration with external scanning tools like GoSec or Trivy requires managing dependencies and ensuring availability within the Jenkins environment.|
| **Learning Curve** |	Users unfamiliar with Groovy scripting or Jenkins pipeline syntax may face a learning curve when implementing scripted pipelines.
| **Potential Overhead**|	Continuous scanning within CI/CD pipelines may introduce overhead, impacting build times and resource utilization, especially in large-scale projects.|

***
## Jenkins
    node {
    // Define environment variable
    def DEP_CHECK_VERSION = '9.0.9'

    // Stage: Install JDK
    stage('Install JDK') {
        sh 'sudo apt update && sudo apt install -y openjdk-17-jdk'
    }

    // Stage: Download Dependency Check
    stage('Download Dependency Check') {
        sh "wget -q https://github.com/jeremylong/DependencyCheck/releases/download/v${DEP_CHECK_VERSION}/dependency-check-${DEP_CHECK_VERSION}-release.zip"
        sh "unzip -q dependency-check-${DEP_CHECK_VERSION}-release.zip"
    }

    // Stage: Clone Repository
    stage('Clone Repository') {
        git branch: 'main', credentialsId: 'tripathi-cred', url: 'https://github.com/OT-MICROSERVICES/employee-api.git/'
    }

    // Stage: Run Dependency Check
    stage('Run Dependency Check') {
        sh './dependency-check/bin/dependency-check.sh --scan /var/lib/jenkins/workspace/ --out dep-check.html'
    }

    // Stage: Clean workspace
    stage('Clean workspace') {
        sh "rm -rf dependency-check-${DEP_CHECK_VERSION}-release.zip"
        sh "rm -rf dependency-check"
    }
***  
## Create new pipeline task

![Screenshot from 2024-02-13 20-28-22](https://github.com/avengers-p7/Documentation/assets/156056746/b8595f14-32ae-4198-ab11-500e6736182a)

***
## Scroll down to pipeline section, we use pipeline script this time, script is shown as below.
![Screenshot from 2024-02-13 20-26-56](https://github.com/avengers-p7/Documentation/assets/156056746/561bdbff-8fb5-4b4b-afc9-a3a289fd8c3c)

***
## Build and check result
![Screenshot from 2024-02-21 23-30-58](https://github.com/avengers-p7/Documentation/assets/156056746/93a6451e-bec1-4f3b-afe9-e29282c0b461)


***
## Console OUtput
![Screenshot from 2024-02-21 23-31-22](https://github.com/avengers-p7/Documentation/assets/156056746/9bf0234b-3084-44f6-ba5a-40024d4d8323)


***

## Conclusion
In conclusion, integrating GoLang dependency scanning into scripted pipelines is essential for enhancing the security of CI/CD workflows. By automating security checks and offering customization options, these pipelines enable early vulnerability detection, compliance adherence, and streamlined development processes. Despite potential complexities, the benefits of comprehensive security coverage and reduced risk of exploitation outweigh the challenges, ensuring the integrity and reliability of GoLang projects.

***

## Contact Information

|     Name         | Email  |
| -----------------| ------------------------------------ |
| Shikha Tripathi   | shikha.tripathi.snaatak@mygurukulam.co |
***

## References

| Description                                   | References  
| --------------------------------------------  | -------------------------------------------------|
| Pipeline | https://docs.cloudbees.com/docs/cloudbees-ci/latest/pipeline-syntax-reference-guide/scripted-pipeline |
| GenericDoc | https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GenericDoc/jenkinsPipeline.md |

