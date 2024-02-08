# Documentation of Declarative Pipeline for Static Code Analysis in Python

![image](https://github.com/avengers-p7/Documentation/assets/79625874/5419d5c8-ee87-4c28-9894-af831e8aba84)


***

| **Author** | **Created On** | **Last Updated** | **Document Version** |
| ---------- | -------------- | ---------------- | -------------------- |
| **Vikram Bisht** | **08-02-2024** | **08-02-2024** | **v1** |

***
# Table Of Contents

1. [Introduction](#Introduction)
2. [Pre-requisites](#Pre-requisites)
3. [Runtime Prerequisites](#Runtime-Prerequisites)
4. [Flow Diagram](#Flow-diagram)
5. [Configure Pipeline job](#Configure-Pipeline-job)
6. [Pipeline](#Pipeline)
7. [Declarative Syntax](#Declarative-Syntax)
8. [Evaluate Output](#Evaluate-Output)
9. [Conclusion](#conclusion)
10. [Contact Information](#contact-information)
11. [References](#References)


# Introduction


In this documentation, we'll explore the integration of static code analysis into a Python code repository using the powerful Pylint tool within a Jenkins pipeline. Static code analysis is a crucial step in ensuring code quality by identifying potential issues, enforcing coding standards, and promoting best practices. Jenkins, a widely used automation server, allows us to automate this process through defined pipelines, providing a streamlined and consistent approach to code analysis.

# Pre-requisites

| **Tool**   | **Description**            | 
| ---------- | -------------------------  | 
| Jenkins    | For continuous integration | 


# Runtime Prerequisites

| **Tool**   | **Description**                                         | 
| ---------- | -------------------------                               | 
| Python3    | For python                                              | 
| Pylint     | It will help to do Static code analysis. on python code |


# Flow Diagram

![image](https://github.com/avengers-p7/Documentation/assets/79625874/5ee31526-7422-480b-ba8e-e829b7ccbd8d)

# Configure Pipeline job

Below are the steps to Configure pipeline job for Jenkins and execute the pipeline

* Click on "New Item" or "Create new jobs" from the Jenkins dashboard.
* Enter a name for your job (e.g., "Python App Static_code_analysis") and select "Pipeline" as the job type.
* Click "OK" to create the new job.

![image](https://github.com/avengers-p7/Documentation/assets/79625874/a9605734-9d40-40f1-bc6d-a820d17a6a0b)

* Then configure the Pipeline section and click “Save” Button.
* Select pipeline script from SCM option as in this case we are running python code which is our github repo
* Give repo link and pass access token keys in credentials(access token generated from github) 
![image](https://github.com/avengers-p7/Documentation/assets/79625874/ff0cd2d9-3cd4-4536-b9b7-813a7c0faf35)
* select branch type
* Give path of your jenkins file(we have written our declerative pipeline for static code analysis in it) then apply save it. 
![image](https://github.com/avengers-p7/Documentation/assets/79625874/df67155a-4670-482e-861d-559a3a98cf61)

* Then execute your Pipeline by click on “Build Now”
![image](https://github.com/avengers-p7/Documentation/assets/79625874/5b551159-568c-4617-931b-c5ce53a3e1f8)

# Declarative Syntax
```
pipeline {
    agent any

    stages {
        stage('Code Checkout') {
            steps {
                git branch: 'main', credentialsId: 'Attendance-creds', url: 'https://github.com/OT-MICROSERVICES/attendance-api.git'
            }
        }

        stage('Create Virtual ENV') {
            steps {
                script {
                    sh 'python3 -m venv myenv'
                    sh '. myenv/bin/activate'
                }
            }
        }

        stage('Install dependencies') {
            steps {
                script {
                    sh 'python3 -m pip install -r requirements.txt'
                }
            }
        }

        stage('Static Code Analysis') {
            steps {
                script {
                    sh 'pylint router/ client/ models/ utils/ app.py | tee pylint.log'
                }
            }
        }
    }

    post {
        always {
            // Archive pylint reports
            archiveArtifacts artifacts: '**/pylint.log', allowEmptyArchive: true
        }
    }
}
```
* After successful completion of job our detailed output will store in pylint.log file, which looks like below: 
![image](https://github.com/avengers-p7/Documentation/assets/79625874/1a0d2d3d-5117-4152-88a8-6b9ba1759913)

# Conclusion
This pipeline will do Static Code Analysis against a python code and provide you details report.

# Contact Information

|  Name                     |        	Email Address         |
| ------------              | --------------------------------|
| Vikram Bisht              |  Vikram.Bisht@opstree.com       |  

# References

|  Source                                                                                 |        Description      |
| ------------                                                                            | ----------------------- |
| https://pylint.readthedocs.io/en/stable/                                                | Pylint Documentation    |  
| https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/04-%20Python%20CI%20Checks/Static%20code%20analysis(Python%20CI%20Checks).md                  | Refrence Documentation    |	
