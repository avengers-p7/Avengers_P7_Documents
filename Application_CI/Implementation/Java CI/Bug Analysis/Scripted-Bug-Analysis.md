# Scripted Pipeline For JAVA Bug Analysis


| **Author** | **Created On** | **Last Updated** | **Document Version** |
| ---------- | -------------- | ---------------- | -------------------- |
| **Parasharam Desai** | 07-02-2024 | 07-02-2024 | V1 |

***


# Table of Contents

1. [Introduction](#introduction)
2. [Prerequisites](#prerequisites)
3. [Steps to run Pipeline](#steps-to-run-pipeline)
4. [Conclusion](#conclusion)
5. [Contact Information](#contact-information)
6. [Resources and References](#resources-and-references)


***
# Introduction
Establishing a Java pipeline for bug analysis typically involves leveraging a CI/CD (Continuous Integration/Continuous Deployment) tool to automate the process of building, testing, and potentially deploying your Java application. Here we will be utilizing the Spotbugs plugin for bug scanning to ensure the quality and reliability of our codebase.
***
# Prerequisites
|    Tool                                   | Description                    |
|-------------------------------------------|----------------------------------|
| **Jenkins** | Enables Continuous Integration |
| **JDK17** | Required for compiling Jenkins and Spring Boot projects |
| **Maven** | Handles build automation and dependency management |
| **Spotbug** | Employed for bug analysis |


***

# Steps to run Pipeline

**1. Fork the repository:** You can Fork the repository from GitHub - [**Repo Link**](https://github.com/Parasharam-Desai/salary-api.git).

**2. The Spotbugs plugin needs to be included in the pom.xml file.**

            <plugin>
                  <groupId>com.github.spotbugs</groupId>
                  <artifactId>spotbugs-maven-plugin</artifactId>
                  <version>4.8.1.0</version>
                  <executions>
                      <execution>
                          <id>spotbugs-check</id>
                          <phase>verify</phase>
                          <goals>
                              <goal>check</goal>
                          </goals>
                      </execution>
                  </executions>
                  <dependencies>
                      <dependency>
                          <groupId>com.github.spotbugs</groupId>
                          <artifactId>spotbugs</artifactId>
                          <version>4.8.1</version>
                      </dependency>
                  </dependencies>
              </plugin>

              
* Include the Spotbugs-maven-plugin within the reporting section. This ensures that running mvn site will generate the Spot Bugs report.

              <reporting>
                  <plugins>
                      <plugin>
                          <groupId>com.github.spotbugs</groupId>
                          <artifactId>spotbugs-maven-plugin</artifactId>
                          <version>4.8.1.0</version>
                      </plugin>
                  </plugins>
              </reporting>
 

**3. Configure Maven tool in Jenkins**

Go to `Dashboard--> Manage Jenkins--> Tools` and configure maven tool.

![image](https://github.com/avengers-p7/Documentation/assets/156056444/d9ff8a0d-900a-4e4b-ac68-34507ef3348b)

**4. Set up Jenkins Pipeline job & Configure your pipeline using the detailed documentation provided in the following link:**
**

**[Reference Link]()**

**5. Now Build Your Pipelne**


        node {
            stage("Git Checkout") {
                git branch: 'main', url: 'https://github.com/Parasharam-Desai/salary-api.git'
            }
            
            stage("Bug Analysis") {
                sh 'mvn compile'
                sh 'mvn spotbugs:spotbugs'
                sh 'mvn site'
            }
            
            stage('Publish HTML Report') {
                step([$class: 'PublishHTMLPublisher', 
                    allowMissing: false,
                    alwaysLinkToLastBuild: true,
                    keepAll: true,
                    reportDir: 'target/site',
                    reportFiles: 'spotbugs.html',
                    reportName: 'SpotBugs Report'
                ])
            }
        }

**Description:**

- `mvn compile`: This command compiles the Java source code in the project.
- `mvn spotbugs:spotbugs`: This command executes the SpotBugs analysis using the SpotBugs Maven plugin. SpotBugs is a static analysis tool that identifies potential bugs in Java code.
- `mvn site`: The Maven site goal generates various reports, including a report for bug analysis.
  


**6. Evaluate Output: Based on the console output provided below, we can infer that there are a few bugs present.**

![image](https://github.com/avengers-p7/Documentation/assets/156056709/353ac994-2300-4b4c-aa3e-ac0eb8cfa63e)


![image](https://github.com/avengers-p7/Documentation/assets/156056709/204c12dc-462c-4319-81bd-68256d4e8cdc)


***

# Conclusion

This pipeline will clone your source code repository, compile the project using Maven, and conduct bug scanning.


# Contact Information

|    Name                                   | Email Address                    |
|-------------------------------------------|----------------------------------|
| **[Parasharam Desai](https://github.com/Parasharam-Desai)** | parasharam.desai.snaatak@mygurukulam.co |

***
# Resources and References

|       **Description**                                   |           **References**                    |
|---------------------------------------------------------|-----------------------------------------------|
| Jenkins Pipeline     | [Jenkins Pipeline Documentation](https://www.jenkins.io/doc/book/pipeline/) |
| Using Spotbug Plugins                 | [Spotbugs Maven Plugin Documentation](https://spotbugs.readthedocs.io/en/latest/maven.html) |
| Guide to use SpotBugs           | [SpotBugs Maven Configuration Guide](https://github.com/find-sec-bugs/find-sec-bugs/wiki/Maven-configuration) |
