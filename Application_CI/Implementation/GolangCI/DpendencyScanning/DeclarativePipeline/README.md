## Declarative Pipeline GoLang Dependency Scanning
![download](https://github.com/avengers-p7/Documentation/assets/156056570/a292f2dd-4795-4566-bfb6-014b634f76bf)
***
| Author | Created on | Last updated by | Last edited on |
|--------|------------|-----------------|----------------|
|Shikha Tripathi| 9-02-2024 | Shikha Tripathi | 9-02-2024|

***
## Table of Contents
+ [Introduction](#Introduction)
+ [Why Declarative Pipeline GoLang Dependency Scanning](#DeclarativePipelineGoLangDependencyScanning)
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
In modern software development, managing dependencies is crucial for code stability and security. This guide explores implementing a Jenkins Declarative Pipeline tailored for GoLang projects, automating dependency scanning to ensure robustness and reliability. By integrating this pipeline, teams can efficiently identify and mitigate dependency-related issues, enhancing code quality and project security seamlessly within their CI/CD workflow.
***
## Why Declarative Pipeline GoLang Dependency Scanning
| Feature	| Description |
|---------|-------------|
| **Automated Dependency Management** | Automates the process of scanning project dependencies within GoLang projects, eliminating the need for manual intervention and reducing the likelihood of errors.|
|**Early Issue Detection** | Enables early detection of dependency-related issues like outdated dependencies, vulnerabilities, or conflicts, allowing prompt resolution to prevent escalation.|
| **Code Quality Assurance**| Ensures that project dependencies meet specified quality standards, contributing to overall code quality and reducing technical debt.|
| **Enhanced Security Posture** | Identifies and mitigates potential security vulnerabilities within project dependencies, minimizing the risk of security breaches or exploits.|
| **Streamlined CI/CD Workflow**| Seamlessly integrates with Continuous Integration/Continuous Deployment (CI/CD) pipelines, making dependency scanning a fundamental part of the software delivery process.|
| **Efficient Resource Utilization** | Optimizes resource usage by automating dependency scanning tasks, freeing developers to focus on value-added activities like feature development and innovation.|
| **Compliance Requirements**| Supports compliance needs by offering an auditable trail of dependency scanning activities, facilitating regulatory compliance and industry standards adherence.|

***
## Pre-requisites

| Tool   | Description                          | 
|--------|--------------------------------------|
| OWASP ZAP | A tool for bug analysis in Python | 
| Jenkins | CICD Tool                          |  
| JAVA    |

***

## Features
| Feature |	Description |
|---------|-------------|
| **Automated Dependency Scanning** | Utilizes Jenkins Declarative Pipeline to automate the scanning of dependencies within GoLang projects.|
| **Integration with GoLang Tools**| Incorporates GoLang-specific tools and commands (e.g., go list) to analyze project dependencies effectively.|
| **Structured Pipeline Syntax**| Utilizes a structured syntax provided by Jenkins Declarative Pipeline for clear definition and readability.|
| **Built-in Stage Definitions**| Provides built-in stages (stages, steps, post) for defining the different stages of the dependency scanning process.|
|**Error Handling Mechanisms** | Implements error handling mechanisms to gracefully manage failures during dependency scanning execution.|

***
## Jenkins Architecture
![image](https://github.com/avengers-p7/Documentation/assets/156056746/85be06bb-b800-4844-b4d3-7389506e1918)
**Note**: Jenkins follows a master-slave architecture, with the master coordinating tasks and distributing them to one or more slave nodes for execution. Plugins extend its functionality, enabling integration with various tools and systems. Jobs, defined tasks or processes, are executed based on triggers such as code commits or time schedules. The master manages the web interface and schedules builds, while slaves execute build tasks on different environments. Jenkins' architecture facilitates scalable and distributed automation in continuous integration and delivery pipelines.

***
### Here's the advantages and disadvantages of implementing a Declarative Pipeline for GoLang Dependency Scanning presented in a tabular form:
| Advantages | Disadvantages |
|------------|---------------|
| Simplified Syntax |	Limited Flexibility|
| Declarative pipelines offer a simpler syntax compared to scripted pipelines, making them easier to read, write, and maintain.| Declarative pipelines provide less flexibility compared to scripted pipelines, restricting the ability to implement complex custom logic.|
| Built-in Stages |	Limited Control |
| Declarative pipelines provide built-in stages (stages, steps, post), simplifying the definition of pipeline stages and steps.| May not be suitable for advanced use cases that require fine-grained control over pipeline execution, as declarative pipelines impose certain restrictions.|
| Enforced Best Practices |	Learning Curve |
| Declarative pipelines enforce best practices, ensuring consistent pipeline structure and quality across projects.| Developers may require time to familiarize themselves with the specific syntax and constraints of declarative pipelines, potentially increasing the learning curve.|
| Integration with Jenkins Ecosystem | Less Customization |
|  Integrates seamlessly with other Jenkins features and plugins, allowing for easy customization and extension.| Declarative pipelines offer less customization compared to scripted pipelines, limiting the ability to implement complex or unconventional workflows.|
| Improved Readability and Maintainability | Potentially Bloated Configuration |
| Declarative pipelines promote improved readability and maintainability due to their structured syntax and predefined stages.| Declarative pipelines may result in bloated configuration files for complex pipelines, making them harder to manage and understand.|

***
## Jenkinsfile
    pipeline {
    agent any
    
    
    
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/OT-MICROSERVICES/employee-api.git/'
            }
        }
        
        
        
        stage('Publish Dependency Check Report') {
            steps {
                publishHTML(target: [
                    allowMissing: false,
                    alwaysLinkToLastBuild: false,
                    keepAll: true,
                    reportDir: '',
                    reportFiles: 'dep-check.html',
                    reportName: 'Dependency Check Report'
                ])
            }
        }
    }
}
## Create new pipeline task
![image](https://github.com/avengers-p7/Documentation/assets/156056746/e06ca324-4a6f-45d2-84b8-a2856a089662)

***
## Scroll down to pipeline section, we use pipeline script this time, script is shown as below.

![Screenshot from 2024-02-09 15-18-18](https://github.com/avengers-p7/Documentation/assets/156056746/5e9629b5-d600-4cfd-9f20-fd83a67a375c)

***
## Build and check result

![Screenshot from 2024-02-09 15-18-01](https://github.com/avengers-p7/Documentation/assets/156056746/1abc53d7-0fa7-41c1-affe-e8264ed5a54c)

***


## Console Output
![image](https://github.com/avengers-p7/Documentation/assets/156056746/4ebb4c28-a52e-4bcf-bbab-b66cb8f5defe)

***



## Conclusion
In conclusion, implementing a Declarative Pipeline for GoLang Dependency Scanning automates dependency management, enhances code quality, and strengthens security posture. This approach fosters a streamlined CI/CD workflow, optimizing resource utilization and ensuring compliance with industry standards. By proactively addressing potential issues, teams can deliver high-quality software with confidence, promoting reliability and resilience in their projects.

***
## Contact Information

|     Name         | Email  |
| -----------------| ------------------------------------ |
| Shikha Tripathi   | shikha.tripathi.snaatak@mygurukulam.co |
***

## References

| Description                                   | References  
| --------------------------------------------  | -------------------------------------------------|
| Pipeline | https://docs.cloudbees.com/docs/cloudbees-ci/latest/pipeline-syntax-reference-guide/declarative-pipeline |
| GenericDoc | https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GenericDoc/jenkinsPipeline.md |
