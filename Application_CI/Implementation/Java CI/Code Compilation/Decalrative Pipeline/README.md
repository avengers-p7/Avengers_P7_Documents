# Java Code Compilation(Declarative Pipeline)

| Author                                                           | Created on  | Version    | Last Updated by | Last Updated on |
| ---------------------------------------------------------------- | ----------- | ---------- | --------------- | --------------- |
| **[Harshit Singh](https://github.com/Panu-S-Harshit-Ninja-07)**  | 02-02-2024  | 1.0        | Harshit Singh   | 11-02-2024      |


## Table  of Contents

1. [Introduction](#Introduction)
2. [What is Declarative Pipeline](#What-is-Declarative-Pipeline)
3. [Prerequisites](#Prerequisites)
4. [Runtime Prerequisites](#Runtime-Prerequisites)
5. [Pipeline Setup](#Pipeline-Setup)
6. [Contact Information](#Contact-Information)
7. [References](#References)
***

## Introduction 

The process of code compilation involves converting high-level programming code, such as Java, C++, or Python, into machine-readable instructions or bytecode. This transformation is carried out by a compiler, which is a specialized tool designed to translate human-readable source code into an executable format.
Here we are using maven compiler to convert of code into  bytecode.

**For more information visit the below document link:**

[\[ Reference Doc \]](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/03-%20Java%20CI%20checks/Code%20Complication.md)

In this task, we are using Declarative Pipeline.
***
## What is Declarative Pipeline

Declarative Pipeline in Jenkins offers a simplified and structured approach for defining CI/CD pipelines, using a human-readable syntax with predefined sections like pipeline, stages, and agent. It's designed to be easy to read and maintain, making it suitable for users without strong scripting skills.It enforces a stricter syntax and allows for less flexibility compared to the scripted pipeline, which can be seen as an advantage for ensuring consistency and readability.

## Prerequisites

| Tool | Description |
| ---- | ----------- |
| **Jenkins(2.426.3)** | To build our pipeline |

> [!Important]
> I have installed the plugin bundle provided by Jenkins during setup. If you have not done the same, you may encounter plugin errors.

***
## Runtime Prerequisites

|Language / Dependency|Description|
|-------|-------|
| **Java 17** | For springboot project compilation | 
| **Maven Compiler Plugin** | For springboot project compilation |
***
## Pipeline Setup
1. **Fork the Github Repo**
```shell
git clone https://github.com/OT-MICROSERVICES/salary-api.git
```
[**Repo Link**](https://github.com/OT-MICROSERVICES/salary-api)

2. **Add maven compiler plugin in `pom.xml`**   
```shell
			<plugin>
				<groupId>org.apache.maven.plugins</groupId>
				<artifactId>maven-compiler-plugin</artifactId>
				<version>3.11.0</version>
				<!-- ... other configurations ... -->
			</plugin>
```
![image](https://github.com/avengers-p7/Documentation/assets/156056444/5375b03d-718e-4ef3-a79a-b7a035a9956e)

3. **Configure Maven tool in Jenkins**
Go to `Dashboard--> Manage Jenkins--> Tools` and configure maven tool.

![image](https://github.com/avengers-p7/Documentation/assets/156056444/d9ff8a0d-900a-4e4b-ac68-34507ef3348b)

4. **Create and Configure your Jenkins Pipeline job**

	Follow below document

	[Reference Document](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GenericDoc/pipelinePOC.md)

![image](https://github.com/avengers-p7/Documentation/assets/156056444/3b8bd90c-bc4f-47bd-8aea-380275a4fbf6)

6. **Now Build your Pipeline**
![image](https://github.com/avengers-p7/Documentation/assets/156056444/53deb6b1-a9a1-4e5b-83da-c64a93becfb0)
***
## Console Output
![image](https://github.com/avengers-p7/Documentation/assets/156056444/cbd74086-602f-45af-8cb8-61e2ec2ba2ae)

![image](https://github.com/avengers-p7/Documentation/assets/156056444/33b3f5e3-cc47-4035-b25f-1016eea09c97)
***
## [Pipeline](https://github.com/avengers-p7/Jenkinsfile/blob/main/Declarative%20Pipeline/Java/CodeCompilation/Jenkinsfile)

```shell
pipeline {
    agent any
    tools {
      maven 'mvn'
    }
    stages {
        stage('Checkout GIT') {
            steps {
                checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/Panu-S-Harshit-Ninja-07/OT-Salary-API.git']])
                sh 'ls $WORKSPACE/'
            }
        }
        stage('Starting Code Compilation ') {
            steps {
                sh 'echo "Starting Java Code Compilation.........."'
                sh 'mvn clean compile'
            }
        }
    }
post { 
        success { 
            sh 'ls $WORKSPACE/'
            echo 'Compiled Successfully !'
            sh 'tree $WORKSPACE/target/'
        }
        failure { 
            echo 'Compilation Failed !'
        }
    }
}
```

***

## Contact Information

|     Name         | Email  |
| -----------------| ------------------------------------ |
| Harshit Singh    | harshit.singh.snaatak@mygurukulam.co |
***

## References

| Description                                   | References  
| --------------------------------------------  | -------------------------------------------------|
| Clean Workspace | https://www.jenkins.io/doc/pipeline/tour/running-multiple-steps/#finishing-up |
| Pipeline (Generic Doc) | https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GenericDoc/jenkinsPipeline.md |
| Create Pipeline (Generic Doc)| https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GenericDoc/pipelinePOC.md |
| Pipeine Syntax | https://www.jenkins.io/doc/book/pipeline/#pipeline-syntax-overview |
| Pipeline Concepts | https://www.jenkins.io/doc/book/pipeline/#pipeline-concepts |
