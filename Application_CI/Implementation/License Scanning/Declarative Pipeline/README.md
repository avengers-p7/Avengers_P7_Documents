# Declarative Pipeline : License Scanning



|   Author        |  Created on   |  Version   | Last updated by  | Last edited on |
| --------------- | --------------| -----------|----------------- | -------------- |
| Aakash Tripathi |  16-02-2024  |  Version 1 | Aakash  | 18-02-2024    |

***
## Table of Contents
+ [Introduction](#Introduction)
+ [Why Declarative Pipeline](#Why-Declarative-Pipeline)
+ [Flow Diagram](#Flow-Diagram)
+ [Pre-requisites](#Pre-requisites)
+ [Setup of License Scanning](#Setup-of-License-Scanning)
+ [Jenkinsfile](#Jenkinsfile)
+ [Conclusion](#Conclusion)
+ [Contact Information](#Contact-Information)
+ [Resources and References](#Resources-and-References)
  
***
## Introduction

Declarative Pipeline is a streamlined way to define Jenkins pipelines using a structured syntax within a pipeline {} block. It offers simplicity, readability, and built-in directives for defining stages, steps, and more. It integrates well with the Jenkins UI, provides pipeline visualization, and supports pipeline templates for code reuse. It's ideal for teams looking for a straightforward approach to CI/CD pipeline configuration.

***
## Why Declarative Pipeline
| Aspect          | Description                                                                                               |
|-----------------|-----------------------------------------------------------------------------------------------------------|
| **Organization**    | Markdown tables organize pipeline stages, descriptions, and commands into neat columns for easier readability and understanding. |
| **Readability**     | Condenses verbose Declarative Pipeline syntax, particularly beneficial for complex pipelines, enhancing readability and comprehension. |
| **Documentation**   | Integrates pipeline configuration seamlessly into project documentation using Markdown, providing a comprehensive overview of CI/CD processes. |
| **Version Control** | Markdown files are version-controlled with tools like Git, enabling tracking of pipeline changes, revision history, and collaboration. |
| **Accessibility**   | Markdown files are viewable and editable with basic text editors or online Markdown editors, facilitating review and contribution by team members, including non-technical stakeholders. |
| **Presentation**    | Markdown files can be rendered into multiple formats, including HTML, PDF, and slideshows, enabling formatted documents or presentations for sharing and presentation purposes. |

***
## Flow Diagram  
![Screenshot 2024-02-20 093526](https://github.com/avengers-p7/Documentation/assets/156056344/ff5e61b7-196e-47a0-a812-a81d440bd932)


***
## Pre-requisites
| **Pre-requisites** | **Version** |
| ------------------ | ----------- |
| Jenkins | 2.426.3 | 
| FOSSA CLI | 3.9.5 |

***
## Setup of Credential Scanning Declerative Pipeline
* Follow this document for Setup [**Cilck here**](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GenericDoc/pipelinePOC.md)

![Screenshot 2024-02-18 213920](https://github.com/avengers-p7/Documentation/assets/156056344/be9d3972-a6a4-4d4d-b5cd-3119585f408d)


* Build
  
![Screenshot 2024-02-18 222357](https://github.com/avengers-p7/Documentation/assets/156056344/47852dcb-c6ac-411c-b691-78a698572fa6)

* Console Output:
 ![Screenshot 2024-02-18 222512](https://github.com/avengers-p7/Documentation/assets/156056344/751ae5d1-daf9-4e32-a247-c7a41ebf1bca)



> [!NOTE]
> **Changes**
> *  **Pipeline name**       **-**  `License Scanning Declarative Pipeline`
> *  **Jenkinsfile Path**    **-**  `Declarative Pipeline/License Scanning/Jenkinsfile`  
![Screenshot 2024-02-18 213939](https://github.com/avengers-p7/Documentation/assets/156056344/c1165750-e64e-49d0-9c29-ac492cdd9ae6)

***

## Jenkinsfile
  * [**Jenkinsfie**](https://github.com/CodeOps-Hub/Jenkinsfile/blob/main/Declarative%20Pipeline/Credential%20Scanning/Jenkinsfile)
  ```shell 
pipeline {
    agent any
    
    environment {
        // Define the environment variable that will hold the secret
        FOSSA_API_KEY = credentials('fossaToken')
    }

    stages {
         stage('Checkout SCM') {
            steps {
                    git branch: 'main', url: 'https://github.com/OT-MICROSERVICES/salary-api.git'
            }
        }
        
        stage('Download and Install FOSSA') {
            steps {
                     sh 'curl -H \'Cache-Control: no-cache\' https://raw.githubusercontent.com/fossas/fossa-cli/master/install-latest.sh | bash'
            }
        }
        

        stage('FOSSA Scan') {
            steps {
                    sh 'fossa analyze'
                    sh 'fossa test'
            }
        }
    }
    post {
        success {
            sh 'echo "No Issues Reported"'
            cleanWs()
        }
        failure {
            sh 'echo "Issues Reported - Please review your code"'
            cleanWs()
        }
        }
        
    }

```
***
## Conclusion

Declarative Pipeline simplifies Jenkins pipeline configuration, offering clarity, readability, and integration with Markdown tables. It enhances collaboration, version control, and accessibility while enabling easy documentation and presentation of CI/CD processes.

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
| License Scanning POC Steps | [Link](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/02-%20Generic%20CI%20operation/License%20Scanning/License%20Scanning%20via%20FOSSA%20POC.md) |
| POC Generic Document | [Link](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GenericDoc/pipelinePOC.md) |
| Setup Jenkins | [Link](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GolangCI/Bug%20Analysis/Declarative%20Pipeline/Readme.md#Setup) |
| Jenkinsfile | [Link](https://github.com/avengers-p7/Jenkinsfile/blob/main/Declarative%20Pipeline/Python/Dependency_Scanning/Jenkinsfile) |
| Scripted vs Declarative Pipelines | [Link](https://www.baeldung.com/ops/jenkins-scripted-vs-declarative-pipelines) |
| License Scanning| [Link](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/02-%20Generic%20CI%20operation/License%20Scanning/README.md) |

***


