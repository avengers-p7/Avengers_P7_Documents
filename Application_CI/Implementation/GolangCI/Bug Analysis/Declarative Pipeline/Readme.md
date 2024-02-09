# Declarative Pipeline-Go Lang Bug Analysis

|   Author        |  Created on   |  Version   | Last updated by  | Last edited on |
| --------------- | --------------| -----------|----------------- | -------------- |
| Vishal Kumar Kesarwani |  09-02-2024  |  Version 1 | Vishal  | 09-02-2024    |

***
## Table of Contents
+ [Introduction](#Introduction)
+ [Why Declarative Pipeline](#Why-Declarative-Pipeline)
+ [Flow Daigram](#Flow-Daigram)
+ [Pre-requisites](#Pre-requisites)
+ [Setup](#Setup)
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
## Flow Daigram
![Screenshot from 2024-02-09 17-47-50](https://github.com/avengers-p7/Documentation/assets/156056413/68a24b98-2a1e-4586-a748-566938055d4d)

***
## Pre-requisites

* Jenkins Installed
* golang
* golangCI-lint

***
## Setup
**Step-1** Create a New Pipeline Job:

- Navigate to the Jenkins dashboard and click on **New Item**.
- Enter a name for your job (e.g., **"Bug Analysis (GoLang CI Checks)"**).
- Select Pipeline and click **OK**.
    <img width="760" length="100" alt="Golang" src="https://github.com/avengers-p7/Documentation/assets/156056413/ec91bd45-1d51-4f6d-9898-58ef3e6c104e">

**Step-2** Configure Pipeline Script:

- In the job configuration page, scroll down to the Pipeline section.
- Select Pipeline script from SCM.
- Give required repo url and enter your credentials.
  <img width="760" length="100" alt="Golang" src="https://github.com/avengers-p7/Documentation/assets/156056413/76030dcc-c1b8-4604-94f7-6f329563a88e">

**Step-3** Save the Configuration :

- Click on Save to save the job configuration.
  <img width="760" length="100" alt="Golang" src="https://github.com/avengers-p7/Documentation/assets/156056413/70706041-979e-4df9-aadb-adbf57419e3c">

**Step-4** Build the Pipeline and View Build Console Output:

- Once the pipeline configuration is saved, you can manually trigger the build by clicking on Build Now.
- After triggering the build, you can view the progress and console output of the build by clicking on the build number in the Jenkins dashboard.
- The console output will display the steps executed by the pipeline script, including code checkout and compilation.
  <img width="760" length="100" alt="Golang" src="https://github.com/avengers-p7/Documentation/assets/156056413/47227db9-4499-4db1-a0f3-70dedf92091d">

- Console Output :
    
  <img width="760" length="100" alt="Golang" src="https://github.com/avengers-p7/Documentation/assets/156056413/5b9d12d7-e0b6-4584-8bcc-3f8d63626327">
   <img width="760" length="100" alt="Golang" src="https://github.com/avengers-p7/Documentation/assets/156056413/1813ded0-e8a2-43cf-a06e-9301decd5a6a">
***

## HTML Report
 * Cilck [**here**](https://github.com/avengers-p7/Jenkinsfile/blob/main/Declarative%20Pipeline/golang/Bug%20Analysis/Report.html)

***
## Jenkinsfile
  * [**Jenkinsfie**](https://github.com/avengers-p7/Jenkinsfile/blob/main/Declarative%20Pipeline/golang/Bug%20Analysis/Jenkinsfile)
  ```shell
  pipeline {
    agent any
    
    stages {
        stage('Installation Pre-Requisites') {
            steps {
                script {
                    // Update apt packages
                    sh 'sudo apt update'
                    // Install Go using snap
                    sh 'sudo snap install go --classic'
                    // Remove golangci-lint using snap
                    sh 'sudo snap remove golangci-lint || true'
                    // Install GolangCI-lint
                    sh 'go install github.com/golangci/golangci-lint/cmd/golangci-lint@latest'
                    // Add $HOME/go/bin to PATH
                    env.PATH += ":$HOME/go/bin"
                }
            }
        }
        stage('Clone Repository') {
            steps {
                // Clone the Git repository
                git branch: 'main', credentialsId: 'vishal-cred', url: 'https://github.com/OT-MICROSERVICES/employee-api.git'
            }
        }
        stage('Linting') {
            steps {
                script {
                    // Run golangci-lint and ignore errors
                    sh 'golangci-lint run ./... || true'
                }
            }
        }
        stage('Generate HTML Report') {
            steps {
                script {
                    // Run golangci-lint with the --out-format option to specify the output format
                    sh 'golangci-lint run ./... --out-format html > report.html || true'
                }
            }
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
| Vishal | vishal.kesarwani.snaatak@mygurukulam.co |
***
## Resources and References
|  **Description** |   **Source** |
| ---------------- | ------------ |
| About Jenkins Pipeline (Generic Document) | [Link](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GenericDoc/jenkinsPipeline.md  ) |
| Flow Step for create pipeline | [Link](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/05-%20GoLang%20CI%20Checks/Bug%20Analysis/POC%20of%20Bug%20Analysis%20(Golang%20CI%20Checks).md) |
| Jenkinsfile | [Link](https://github.com/avengers-p7/Jenkinsfile/blob/main/Declarative%20Pipeline/golang/Bug%20Analysis/Jenkinsfile) |
| Scripted vs Declarative Pipelines | [Link](https://www.baeldung.com/ops/jenkins-scripted-vs-declarative-pipelines) |
| Bug Analysis Introduction | [Link](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/05-%20GoLang%20CI%20Checks/Bug%20Analysis/Introduction%20of%20Bugs%20analysis%20(GoLang%20CI%20Checks).md#resources-and-references) |

***
