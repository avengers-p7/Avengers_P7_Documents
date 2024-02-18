# Scripted Pipeline : Credential Scanning



|   Author        |  Created on   |  Version   | Last updated by  | Last edited on |
| --------------- | --------------| -----------|----------------- | -------------- |
| Aakash Tripathi |  16-02-2024  |  Version 1 | Aakash  | 18-02-2024    |

***
## Table of Contents
+ [Introduction](#Introduction)
+ [Why Scripted Pipeline](#Why-Scripted-Pipeline)
+ [Flow Diagram](#Flow-Diagram)
+ [Pre-requisites](#Pre-requisites)
+ [Setup of Credential Scanning](#Setup-of-Credential-Scanning)
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
![Screenshot 2024-02-18 204835](https://github.com/avengers-p7/Documentation/assets/156056344/8c5132c8-1901-4900-a222-18bd8109b8b3)



***
## Pre-requisites
| **Pre-requisites** | **Version** |
| ------------------ | ----------- |
| Jenkins | 2.426.3 | 
| Gitleaks | 8.18.2 |

***
## Setup of Credential Scanning
* Follow this document for Setup [**Cilck here**](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GenericDoc/pipelinePOC.md)

![Screenshot 2024-02-18 213920](https://github.com/avengers-p7/Documentation/assets/156056344/95d8501d-c3ee-4046-a0f2-6e37b25a32aa)

* Build

![Screenshot 2024-02-18 211446](https://github.com/avengers-p7/Documentation/assets/156056344/931233c3-be7e-4eba-b588-436e78506d1a)



* Console Output:
 ![Screenshot 2024-02-18 211523](https://github.com/avengers-p7/Documentation/assets/156056344/8153087f-4683-47af-b9cf-0bb6353e50e9)



> [!NOTE]
> **Changes**
> *  **Pipeline name**       **-**  `Credential Scanning Scripted Pipeline`
> *  **Jenkinsfile Path**    **-**  `Scripted Pipeline/Credential Scanning/Jenkinsfile`  
![Screenshot 2024-02-18 214637](https://github.com/avengers-p7/Documentation/assets/156056344/4812f753-2287-425a-a1c5-0a1dc39b85af)

***

## JSON Report
![Screenshot 2024-02-18 211504](https://github.com/avengers-p7/Documentation/assets/156056344/840a0512-10b8-40b5-bd89-3cbdd3b02c03)


 * Cilck [**here**](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/Credential%20Scanning/Declarative%20Pipeline/credScanReport)

***
## Jenkinsfile
  * [**Jenkinsfie**](https://github.com/CodeOps-Hub/Jenkinsfile/blob/main/Scripted%20Pipeline/Credential%20Scanning/Jenkinsfile)
  ```shell 
node {
    // Checkout SCM
    stage('Checkout SCM') {
        git branch: 'main', url: 'https://github.com/OT-MICROSERVICES/employee-api.git'
    }

    // Download and Install Gitleaks
    stage('Download and Install Gitleaks') {
        sh 'wget https://github.com/gitleaks/gitleaks/releases/download/v8.18.2/gitleaks_8.18.2_linux_x64.tar.gz'
        sh 'tar xvzf gitleaks_8.18.2_linux_x64.tar.gz'
    }

    // Gitleaks Scan
    stage('Gitleaks Scan') {
         try {
            sh './gitleaks detect -r credScanReport'
        } catch (Exception e) {
            echo "Gitleaks scan failed. Archiving report."
            archiveArtifacts artifacts: 'credScanReport', allowEmptyArchive: true
            error 'Gitleaks scan failed'
        }
    }

    // Post-build actions
    cleanWs()

}
```
***
## Conclusion

Scripted Pipeline is a powerful and flexible way to define Jenkins pipelines using Groovy scripting language. It's suitable for environments and use cases that require fine-grained control, advanced automation, and integration capabilities. However, it also requires a deeper understanding of programming concepts and may entail additional complexity in debugging and maintenance compared to Declarative Pipeline.

***
## Contact Information
| Name | Email address |
| ---- | ------------- |
| Aakash Tripathi | aakash.tripathi.snaatak@mygurukulam.co |
***
## Resources and References
|  **Description** |   **Source** |
| ---------------- | ------------ |
| About Jenkins Pipeline (Generic Document) | [Link](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GenericDoc/jenkinsPipeline.md  ) |
| Credential Scanning POC Steps | [Link](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/02-%20Generic%20CI%20operation/Credentials%20Scanning/Credential%20Scanning%20via%20GitLeaks%20POC.md) |
| POC Generic Document | [Link](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GenericDoc/pipelinePOC.md) |
| Setup Jenkins | [Link](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GolangCI/Bug%20Analysis/Declarative%20Pipeline/Readme.md#Setup) |
| Jenkinsfile | [Link](https://github.com/avengers-p7/Jenkinsfile/blob/main/Declarative%20Pipeline/Python/Dependency_Scanning/Jenkinsfile) |
| Scripted vs Declarative Pipelines | [Link](https://www.baeldung.com/ops/jenkins-scripted-vs-declarative-pipelines) |
| Credential Scanning| [Link](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/02-%20Generic%20CI%20operation/Credentials%20Scanning/README.md) |

***


