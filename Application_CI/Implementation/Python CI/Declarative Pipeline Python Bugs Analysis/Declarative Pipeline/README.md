# Declarative Pipeline Python Bugs Analysis

![download](https://github.com/avengers-p7/Documentation/assets/156056570/983714ea-4f87-4c76-821a-a3af2af48291)


|   Author        |  Created on   |  Version   | Last updated by  | Last edited on |
| --------------- | --------------| -----------|----------------- | -------------- |
| Samir Kesare |  12-02-2024  |  Version 1 | Samir  | 13-02-2024    |

***
## Table of Contents
+ [Introduction](#Introduction)
+ [Why Declarative Pipeline](#Why-Declarative-Pipeline)
+ [Flow Diagram](#Flow-Diagram)
+ [Pre-requisites](#Pre-requisites)
+ [Setup](#Setup)
+ [Jenkinsfile](#Jenkinsfile)
+ [Conclusion](#Conclusion)
+ [Contact Information](#Contact-Information)
+ [Resources and References](#Resources-and-References)
  
***
## Introduction

Declarative Pipeline is a streamlined way to define Jenkins pipelines using a structured syntax within a pipeline {} block. It offers simplicity, readability, and built-in directives for defining stages, steps, and more. It integrates well with the Jenkins UI, provides pipeline visualization, and supports pipeline templates for code reuse. It's ideal for teams looking for a straightforward approach to CI/CD pipeline configuration. Cilck [**here**](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GenericDoc/jenkinsPipeline.md)

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

![image](https://github.com/avengers-p7/Documentation/assets/156056570/154a0883-c728-429b-a1c7-c8d7be8290f4)

***
## Pre-requisites

| Tool   | Description                          | Python3 Support | Purpose        |
|--------|--------------------------------------|-----------------|----------------|
| Bandit | A tool for bug analysis in Python   | Yes             | Python App     |
| Jenkins | CICD Tool                          |                 |                 |
***
## Setup

### Configure Pipeline Script:

* In the job configuration page, scroll down to the Pipeline section.
* Select Pipeline script from SCM.
* Give required repo url and enter your credentials.

![image](https://github.com/avengers-p7/Documentation/assets/156056570/f13a04bf-f6e4-4aa4-80a1-7005d9a5a383)

### Build the Pipeline and View Build Console Output:

* Once the pipeline configuration is saved, you can manually trigger the build by clicking on Build Now.
* After triggering the build, you can view the progress and console output of the build by clicking on the build number in the Jenkins dashboard.
* The console output will display the steps executed by the pipeline script, including code checkout and compilation.

![Screenshot 2024-02-07 185756](https://github.com/avengers-p7/Documentation/assets/156056570/a6de0626-5387-4391-ac4f-a87656bf15a0)

![Screenshot 2024-02-07 190504](https://github.com/avengers-p7/Documentation/assets/156056570/ed038dff-efa7-4d5a-bc02-2b1d66ffe196)

### JSON Report

* Cilck [**here**](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/Python%20CI/Declarative%20Pipeline%20Python%20Bugs%20Analysis/Declarative%20Pipeline/JSON%20Report)

***
## Jenkinsfile
```shell
pipeline {
    agent any
    
    environment {
        REPO_URL = 'https://github.com/OT-MICROSERVICES/attendance-api.git'
    }
    
    stages {
        stage('Checkout') {
            steps {
                // Checkout your code repository
                checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: "${REPO_URL}"]])
            }
        }
        stage('Install Dependencies') {
            steps {
                // Install necessary dependencies
                script {
                    sh 'python3 -m venv myenv'
                    sh '. myenv/bin/activate'
                }
            }
        }
        
        stage('Bugs Analysis - Bandit') {
            steps {
                script {
                    try {
                        // Ensure Bandit is installed and run the analysis
                        sh 'bandit --version' // Check Bandit version to ensure it's installed
                        sh 'bandit -r . -f json -o bandit_report.json'
                    } catch (Exception e) {
                        echo "Bugs analysis failed: ${e.message}"
                    }
                }
            }
        }
    }
    
    post {
        always {
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
| Samir Kesare | samir.kesare.snaatak@mygurukulam.co |

***
## Resources and References

|  **Description** |   **Source** |
| ---------------- | ------------ |
| About Jenkins Pipeline (Generic Document) | [Link](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GenericDoc/jenkinsPipeline.md  ) |
| Jenkinsfile | [Link](https://github.com/avengers-p7/Jenkinsfile/blob/main/Declarative%20Pipeline/golang/Bug%20Analysis/Jenkinsfile) |
| Scripted vs Declarative Pipelines | [Link](https://www.baeldung.com/ops/jenkins-scripted-vs-declarative-pipelines) |
| Bug Analysis Introduction | [Link](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/05-%20GoLang%20CI%20Checks/Bug%20Analysis/Introduction%20of%20Bugs%20analysis%20(GoLang%20CI%20Checks).md#resources-and-references) |

