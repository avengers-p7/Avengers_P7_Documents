# Scripted Pipeline For Java Unit Testing

| **Author** | **Created On** | **Last Updated** | **Document Version** |
| ---------- | -------------- | ---------------- | -------------------- |
| **Parasharam Desai** | 08-02-2024 | 08-02-2024 | V1 |

---

# Table of Content

1. [Introduction](#introduction)
2. [What is Scripted Pipeline](#what-is-scripted-pipeline)
3. [Prerequisites](#prerequisites)
4. [Flow Diagram](#Flow-Diagram)
5. [Steps](#steps)
6. [Evaluate Output](#evaluate-output)
7. [Conclusion](#conclusion)
8. [Contact Info](#contact-info)
9. [Resource and References](#resource-and-references)


---

# Introduction

Establishing a Java pipeline for unit testing typically involves leveraging a CI/CD (Continuous Integration/Continuous Deployment) tool to automate the process of building, testing, and potentially deploying your Java application. In this setup, we utilize a Jenkins pipeline for unit testing using Maven and JUnit.

If you want to learn more about Unit Testing, refer to this detailed documentation: [Unit Testing Documentation](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/03-%20Java%20CI%20checks/Unit%20Testing/README.md)


# What is Scripted Pipeline
A Scripted Pipeline in Jenkins is a Groovy-based approach to defining continuous integration and continuous delivery (CI/CD) pipelines. It allows users to write pipeline scripts using Groovy syntax, providing full flexibility and customization for defining build, test, and deployment stages. Scripted Pipelines enable users to incorporate conditional logic, loops, and functions within the pipeline script to handle complex workflows and custom requirements. While offering extensive power and flexibility, Scripted Pipelines require users to have knowledge of Groovy programming and scripting concepts. They are well-suited for projects with intricate build processes or those requiring advanced automation and customization capabilities.

To know more about pipelines please follow this [Reference Link](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GenericDoc/jenkinsPipeline.md)

---

# Prerequisites

| Tool | Description |
| ---- | ----------- |
| **Jenkins (2.426.3)** | Enables Continuous Integration |
| **Java 17** | Required for compiling Jenkins and Spring Boot projects |
| **Maven(3.6.9)** | Handles build automation and dependency management |
| **Junit (4.12)** | Facilitates Unit testing |

***
# Flow Diagram

![image](https://github.com/avengers-p7/Documentation/assets/156056709/cb0fe70e-4a99-49ed-a057-de4363591c23)


---

# Steps to run Pipeline

**1. Fork Repository:** Fork the repository to your GitHub account. 
[Repo-Link](https://github.com/Parasharam-DevOps/salary-api.git)

**2. Add Dependency:** Add JUnit dependency to the `pom.xml` file. Refer to the documentation [POC for Java Unit Testing](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/03-%20Java%20CI%20checks/Unit%20Testing/README.md).

[Click here for reference](https://github.com/Parasharam-DevOps/salary-api/blob/main/pom.xml) to view the pom.xml file.

**3. Configure Maven tool in Jenkins**

Go to `Dashboard--> Manage Jenkins--> Tools` and configure maven tool.

![image](https://github.com/avengers-p7/Documentation/assets/156056444/d9ff8a0d-900a-4e4b-ac68-34507ef3348b)

**4. Set up Jenkins Pipeline job & Configure your pipeline using the detailed documentation provided in the following link:**

**[Reference Link](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GenericDoc/jenkinsPipeline.md)**


**5. Now Build Your Pipelne**

         node {
             // Define tools
             def mvnHome = tool 'mvn'
         
             // Checkout stage
             stage('Checkout') {
                 git branch: 'main', url: 'https://github.com/Parasharam-DevOps/salary-api.git'
             }
         
             // Test stage
             stage('Test') {
                 echo "Executing Java Unit Testing"
                 sh "${mvnHome}/bin/mvn test"
             }
         }
---

# Evaluate Output

Based on the results below, it is evident that all 4 tests were executed successfully with 0 failures and 0 errors.

![image](https://github.com/avengers-p7/Documentation/assets/156056709/b3229d77-7f26-4eaa-bc6e-5f37884f10e4)

![image](https://github.com/avengers-p7/Documentation/assets/156056709/3adc4cae-6034-42c8-bff8-40b098e42f2d)

---

# Conclusion

This pipeline will check out your source code, build the project using Maven, and run JUnit tests.

---

# Contact Information

| Name | Email Address |
| ---- | ------------- |
| [Parasharam Desai](https://github.com/Parasharam-Desai) | parasharam.desai.snaatak@mygurukulam.co |

---

# Resources and References

| Description | References |
| ----------- | ---------- |
| Jenkins Pipeline | [Jenkins Pipeline Documentation](https://www.jenkins.io/doc/book/pipeline/) |
| Junit-POC | [Detailed POC Documentation](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/03-%20Java%20CI%20checks/Unit%20Testing/POC.md) |
| JUnit Setup Maven - JUnit 4 and JUnit 5 | [Digital Ocean ](https://www.digitalocean.com/community/tutorials/junit-setup-maven) |
| Jenkinsfile Code | [Jenkinsfile](https://github.com/avengers-p7/Jenkinsfile/blob/main/Scripted%20Pipeline/Java/UnitTesting/Jenkinsfile) |
|Pipeline Generic Doc|[Link](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GenericDoc/jenkinsPipeline.md)|
| Set up Jenkins Pipeline job & Configure your pipeline |[Link](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GenericDoc/jenkinsPipeline.md)|



