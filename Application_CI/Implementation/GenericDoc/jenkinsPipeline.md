# Jenkins Pipeline and Setup

| Author                                                           | Created on  | Version    | Last Updated by | Last Updated on |
| ---------------------------------------------------------------- | ----------- | ---------- | --------------- | --------------- |
| **[Harshit Singh](https://github.com/Panu-S-Harshit-Ninja-07)**  | 07-02-2024  | 1.0        | Harshit Singh   | 09-02-2024      |


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

A _**job**_ in Jenkins is a user-specified description of work, typically divided into sequential steps. For example, a job may fetch source code from a Git repository, compile it using the configured compiler, run it inside a staging environment, examine the output for any errors, and send an email notification to the user.

Jenkins uses projects (also known as "**jobs**") to perform its work. Projects are defined and run by Jenkins users. Jenkins offers several different types of projects, including:

- [Pipeline](https://www.jenkins.io/doc/book/pipeline/)
- [Multibranch Pipeline](https://www.jenkins.io/doc/book/pipeline/multibranch/)
- [Organization folders](https://www.jenkins.io/doc/book/pipeline/multibranch/#organization-folders)
- [Freestyle](https://phoenixnap.com/kb/jenkins-build-freestyle-project#:~:text=Jenkins%20freestyle%20projects%20allow%20users,steps%20and%20post%2Dbuild%20actions.)
- [Multi-configuration(matrix)](https://plugins.jenkins.io/matrix-project)
- [Maven](https://plugins.jenkins.io/maven-plugin)
- [External job](https://plugins.jenkins.io/external-monitor-job)

## What is Jenkins Pipeline

A Jenkins pipeline is a set of plug-ins to create automated, recurring workflows that constitute CI/CD pipelines. A Jenkins pipeline includes all the tools you need to orchestrate testing, merging, packaging, shipping, and code deployment.

A pipeline is typically divided into multiple stages and steps, with each step representing a single task and each stage grouping together similar steps. For example, you may have “Build”, “Test”, and “Deploy” stages in your pipeline. You can also run existing jobs within a pipeline.

***
## Why Pipeline?
Jenkins is, fundamentally, an automation engine which supports a number of automation patterns. Pipeline adds a powerful set of automation tools onto Jenkins, supporting use cases that span from simple continuous integration to comprehensive CD pipelines. By modeling a series of related tasks, users can take advantage of the many features of Pipeline:

| Features | Description |
| --------- | ---------- |
|Code | Pipelines are implemented in code and typically checked into source control, giving teams the ability to edit, review, and iterate upon their delivery pipeline.
| Durable | Pipelines can survive both planned and unplanned restarts of the Jenkins controller.
| Pausable | Pipelines can optionally stop and wait for human input or approval before continuing the Pipeline run.
| Versatile | Pipelines support complex real-world CD requirements, including the ability to fork/join, loop, and perform work in parallel.
| Extensible | The Pipeline plugin supports custom extensions for integration with other plugins. |

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
