# Scripted Pipeline : License Scanning



|   Author        |  Created on   |  Version   | Last updated by  | Last edited on |
| --------------- | --------------| -----------|----------------- | -------------- |
| Aakash Tripathi |  16-02-2024  |  Version 1 | Aakash  | 18-02-2024    |

***
## Table of Contents
+ [Introduction](#Introduction)
+ [Why Scripted Pipeline](#Why-Scripted-Pipeline)
+ [Flow Diagram](#Flow-Diagram)
+ [Pre-requisites](#Pre-requisites)
+ [Setup of License Scanning](#Setup-of-License-Scanning)
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
![Screenshot 2024-02-18 221207](https://github.com/avengers-p7/Documentation/assets/156056344/5c780442-e198-47d7-965d-4faa026db1e5)




***
## Pre-requisites
| **Pre-requisites** | **Version** |
| ------------------ | ----------- |
| Jenkins | 2.426.3 | 
| FOSSA CLI | 3.9.5 |

***
## Setup of License Scanning
* Follow this document for Setup [**Cilck here**](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GenericDoc/pipelinePOC.md)

![Screenshot 2024-02-18 213920](https://github.com/avengers-p7/Documentation/assets/156056344/95d8501d-c3ee-4046-a0f2-6e37b25a32aa)

* Build
![Screenshot 2024-02-18 230422](https://github.com/avengers-p7/Documentation/assets/156056344/c1f257f7-7c72-460e-b04b-0bdbfd2c137b)


* Console Output:
![Screenshot 2024-02-18 225809](https://github.com/avengers-p7/Documentation/assets/156056344/0422f193-3df8-4eb2-bd23-6986cf1bd1c5)



> [!NOTE]
> **Changes**
> *  **Pipeline name**       **-**  `License Scanning Scripted Pipeline`
> *  **Jenkinsfile Path**    **-**  `Scripted Pipeline/License Scanning/Jenkinsfile`  
![Screenshot 2024-02-18 230610](https://github.com/avengers-p7/Documentation/assets/156056344/24938ba3-af85-4f47-b897-ccc58a54b5f2)

***


## Jenkinsfile
  * [**Jenkinsfie**](https://github.com/CodeOps-Hub/Jenkinsfile/blob/main/Scripted%20Pipeline/Credential%20Scanning/Jenkinsfile)
  ```shell 
node {
    // Define repository URL and branch
    def repoUrl = 'https://github.com/OT-MICROSERVICES/employee-api.git'
    def branch = 'main'

    // Define FOSSA API key credential ID
    def fossaTokenCredentialId = 'fossaToken'

    // Checkout SCM
    stage('Checkout SCM') {
        git branch: branch, url: repoUrl
    }

    // Set FOSSA API key as environment variable
    withCredentials([string(credentialsId: fossaTokenCredentialId, variable: 'FOSSA_API_KEY')]) {
        // Download and Install FOSSA
        stage('Download and Install FOSSA') {
            sh 'curl -H \'Cache-Control: no-cache\' https://raw.githubusercontent.com/fossas/fossa-cli/master/install-latest.sh | bash'
        }

        // FOSSA Scan
        stage('FOSSA Scan') {
             try {
            sh 'fossa analyze'
            sh 'fossa test'
        } catch (Exception e) {
            echo "FOSSA Test failed. Review Your Code."
            cleanWs()
            error 'FOSSA scan failed'
        }
            
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
## Resources and References
|  **Description** |   **Source** |
| ---------------- | ------------ |
| About Jenkins Pipeline (Generic Document) | [Link](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GenericDoc/jenkinsPipeline.md  ) |
| License Scanning POC Steps | [Link](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/02-%20Generic%20CI%20operation/License%20Scanning/License%20Scanning%20via%20FOSSA%20POC.md) |
| POC Generic Document | [Link](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GenericDoc/pipelinePOC.md) |
| Setup Jenkins | [Link](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GolangCI/Bug%20Analysis/Declarative%20Pipeline/Readme.md#Setup) |
| Jenkinsfile | [Link](https://github.com/avengers-p7/Jenkinsfile/blob/main/Declarative%20Pipeline/Python/Dependency_Scanning/Jenkinsfile) |
| Scripted vs Declarative Pipelines | [Link](https://www.baeldung.com/ops/jenkins-scripted-vs-declarative-pipelines) |
| License Scanning| [Link](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/02-%20Generic%20CI%20operation/License%20Scanning/README.md) |

***



