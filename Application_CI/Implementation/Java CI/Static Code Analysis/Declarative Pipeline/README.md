# Java Static Code Analysis(Declarative Pipeline)
![image](https://github.com/avengers-p7/Documentation/assets/156056444/82b47df9-4d1d-4bc7-ae5c-56e44f65beb5)

| Author                                                           | Created on  | Version    | Last Updated by | Last Updated on |
| ---------------------------------------------------------------- | ----------- | ---------- | --------------- | --------------- |
| **[Harshit Singh](https://github.com/Panu-S-Harshit-Ninja-07)**  | 13-02-2024  | 1.0        | Harshit Singh   | 14-02-2024      |


## Table  of Contents

1. [Introduction](#Introduction)
2. [What is Declarative Pipeline](#What-is-Declarative-Pipeline)
3. [Prerequisites](#Prerequisites)
4. [Flow Diagram](#Flow-Diagram)
5. [Runtime Prerequisites](#Runtime-Prerequisites)
6. [Pipeline Setup](#Pipeline-Setup)
7. [Results](#results)
8. [Pipeline](#pipeline)
9. [Contact Information](#Contact-Information)
10. [References](#References)
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

**For more information visit the below document link:**

[\[ Reference Doc \]](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GenericDoc/jenkinsPipeline.md )

## Prerequisites

| Tool | Description |
| ---- | ----------- |
| **Jenkins(2.426.3)** | To build our pipeline |
|**Sonarqube(9.6.1.59531)**| For Static code analysis |

> [!Important]
> I have installed the plugin bundle provided by Jenkins during setup. If you have not done the same, you may encounter plugin errors.

***
## Runtime Prerequisites

|Language / Dependency|Description|
|-------|-------|
| **Java 17** | For springboot project compilation | 
| **Maven Compiler Plugin** | For springboot project compilation |
|**Sonarque Scanner Plugin**| To integrate Jenkins with Sonarqube |
***
## Flow Diagram
![image](https://github.com/avengers-p7/Documentation/assets/156056444/40a61172-8415-45b7-8c14-e9b947b7e968)
***
## Pipeline Setup

1. **Configure Maven tool in Jenkins**
Go to `Dashboard--> Manage Jenkins--> Tools` and configure maven tool.

![image](https://github.com/avengers-p7/Documentation/assets/156056444/d9ff8a0d-900a-4e4b-ac68-34507ef3348b)


2. **Install Sonarqube Scanner plugin in Jenkins**

![image](https://github.com/avengers-p7/Documentation/assets/156056444/28625f84-3ae7-45e3-8cea-d1d73daba895)

3. **Create  token in Sonarqube and add in Jenkins Credentials**
	- login to Sonarqube Server and
		![image](https://github.com/avengers-p7/Documentation/assets/156056444/f01959ac-2a3a-4644-ba49-ea52e886f2db)

	- click on `Update Tokens`
		![image](https://github.com/avengers-p7/Documentation/assets/156056444/f2f5fcbd-15db-45f7-8e41-abcda2e21da3)

 	- give name of token , select no. of days and then genarate the token
		![image](https://github.com/avengers-p7/Documentation/assets/156056444/8a0838e5-e186-4f2a-8a55-8151bad09958)

  	- copy and keep your token
     		![image](https://github.com/avengers-p7/Documentation/assets/156056444/511a3b73-922b-4277-b2a1-01d782609aca)
     

3. **Configure Sonarqube Server  in `Dashboard --> Manage Jenkins --> System`**

![image](https://github.com/avengers-p7/Documentation/assets/156056444/1681289c-a3ef-4d6a-9e54-a2b2a948d660)

4. **Create and Configure your Jenkins Pipeline job**

	Follow below document

	[Reference Document](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GenericDoc/pipelinePOC.md)

![image](https://github.com/avengers-p7/Documentation/assets/156056444/3b8bd90c-bc4f-47bd-8aea-380275a4fbf6)

5. **Now Build your Pipeline**
![image](https://github.com/avengers-p7/Documentation/assets/156056444/ef7acca1-6e0d-4fc3-bfff-11b71a420dc3)
***
## Results
![image](https://github.com/avengers-p7/Documentation/assets/156056444/9fb6a3d9-3e72-46b4-97ef-07e318160d9b)

![image](https://github.com/avengers-p7/Documentation/assets/156056444/a05f8611-6a83-48fa-a98a-61f2c6b2c6f6)

***
## [Pipeline](https://github.com/avengers-p7/Jenkinsfile/blob/main/Declarative%20Pipeline/Java/CodeCompilation/Jenkinsfile)

```shell
pipeline {
    agent any

    tools {
       maven 'mvn'
    }

    stages {
        stage("Git Checkout") {
            steps {
                script {
                    git branch: 'main', url: 'https://github.com/OT-MICROSERVICES/salary-api.git'
                }
            }
        }
        stage ('compile'){
            steps{
                sh 'mvn clean compile'
                }
        }

        stage('Static Code Analysis') {
            steps {
                withSonarQubeEnv(installationName: 'sq1') { 
                    sh './mvnw org.sonarsource.scanner.maven:sonar-maven-plugin:3.9.0.2155:sonar'
                }
            }
        }
    }
    post {
        always {
        // One or more steps need to be included within each condition's block.
        cleanWs cleanWhenSuccess: false
       }
        success { 
            echo 'Build Successfully !'
        }
        failure { 
            echo 'Build Failed !'
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
| Sonarqube Intergration | https://www.youtube.com/watch?v=KsTMy0920go&t=342s |
| Clean Workspace | https://www.jenkins.io/doc/pipeline/tour/running-multiple-steps/#finishing-up |
| Pipeline (Generic Doc) | https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GenericDoc/jenkinsPipeline.md |
| Create Pipeline (Generic Doc)| https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GenericDoc/pipelinePOC.md |
| Pipeine Syntax | https://www.jenkins.io/doc/book/pipeline/#pipeline-syntax-overview |
| Pipeline Concepts | https://www.jenkins.io/doc/book/pipeline/#pipeline-concepts |

