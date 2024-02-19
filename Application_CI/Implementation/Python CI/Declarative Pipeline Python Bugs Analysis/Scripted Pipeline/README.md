# Scripted Pipeline Python Bugs Analysis

![download](https://github.com/avengers-p7/Documentation/assets/156056570/983714ea-4f87-4c76-821a-a3af2af48291)


|   Author        |  Created on   |  Version   | Last updated by  | Last edited on |
| --------------- | --------------| -----------|----------------- | -------------- |
| Samir Kesare |  12-02-2024  |  Version 1 | Samir  | 13-02-2024    |

***
## Table of Contents
+ [Introduction](#Introduction)
+ [Why Scripted Pipeline](#Why-Scripted-Pipeline)
+ [Flow Diagram](#Flow-Diagram)
+ [Pre-requisites](#Pre-requisites)
+ [Setup](#Setup)
+ [Jenkinsfile](#Jenkinsfile)
+ [Conclusion](#Conclusion)
+ [Contact Information](#Contact-Information)
+ [Resources and References](#Resources-and-References)
  
***
## Introduction

Scripted Pipeline in Jenkins allows users to define CI/CD pipelines using Groovy scripting language, offering flexibility and customization for defining complex workflows. It provides an imperative, programmatic approach where users write scripts executed sequentially by Jenkins, with direct access to Jenkins APIs for advanced automation and integration. Scripted Pipelines are suitable for environments requiring fine-grained control over pipeline execution and the ability to define pipelines as code.* Cilck [**here**](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GenericDoc/jenkinsPipeline.md)

***
## Why Scripted Pipeline

| Aspect                    | Description                                                                                                                                                       |
|---------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Imperative Syntax**        | Write pipelines as Groovy scripts, providing full control over execution flow for complex logic and dynamic behavior.                                           |
| **Programmatic Constructs**  | Access to programming features like loops, conditions, variables, and functions for building highly customizable pipelines.                                       |
| **Direct Access to APIs**    | Scripts directly interact with Jenkins APIs, enabling fine-grained automation and integration with plugins and external systems.                                 |
| **Extensibility**            | Allows for defining custom functions and importing external libraries to enhance pipeline functionality and reusability.                                          |
| **Legacy Support**           | Widely used in environments with existing pipelines, providing familiarity and compatibility with legacy systems.                                               |
| **Learning Curve**           | Requires understanding of Groovy syntax and Jenkins pipeline concepts, posing a steeper learning curve, especially for newcomers.                                |
| **Debugging and Maintenance** | Imperative nature can make debugging and maintenance challenging, necessitating proper organization, documentation, and testing practices.                     |



***
## Flow Diagram

![image](https://github.com/avengers-p7/Documentation/assets/156056570/154a0883-c728-429b-a1c7-c8d7be8290f4)

***
## Pre-requisites

| Tool   | Description                          | Python3 Support | Purpose        |
|--------|--------------------------------------|-----------------|----------------|
| Bandit | A tool for bug analysis in Python   | Yes             | Python App     |
| Jenkins | CICD Tool                          |                |              |
***
## Setup

### Configure Pipeline Script:

* In the job configuration page, scroll down to the Pipeline section.
* Select Pipeline script from SCM.
* Give required repo url and enter your credentials.

![image](https://github.com/avengers-p7/Documentation/assets/156056570/09e9bce8-3572-4bc9-bc56-5d75419bd6c9)

### Build the Pipeline and View Build Console Output:

* Once the pipeline configuration is saved, you can manually trigger the build by clicking on Build Now.
* After triggering the build, you can view the progress and console output of the build by clicking on the build number in the Jenkins dashboard.
* The console output will display the steps executed by the pipeline script, including code checkout and compilation.

![Screenshot 2024-02-07 185756](https://github.com/avengers-p7/Documentation/assets/156056570/a6de0626-5387-4391-ac4f-a87656bf15a0)

![Screenshot 2024-02-07 190504](https://github.com/avengers-p7/Documentation/assets/156056570/ed038dff-efa7-4d5a-bc02-2b1d66ffe196)

![image](https://github.com/avengers-p7/Documentation/assets/156056570/c5bbf8b8-c131-4b8b-bac0-31d39399899f)


### JSON Report

* Cilck [**here**](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/Python%20CI/Declarative%20Pipeline%20Python%20Bugs%20Analysis/Declarative%20Pipeline/JSON%20Report)

***
## Jenkinsfile
```shell
node {
    // Define environment variables
    def REPO_URL = 'https://github.com/OT-MICROSERVICES/attendance-api.git'
    
    // Checkout code repository
    checkout([$class: 'GitSCM', branches: [[name: '*/main']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: REPO_URL]]])
    
    // Install necessary dependencies
    sh 'python3 -m venv myenv'
    sh '. myenv/bin/activate'

    // Clean workspace
    cleanWs()

    // Run bugs analysis with Bandit
    try {
        // Ensure Bandit is installed and run the analysis
        sh 'bandit --version' // Check Bandit version to ensure it's installed
        sh 'bandit -r . -f json -o bandit_report.json'
    } catch (Exception e) {
        echo "Bugs analysis failed: ${e.message}"
    }

    // Publish Bandit report as post-build action
    publishHTML(target: [
        allowMissing: false,
        alwaysLinkToLastBuild: true,
        keepAll: true,
        reportDir: '.',
        reportFiles: 'bandit_report.json',
        reportName: 'Bandit Security Report'
    ])
}

```

***
## Conclusion

Scripted Pipeline is a powerful and flexible way to define Jenkins pipelines using Groovy scripting language. It's suitable for environments and use cases that require fine-grained control, advanced automation, and integration capabilities. However, it also requires a deeper understanding of programming concepts and may entail additional complexity in debugging and maintenance compared to Declarative Pipeline.

***
## Contact Information

| Name | Email address |
| ---- | ------------- |
| Samir Kesare | samir.kesare.snaatak@mygurukulam.co |

***
## Resources and References

|  **Description** |   **Source** |
| ---------------- | ------------ |
| About Jenkins Pipeline (Generic Document) | [Link](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GenericDoc/jenkinsPipeline.md  ) |
| Jenkinsfile | [Link](https://github.com/avengers-p7/Jenkinsfile/blob/main/Declarative%20Pipeline/golang/Bug%20Analysis/Jenkinsfile) |
| Scripted vs Declarative Pipelines | [Link](https://www.baeldung.com/ops/jenkins-scripted-vs-declarative-pipelines) |
| Bug Analysis Introduction | [Link](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/05-%20GoLang%20CI%20Checks/Bug%20Analysis/Introduction%20of%20Bugs%20analysis%20(GoLang%20CI%20Checks).md#resources-and-references) |
