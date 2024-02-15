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

Static analysis, also called static code analysis, is a method of computer program debugging that is done by examining the code without executing the program. The process provides an understanding of the code structure and can help ensure that the code adheres to industry standards. Static analysis is used in software engineering by software development and quality assurance teams. Automated tools can assist programmers and developers in carrying out static analysis. The software will scan all code in a project to check for vulnerabilities while validating the code.

**For more information visit the below document link:**

[\[ Reference Doc \]](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/08-%20Jenkins/static%20code%20Analysis.md)

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
![image](https://github.com/avengers-p7/Documentation/assets/156056444/ad92496d-4b84-481f-94d8-0b8cd8f6e944)
***
## Pipeline Setup

1. **Configure Maven tool in Jenkins**
Go to `Dashboard--> Manage Jenkins--> Tools` and configure maven tool.

![image](https://github.com/avengers-p7/Documentation/assets/156056444/d9ff8a0d-900a-4e4b-ac68-34507ef3348b)


2. **Install Sonarqube Scanner plugin in Jenkins**

![image](https://github.com/avengers-p7/Documentation/assets/156056444/28625f84-3ae7-45e3-8cea-d1d73daba895)

3. **Create  token in Sonarqube**
	- login to Sonarqube Server and go to `Administration --> Security --> Users`
		![image](https://github.com/avengers-p7/Documentation/assets/156056444/f01959ac-2a3a-4644-ba49-ea52e886f2db)

	- click on `Update Tokens`
		![image](https://github.com/avengers-p7/Documentation/assets/156056444/f2f5fcbd-15db-45f7-8e41-abcda2e21da3)

 	- give name of token , select no. of days and then genarate the token
		![image](https://github.com/avengers-p7/Documentation/assets/156056444/8a0838e5-e186-4f2a-8a55-8151bad09958)

  	- copy and keep your token
     		![image](https://github.com/avengers-p7/Documentation/assets/156056444/511a3b73-922b-4277-b2a1-01d782609aca)
     

3. **Add Sonarqube token in Jenkins Credentials**
   	- login to your jenkins Dashboard and go to `Dashboard --> Manage Jenkins --> Credentials`

   	  	Below, click on add `Add Credentials`

		![image](https://github.com/avengers-p7/Documentation/assets/156056444/125c1d80-6342-4e24-9d0d-4f122ddeaf95)
  
	- Select **`Secret Text`** and provide the token that you copied in secret section. Also, give ID and Description to your credential.
		![image](https://github.com/avengers-p7/Documentation/assets/156056444/2727ea81-3014-4910-93ef-77237529f313)

4.  **Configure Sonarqube Server  in `Dashboard --> Manage Jenkins --> System`**

![image](https://github.com/avengers-p7/Documentation/assets/156056444/1681289c-a3ef-4d6a-9e54-a2b2a948d660)

4. **Create and Configure your Jenkins Pipeline job**

	Follow below document

	[Reference Document](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GenericDoc/pipelinePOC.md)

![image](https://github.com/avengers-p7/Documentation/assets/156056444/d2950e7f-0ff0-4a19-a83a-bce7594f6854)

5. **Now Build your Pipeline**
![image](https://github.com/avengers-p7/Documentation/assets/156056444/ef7acca1-6e0d-4fc3-bfff-11b71a420dc3)
***
## Results
![image](https://github.com/avengers-p7/Documentation/assets/156056444/9fb6a3d9-3e72-46b4-97ef-07e318160d9b)

![image](https://github.com/avengers-p7/Documentation/assets/156056444/a05f8611-6a83-48fa-a98a-61f2c6b2c6f6)

![image](https://github.com/avengers-p7/Documentation/assets/156056444/e8751504-60c4-45dc-ba2e-7a2d5ebfd465)

![image](https://github.com/avengers-p7/Documentation/assets/156056444/f4125de1-17c7-4252-8e56-8b8fb09d986a)
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
| Statis Code Analysis | https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/08-%20Jenkins/static%20code%20Analysis.md |
| Sonarqube Intergration | https://www.youtube.com/watch?v=KsTMy0920go&t=342s |
| Clean Workspace | https://www.jenkins.io/doc/pipeline/tour/running-multiple-steps/#finishing-up |
| Pipeline (Generic Doc) | https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GenericDoc/jenkinsPipeline.md |
| Create Pipeline (Generic Doc)| https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GenericDoc/pipelinePOC.md |
| Pipeine Syntax | https://www.jenkins.io/doc/book/pipeline/#pipeline-syntax-overview |
| Pipeline Concepts | https://www.jenkins.io/doc/book/pipeline/#pipeline-concepts |

