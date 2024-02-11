# Scripted Pipeline Python CI Depedency Scanning

  <img width="360" length="100" alt="Python" src="https://github.com/avengers-p7/Documentation/assets/156056413/ffb4fd31-eda0-4587-8774-2f694cddfec6"> 

|   Author        |  Created on   |  Version   | Last updated by  | Last edited on |
| --------------- | --------------| -----------|----------------- | -------------- |
| Vishal Kumar Kesarwani |  10-02-2024  |  Version 1 | Vishal  | 10-02-2024    |

***
## Table of Contents
+ [Introduction](#Introduction)
+ [Why Scripted Pipeline](#Why-Scripted-Pipeline)
+ [Flow Diagram](#Flow-Diagram)
+ [Pre-requisites](#Pre-requisites)
+ [Setup of Dependency Scanning](#Setup-of-Dependency-Scanning)
+ [Jenkinsfile](#Jenkinsfile)
+ [Conclusion](#Conclusion)
+ [Contact Information](#Contact-Information)
+ [Resources and References](#Resources-and-References)
  
***
## Introduction

Scripted Pipeline in Jenkins allows users to define CI/CD pipelines using Groovy scripting language, offering flexibility and customization for defining complex workflows. It provides an imperative, programmatic approach where users write scripts executed sequentially by Jenkins, with direct access to Jenkins APIs for advanced automation and integration. Scripted Pipelines are suitable for environments requiring fine-grained control over pipeline execution and the ability to define pipelines as code.

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
| **Debugging and Maintenance** | Imperative nature can make debugging and maintenance challenging, necessitating proper organization, documentation, and testing practices. |   

***
## Flow Diagram  
![Screenshot from 2024-02-11 00-12-01](https://github.com/avengers-p7/Documentation/assets/156056413/849778c6-5554-4bf3-96b8-9efccee52bc2)


***
## Pre-requisites
| **Pre-requisites** | **Version** |
| ------------------ | ----------- |
| Jenkins | 2.426.3 | 
| Java | 17 |
| OWASP Dependency-Check | 9.0.9 |

***
## Setup of Dependency Scanning
* Follow this document for Setup [**Cilck here**](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GolangCI/Bug%20Analysis/Declarative%20Pipeline/Readme.md#Setup)

  <img width="760" length="100" alt="Python" src="https://github.com/avengers-p7/Documentation/assets/156056413/891807cf-a73d-45dc-9a1b-70c49b9d2089"> 

* Console Output:

   <img width="760" length="100" alt="Python" src="https://github.com/avengers-p7/Documentation/assets/156056413/2ee8dc43-bab4-41a5-9e1b-448284ee4d00"> 


> [!NOTE]
> **Changes**
> *  **Pipeline name**       **-**  `Dependency_Scanning_(Python)_(Scripted)`
> *  **Jenkinsfile Path**    **-**  `Scripted Pipeline/Python/Dependency_Scanning`  

***

## HTML Report
 * Cilck [**here**](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/Python%20CI/Dependency_Scanning/Scripted_Pipeline/Report.html)

***
## Jenkinsfile
  * [**Jenkinsfie**](https://github.com/avengers-p7/Jenkinsfile/blob/main/Scripted%20Pipeline/Python/Dependency_Scanning/Jenkinsfile)
  ```shell
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
        git branch: 'main', credentialsId: 'vishal-cred', url: 'https://github.com/OT-MICROSERVICES/attendance-api.git'
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
}
```
***
## Conclusion

Scripted Pipeline is a powerful and flexible way to define Jenkins pipelines using Groovy scripting language. It's suitable for environments and use cases that require fine-grained control, advanced automation, and integration capabilities. However, it also requires a deeper understanding of programming concepts and may entail additional complexity in debugging and maintenance compared to Declarative Pipeline.

***
## Contact Information
| Name | Email address |
| ---- | ------------- |
| Vishal | vishal.kesarwani.snaatak@mygurukulam.co |
***
## Resources and References
|  **Description** |   **Source** |
| ---------------- | ------------ |
| About Jenkins Pipeline (Generic Document) | [Link](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GenericDoc/jenkinsPipeline.md  ) |
| Flow Step for create pipeline | [Link](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/04-%20Python%20CI%20Checks/Dependency%20Scanning/Dependency%20scanning(Python%20CI%20Checks).md) |
| POC Generic Document | [Link](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GenericDoc/pipelinePOC.md) |
| Setup Jenkins | [Link](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GolangCI/Bug%20Analysis/Declarative%20Pipeline/Readme.md#Setup) |
| Jenkinsfile | [Link](https://github.com/avengers-p7/Jenkinsfile/blob/main/Scripted%20Pipeline/Python/Dependency_Scanning/Jenkinsfile) |
| Scripted vs Declarative Pipelines | [Link](https://www.baeldung.com/ops/jenkins-scripted-vs-declarative-pipelines) |
| Dependency Scanning| [Link](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/04-%20Python%20CI%20Checks/Dependency%20Scanning/Dependency%20Scanning%20Introduction.md) |

***

