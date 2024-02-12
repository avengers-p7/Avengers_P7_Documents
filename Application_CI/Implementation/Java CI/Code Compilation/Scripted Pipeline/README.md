# Java Code Compilation(Scripted Pipeline)

| Author                                                           | Created on  | Version    | Last Updated by | Last Updated on |
| ---------------------------------------------------------------- | ----------- | ---------- | --------------- | --------------- |
| **[Harshit Singh](https://github.com/Panu-S-Harshit-Ninja-07)**  | 02-02-2024  | 1.0        | Harshit Singh   | 11-02-2024      |


## Table  of Contents

1. [Introduction](#Introduction)
2. [What is Scripted Pipeline](#What-is-Scripted-Pipeline)
3. [Prerequisites](#Prerequisites)
4. [Flow Diagram](#Flow-Diagram)
5. [Runtime Prerequisites](#Runtime-Prerequisites)
6. [Pipeline Setup](#Pipeline-Setup)
7. [Contact Information](#Contact-Information)
8. [References](#References)
***

## Introduction 

The process of code compilation involves converting high-level programming code, such as Java, C++, or Python, into machine-readable instructions or bytecode. This transformation is carried out by a compiler, which is a specialized tool designed to translate human-readable source code into an executable format.
Here we are using maven compiler to convert of code into  bytecode.

**For more information visit the below document link:**

[\[ Reference Doc \]](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/03-%20Java%20CI%20checks/Code%20Complication.md)

In this task, we are using Scripted Pipeline.
***
## What is Scripted Pipeline

A Scripted Pipeline in Jenkins is a Groovy-based approach to defining continuous integration and continuous delivery (CI/CD) pipelines. It allows users to write pipeline scripts using Groovy syntax, providing full flexibility and customization for defining build, test, and deployment stages. Scripted Pipelines enable users to incorporate conditional logic, loops, and functions within the pipeline script to handle complex workflows and custom requirements. While offering extensive power and flexibility, Scripted Pipelines require users to have knowledge of Groovy programming and scripting concepts. They are well-suited for projects with intricate build processes or those requiring advanced automation and customization capabilities.

**For more information visit the below document link:**

[\[ Reference Doc \]](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GenericDoc/jenkinsPipeline.md )

***

## Prerequisites

| Tool | Description |
| ---- | ----------- |
| **Jenkins(2.426.3)** | To build our pipeline |

> [!Important]
> I have installed the plugin bundle provided by Jenkins during setup. If you have not done the same, you may encounter plugin errors.

***
## Flow Diagram
![image](https://github.com/avengers-p7/Documentation/assets/156056444/4d3b2437-150d-4535-bbc6-932f88c1e1d6)
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

![image](https://github.com/avengers-p7/Documentation/assets/156056444/a9819de7-2f53-4bb1-a2c8-9b25ff0a5304)

5. **Now Build your Pipeline**
![image](https://github.com/avengers-p7/Documentation/assets/156056444/5daa7a40-6aed-4cc1-803f-ecc75d335202)
***
## Console Output
![image](https://github.com/avengers-p7/Documentation/assets/156056444/bbe9072e-bfb4-4532-8489-899e81c62037)

![image](https://github.com/avengers-p7/Documentation/assets/156056444/38497c54-ab1a-4f41-ab3b-e37479302b99)

![image](https://github.com/avengers-p7/Documentation/assets/156056444/c1f73133-aa3d-43fd-b489-6d0d22cbb6cb)


***
## [Pipeline](https://github.com/avengers-p7/Jenkinsfile/blob/main/Declarative%20Pipeline/Java/CodeCompilation/Jenkinsfile)

```shell
node {
    try {
        stage('Checkout GIT') {
            checkout scm: [
                $class: 'GitSCM',
                branches: [[name: '*/main']],
                userRemoteConfigs: [[url: 'https://github.com/Panu-S-Harshit-Ninja-07/OT-Salary-API.git']]
            ]
            sh 'ls $WORKSPACE/'
        }
        
        stage('Starting Code Compilation') {
            echo 'Starting Java Code Compilation..........'
            sh 'mvn clean compile'
        }
        echo 'Compiled Successfully'
    } catch (e) {
        echo 'Compilation Failed'
        cleanWs()
        throw e
    } finally {
        def currentResult = currentBuild.result ?: 'SUCCESS'
        if ((currentResult == 'UNSTABLE')||(currentResult == 'ABORTED')) {
            cleanWs()
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
