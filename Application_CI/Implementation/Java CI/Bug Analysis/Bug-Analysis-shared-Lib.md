# Shared Library for JAVA Bug Analysis

| **Author** | **Created On** | **Last Updated** | **Document Version** |
| ---------- | -------------- | ---------------- | -------------------- |
| **Parasharam Desai** | 15-02-2024 | 15-02-2024 | V1 |

***
# Table of Contents
+ [Introduction](#Introduction)
+ [Why Shared Library](#Why-Shared-Library)
+ [Flow Diagram](#Flow-Diagram)
+ [Pre-requisites](#Pre-requisites)
+ [Setup of Bug Analysis](#Setup-of-Bug-Analysis-Via-Shared-Library)
+ [HTML Report](#HTML-Report)
+ [Jenkinsfile](#Jenkinsfile)
+ [Shared Library](#Shared-Library)
+ [Conclusion](#Conclusion)
+ [Contact Information](#Contact-Information)
+ [Resources and References](#Resources-and-References)

  
***
# Introduction

 <img width="360" length="100" alt="Golang" src="https://github.com/avengers-p7/Documentation/assets/156056413/f94f127a-d207-4c76-bc32-d25e4fe48280"> 

A Jenkins Shared Library is a collection of reusable code that facilitates the sharing of common pipeline logic among teams in Jenkins. It simplifies CI/CD processes by abstracting complex tasks into functions, speeding up pipeline development. By keeping shared code separate from individual pipelines, teams ensure consistency and minimize duplication. This fosters collaboration, encourages best practices, and streamlines Jenkins pipeline creation, leading to better software delivery and development workflows.  
About more information [**Click Here**](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GenericDoc/sharedLibrary/README.md)

***
# Why Shared Library
| Advantage          | Description                                                                                                                                                          |
|--------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Reusability**        | Shared Libraries allow teams to write code once and reuse it across multiple pipelines. This reduces duplication of effort and promotes consistency in the CI/CD process. |
| **Centralization**     | By centralizing common pipeline logic, updates and improvements can be made in one place, benefiting all pipelines that use the library.                             |
| **Abstraction**        | Complex tasks can be abstracted into simple functions in the Jenkins Shared Library, making pipeline scripts cleaner and more maintainable.                            |
| **Standardization**    | Jenkins Shared Library allows organizations to define standardized practices, coding conventions, and security measures across all pipelines.                         |
| **Collaboration**      | Jenkins Shared Libraries encourage collaboration among teams, as they can share and contribute to a common set of pipeline tools and utilities.                         |
| **Versioning Control** | Jenkins Shared Library can be version-controlled, enabling teams to manage changes and rollbacks effectively.                                                        |
| **Ease of Maintenance** | As the Jenkins Shared Library is maintained separately from individual pipelines, updates and bug fixes can be implemented without impacting the pipelines directly. |

***
# Pre-requisites

| **Jenkins (2.426.3)** | Enables Continuous Integration |
| ---------------- | -------------------- |
| **Java 17** | Required for compiling Jenkins and Spring Boot projects |
| **Maven(3.6.9)** | Handles build automation and dependency management |
| **Spotbug (4.8.1)** | Employed for bug analysis |
***

# Flow Diagram




***

# Steps to run Pipeline

**1. Including Spotbugs Plugin in pom.xml**

To include the Spotbugs plugin in the `pom.xml` file, follow these steps:

* Add the Spotbugs-maven-plugin within the reporting section.
* Ensure that running `mvn site` will generate the Spot Bugs report.

For detailed instructions, please refer to the [Proof of Concept (POC) documentation](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/03-%20Java%20CI%20checks/Bug%20Analysis/POC.md).



**2. Configure Maven tool in Jenkins**

Go to `Dashboard--> Manage Jenkins--> Tools` and configure maven tool.

![image](https://github.com/avengers-p7/Documentation/assets/156056444/d9ff8a0d-900a-4e4b-ac68-34507ef3348b)

**3. Bug Analysis Setup via Shared Library**
* Follow this document for Setup [**Cilck here**](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GenericDoc/sharedLibrary/setup.md)


# Console Output:

Based on the console output provided below, we can infer that there are a few bugs present



***

# HTML Report

 * Cilck [**here**](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/03-%20Java%20CI%20checks/spotbugHtmlReports/spotbugs.html)

***
# Jenkinsfile
  * [**Jenkinsfie**](https://github.com/avengers-p7/Jenkinsfile/blob/main/SharedLibrary/Java/BugAnalysis/Jenkinsfile)

  
 ```shell
@Library('my-shared-library') _

pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                script {
                    gitCheckout(branch: "main", url: "https://github.com/Parasharam-Desai/salary-api.git")
                }
            }
        }
        stage('Bug Analysis') {
            steps {
                script {
                    javaBugAnalysis()
                }
            }
        }
        stage('Publish HTML Report') {
            steps {
                script {
                    javaBugHtmlReport()
                }
            }
        }
    }
}
post {
        always {
        // One or more steps need to be included within each condition's block.
        cleanWorkspace()
       }
        success { 
            echo 'Job Run Successfully !'
        }
        failure { 
            echo 'Job Failed !'
        }
    }
}

        
```
# Shared Library

[**gitCheckout.groovy**](https://github.com/CodeOps-Hub/SharedLibrary/blob/main/vars/gitCheckout.groovy)

  ```shell

// Checkout Github Public Repository
def call(Map config = [:]) {
            checkout scm: [
                $class: 'GitSCM',
                branches: [[name: config.branch]],
                userRemoteConfigs: [[url: config.url]]
            ]
}

```
[**javaBugAnalysis.groovy**](https://github.com/CodeOps-Hub/SharedLibrary/blob/main/vars/javaBugAnalysis.groovy)

  ```shell

def call() {
            sh 'mvn compile'
            sh 'mvn spotbugs:spotbugs'
            sh 'mvn site'
}
```
[**javaBugHtmlReport.groovy**](https://github.com/CodeOps-Hub/SharedLibrary/blob/main/vars/javaBugHtmlReport.groovy)

  ```shell

def call() {
            publishHTML(target: [
                allowMissing: false,
                alwaysLinkToLastBuild: true,
                keepAll: true,
                reportDir: 'target/site',
                reportFiles: 'spotbugs.html',
                reportName: 'SpotBugs Report'
            ])
}

```
[**cleanWorkspace.groovy**](https://github.com/CodeOps-Hub/SharedLibrary/blob/main/vars/cleanWorkspace.groovy)

```shell

// Will not clean workspace if build is Sucessful and vice versa
def call() {
  cleanWs cleanWhenSuccess: false
}

```
***
# Conclusion
The Jenkins Shared Library streamlines CI/CD processes by allowing teams to share reusable code and logic across various pipelines. It standardizes workflows, minimizes duplication, and ensures consistency. With abstracted complex tasks into reusable functions, it simplifies maintenance and fosters collaboration among teams. By promoting best practices and enabling version control, it enhances the efficiency and reliability of the CI/CD process, accessible even without Jenkins admin access.

***
# Contact Information

|    Name                                   | Email Address                    |
|-------------------------------------------|----------------------------------|
| **[Parasharam Desai](https://github.com/Parasharam-Desai)** | parasharam.desai.snaatak@mygurukulam.co |

***
# Resources and References

|       **Description**                                   |           **References**                    |
|---------------------------------------------------------|-----------------------------------------------|
| Jenkins Pipeline     | [Jenkins Pipeline Documentation](https://www.jenkins.io/doc/book/pipeline/) |
| Bug Analysis Setup via Shared Library* |[Link](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GenericDoc/sharedLibrary/setup.md)|
