# Scripted Pipeline For Java Unit Testing

| **Author** | **Created On** | **Last Updated** | **Document Version** |
| ---------- | -------------- | ---------------- | -------------------- |
| **Parasharam Desai** | 08-02-2024 | 08-02-2024 | V1 |

---

# Table of Content

1. [Introduction](#introduction)
2. [Prerequisites](#prerequisites)
3. [Steps](#steps)
4. [Configure Job](#configure-job)
5. [Evaluate Output](#evaluate-output)
6. [Conclusion](#conclusion)
7. [Resource and References](#resource-and-references)
8. [Contact Info](#contact-info)

---

# Introduction

Establishing a Java pipeline for unit testing typically involves leveraging a CI/CD (Continuous Integration/Continuous Deployment) tool to automate the process of building, testing, and potentially deploying your Java application. In this setup, we utilize a Jenkins pipeline for unit testing using Maven and JUnit.

---

# Prerequisites

| Tool | Description |
| ---- | ----------- |
| **Jenkins** | Enables Continuous Integration |
| **JDK17** | Required for compiling Jenkins and Spring Boot projects |
| **Maven** | Handles build automation and dependency management |
| **Junit** | Facilitates Unit testing |

---

**Here we are assuming that you already have a Jenkins pipeline job set up with a Spring Boot project. If not, you can access a public repository on GitHub.**

1. Fork Repository: Fork the repository to your GitHub account.
2. Add Dependency: Add JUnit dependency to the `pom.xml` file. Refer to the documentation [POC for Java Unit Testing](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/03-%20Java%20CI%20checks/Unit-Testing-Poc.md).
3. Add Jenkinsfile: Add a Jenkinsfile at the root level of the project with the provided code.

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

# Configure Job

Set up a Jenkins pipeline job for Jenkins and execute the pipeline.

![image](https://github.com/Parasharam-Desai/working-repo/assets/156056709/9cd5b7d6-96a8-44fd-a1ea-ae5a12a0a8d9)

![image](https://github.com/Parasharam-Desai/working-repo/assets/156056709/e6212ebd-8691-4d38-9d3d-9df065c6d19a)

![image](https://github.com/Parasharam-Desai/working-repo/assets/156056709/9716c6f6-04da-4de2-a5c0-1d4b1543dc6d)

---

# Evaluate Output

Based on the results below, it is evident that all 4 tests were executed successfully with 0 failures and 0 errors.

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
