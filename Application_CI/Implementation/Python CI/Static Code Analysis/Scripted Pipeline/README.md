# Documentation of Scripted Pipeline for Static Code Analysis in Python

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
7. [Scripted Syntax](#Scripted-Syntax)
8. [Evaluate Output](#Evaluate-Output)
9. [Conclusion](#conclusion)
10. [Contact Information](#contact-information)
11. [References](#References)


# Introduction


In this documentation, we'll explore the integration of static code analysis into a Python code repository using the powerful Pylint tool within a Jenkins pipeline. Static code analysis is a crucial step in ensuring code quality by identifying potential issues, enforcing coding standards, and promoting best practices. Jenkins, a widely used automation server, allows us to automate this process through defined pipelines, providing a streamlined and consistent approach to code analysis.

A Jenkins scripted pipeline is a way to define your Jenkins pipeline using Groovy code. It allows you to describe your build process using a scripting language instead of a visual interface.
To know more about pipelines please follow this link  **[Reference Link](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GenericDoc/jenkinsPipeline.md
)**


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

![image](https://github.com/avengers-p7/Documentation/assets/79625874/2492a83d-bd29-4682-bb94-974fbaedca77)

# Configure Pipeline job

 Set up Jenkins Pipeline job & Configure your pipeline using the detailed documentation provided in the following link:**

**[Reference Link](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GenericDoc/pipelinePOC.md)**

# Declarative Syntax
```
node {
    stage('Code Checkout') {
        git branch: 'main', credentialsId: 'Attendance-creds', url: 'https://github.com/OT-MICROSERVICES/attendance-api.git'
    }

    stage('Create Virtual ENV') {
        sh 'python3 -m venv myenv'
        sh '. myenv/bin/activate'
    }

    stage('Install dependencies') {
        sh 'python3 -m pip install -r requirements.txt'
    }

    stage('Static Code Analysis') {
        sh 'pylint router/ client/ models/ utils/ app.py | tee pylint.log'
    }
}

post {
    always {
        archiveArtifacts artifacts: '**/pylint.log', allowEmptyArchive: true
    }
    success {
        echo 'Pipeline executed successfully!'
    }
}
```

* After successful completion of job our detailed output will store in pylint.log file, which looks like below: 
![image](https://github.com/avengers-p7/Documentation/assets/79625874/1a0d2d3d-5117-4152-88a8-6b9ba1759913)


# Conclusion
This pipeline will do Static Code Analysis against a python code by using scripted jenkins pipeline and provide you details report.


# Contact Information

|  Name                     |        	Email Address         |
| ------------              | --------------------------------|
| Vikram Bisht              |  Vikram.Bisht@opstree.com       |  


# References

|  Source                                                                                 |        Description      |
| ------------                                                                            | ----------------------- |
| https://pylint.readthedocs.io/en/stable/                                                | Pylint Documentation    |  
| https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/04-%20Python%20CI%20Checks/Static%20code%20analysis(Python%20CI%20Checks).md                  | Refrence Documentation    |	
