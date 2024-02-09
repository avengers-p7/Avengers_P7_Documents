# Declarative Pipeline For Java Unit Testing

| **Author** | **Created On** | **Last Updated** | **Document Version** |
| ---------- | -------------- | ---------------- | -------------------- |
| **Parasharam Desai** | 08-02-2024 | 08-02-2024 | V1 |

---

# Table of Content

1. [Introduction](#introduction)
2. [Prerequisites](#prerequisites)
3. [Flow Diagram](#Flow-Diagram)
4. [Steps](#steps)
5. [Evaluate Output](#evaluate-output)
6. [Conclusion](#conclusion)
7. [Contact Info](#contact-info)
8. [Resource and References](#resource-and-references)


---

# Introduction

Establishing a Java pipeline for unit testing typically involves leveraging a CI/CD (Continuous Integration/Continuous Deployment) tool to automate the process of building, testing, and potentially deploying your Java application. In this setup, we utilize a Jenkins pipeline for unit testing using Maven and JUnit.

A Jenkins pipeline is a way to define your Jenkins pipeline using Groovy code. It allows you to describe your build process using a scripting language instead of a visual interface.
To know more about pipelines please follow this **[Reference Link](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GenericDoc/jenkinsPipeline.md
)**

If you want to learn more about Unit Testing, refer to this detailed documentation: [Unit Testing Documentation](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/03-%20Java%20CI%20checks/Unit%20Testing/README.md)


---

# Prerequisites

| Tool | Description |
| ---- | ----------- |
| **Jenkins (2.426.3)** | Enables Continuous Integration |
| **Java 17** | Required for compiling Jenkins and Spring Boot projects |
| **Maven(3.6.9)** | Handles build automation and dependency management |
| **Junit (4.12)** | Facilitates Unit testing |


# Flow Diagram

![image](https://github.com/avengers-p7/Documentation/assets/156056709/ec329fc3-8ad3-4101-b359-881f2a59eaf6)



---

# Steps to run Pipeline

**1. Fork Repository:** Fork the repository to your GitHub account.

**2. Add Dependency:** Add JUnit dependency to the `pom.xml` file. Refer to the documentation [POC for Java Unit Testing](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/03-%20Java%20CI%20checks/Unit-Testing-Poc.md).

[Click here for reference](https://github.com/Parasharam-DevOps/salary-api/blob/main/pom.xml) to view the pom.xml file.

**3. Configure Maven tool in Jenkins**

Go to `Dashboard--> Manage Jenkins--> Tools` and configure maven tool.

![image](https://github.com/avengers-p7/Documentation/assets/156056444/d9ff8a0d-900a-4e4b-ac68-34507ef3348b)

**4. Set up Jenkins Pipeline job & Configure your pipeline using the detailed documentation provided in the following link:**

**[Reference Link](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GenericDoc/jenkinsPipeline.md)**

**5. Now Build Your Pipelne**


                   pipeline {
                                  agent any
                                  tools {
                                      maven "mvn"
                                  }
                                  stages {
                                      stage('Checkout') {
                                          steps {
                                              git branch: 'main', url: 'https://github.com/Parasharam-DevOps/salary-api.git'
                                          }
                                      }
                                      stage('Test') {
                                          steps {
                                              echo "Executing Java Unit Testing"
                                              sh 'mvn test'
                                          }
                                      }
                                  }
                              }

---

# Evaluate Output

Based on the results below, it is evident that all 4 tests were executed successfully with 0 failures and 0 errors.

![image](https://github.com/avengers-p7/Documentation/assets/156056709/d2c75a85-6d40-4ec0-9d8d-334e77b37cc7)

![image](https://github.com/avengers-p7/Documentation/assets/156056709/9a36ef04-a73d-4241-866b-a70a792f05f3)

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
