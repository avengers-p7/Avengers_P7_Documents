# Declarative Pipeline For Java Unit Testing

| **Author** | **Created On** | **Last Updated** | **Document Version** |
| ---------- | -------------- | ---------------- | -------------------- |
| **Parasharam Desai** | 08-02-2024 | 08-02-2024 | V1 |

---

# Table of Content

1. [Introduction](#introduction)
2. [Prerequisites](#prerequisites)
3. [Steps](#steps)
4. [Evaluate Output](#evaluate-output)
5. [Conclusion](#conclusion)
6. [Contact Info](#contact-info)
7. [Resource and References](#resource-and-references)


---

# Introduction

Establishing a Java pipeline for unit testing typically involves leveraging a CI/CD (Continuous Integration/Continuous Deployment) tool to automate the process of building, testing, and potentially deploying your Java application. In this setup, we utilize a Jenkins pipeline for unit testing using Maven and JUnit.

If you want to learn more about Unit Testing, refer to this detailed documentation: [Unit Testing Documentation](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/03-%20Java%20CI%20checks/Unit%20Testing/README.md)


---

# Prerequisites

| Tool | Description |
| ---- | ----------- |
| **Jenkins** | Enables Continuous Integration |
| **JDK17** | Required for compiling Jenkins and Spring Boot projects |
| **Maven** | Handles build automation and dependency management |
| **Junit** | Facilitates Unit testing |

---

# Steps to run Pipeline

**1. Fork Repository:** Fork the repository to your GitHub account.

**2. Add Dependency:** Add JUnit dependency to the `pom.xml` file. Refer to the documentation [POC for Java Unit Testing](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/03-%20Java%20CI%20checks/Unit-Testing-Poc.md).


**3. Configure Maven tool in Jenkins**

Go to `Dashboard--> Manage Jenkins--> Tools` and configure maven tool.

![image](https://github.com/avengers-p7/Documentation/assets/156056444/d9ff8a0d-900a-4e4b-ac68-34507ef3348b)

**4. Set up Jenkins Pipeline job & Configure your pipeline using the detailed documentation provided in the following link:**

**[Reference Link]()**


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

![Screenshot from 2024-02-07 19-22-56](https://github.com/Parasharam-Desai/working-repo/assets/156056709/92b745e2-26cf-4026-ac70-e6ddd53fc1ea)

![Screenshot from 2024-02-07 19-23-45](https://github.com/Parasharam-Desai/working-repo/assets/156056709/72c47e89-bcb7-46c2-97ad-27e573d59885)

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
| JUnit Setup Maven - JUnit 4 and JUnit 5 | Digital Ocean | [Junit Setup Maven](https://www.digitalocean.com/community/tutorials/junit-setup-maven) |
