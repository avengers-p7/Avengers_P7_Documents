# Java Code Compilation Pipeline

| Author                                                           | Created on  | Version    | Last Updated by | Last Updated on |
| ---------------------------------------------------------------- | ----------- | ---------- | --------------- | --------------- |
| **[Harshit Singh](https://github.com/Panu-S-Harshit-Ninja-07)**  | 02-02-2024  | 1.0        | Harshit Singh   | 04-02-2024      |


## Table  of Contents

1. [Introduction](#Introduction)
2. [What](#What)
3. [Why](#Why)
4. [Infra Diagram](#Infra-Diagram)
5. [Description](#Description)
6. [Contact Information](#Contact-Information)
7. [References](#References)
***

## Introduction 

The process of code compilation involves converting high-level programming code, such as Java, C++, or Python, into machine-readable instructions or bytecode. This transformation is carried out by a compiler, which is a specialized tool designed to translate human-readable source code into an executable format.
Here we are using maven compiler to convert of code into  bytecode.

### For more information visit the below document link:

#### [\[ Reference Doc \]](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/03-%20Java%20CI%20checks/Code%20Complication.md)
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
## Steps to run Pipeline
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
![image](https://github.com/avengers-p7/Documentation/assets/156056444/c9261b85-b99c-4264-88c8-028b5a5d9d20)

3. **Configure Maven tool in Jenkins**
Go to `Dashboard--> Manage Jenkins--> Tools` and configure maven tool.

![image](https://github.com/avengers-p7/Documentation/assets/156056444/d9ff8a0d-900a-4e4b-ac68-34507ef3348b)

4. **Create Jenkins Pipeline job**
Go to your Jenkins `Dashboard`, 

![image](https://github.com/avengers-p7/Documentation/assets/156056444/e5cd0f81-c0d7-46fa-bbba-ab6bcaae5755)

![image](https://github.com/avengers-p7/Documentation/assets/156056444/7500f744-07c5-4579-a823-1a4383ac3fd8)

![image](https://github.com/avengers-p7/Documentation/assets/156056444/ac4ad734-fe8d-40ac-82c2-a4676cdf295a)

5. **Configure  your pipeline**
Go to `Dashboard--> Pipeline_job--> Configure` then add your Jenkinsfile repository link and configure it.
 
![image](https://github.com/avengers-p7/Documentation/assets/156056444/fb9d1964-e080-4cf1-8ddd-b71a90b91db3)

![image](https://github.com/avengers-p7/Documentation/assets/156056444/bef7d4a3-5873-414b-bb89-484b452dd0cb)

6. **Now Build your Pipeline**


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
## Contact Information

|     Name         | Email  |
| -----------------| ------------------------------------ |
| Harshit Singh    | harshit.singh.snaatak@mygurukulam.co |
***

## References

| Description                                   | References  
| --------------------------------------------  | -------------------------------------------------|
| HA  reference doc | https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/DevOps%20Practices/High%20Availability/README.md |
| What is HA?                                   | https://avinetworks.com/glossary/high-availability/ |
| Clustering in Data Center Edition             | https://docs.sonarsource.com/sonarqube/latest/setup-and-upgrade/configure-and-operate-a-cluster/ |
| Installation Sonarqube                        | https://docs.sonarsource.com/sonarqube/latest/setup-and-upgrade/install-the-server/introduction/ |
| High Availability and Scalability - ELB & ASG | https://zhenye-na.github.io/aws-certs-cheatsheet/posts/ha-elb-asg/#:~:text=Auto%20Scaling%20Group%20(ASG),instances%20to%20a%20load%20balancer |
| ”Don’t let the fact that SonarQube bundles-in the H2 database tempt you to skip this step. H2 is included as a courtesy for initial testing only and is not for long-term, production use. If you try to use H2 as your production database, we guarantee you’ll be disappointed—not least because you cannot upgrade a SonarQube database that’s stored in H2.”<| https://livebook.manning.com/book/sonarqube-in-action/appendix-a/ |
