# Shared Library 

<img width="600" alt="image" src="https://github.com/avengers-p7/Documentation/assets/156057205/5ddddfd1-1ea8-486a-a81e-bcf784346e9a">

***

| Author  | Created on  | Version | Last Updated by | Last Updated on |
| ------  | ----------  | ------- | --------------- | --------------- |
| **Shreya Jaiswal** | **14-02-2024** | **1.0** | **Shreya Jaiswal** | **14-02-2024** |
***

# Table  of Contents

1. [Introduction](#Introduction)
2. [Purpose](#Purpose)
3. [What is Shared Library](#What-is-Shared-Library)
4. [Why Shared Library](#Why-Shared-Library)
5. [Directory Structure](#Directory-Structure)
         -  [src File Structure](#src-File-Structure)
         -  [vars File Structure](#vars-File-Structure)
         -  [resources File Structure](#resources-File-Structure)
6. [Flow Diagram](#Flow-Diagram)
7. [Integration With Jenkins Using Jenkinsfile](#Integration-With-Jenkins-Using-Jenkinsfile)
8. [Advantages](#Advantages)
9. [Disadvantages](#Disadvantages)
10. [Scenarios](#Scenarios)
11. [Conclusion](#Conclusion)
12. [Contact Information](#Contact-Information)
13. [Reference](#Reference)
   
***

# Introduction 

Shared libraries are vital components in software development, offering reusable sets of functions and procedures that can be dynamically linked into programs. This documentation aims to provide comprehensive guidance on creating and utilizing shared libraries, covering directory structure, file types, and integration with Jenkins using a Jenkinsfile.

***

# Purpose

The purpose of shared libraries is to promote modularity, code reuse, and efficient memory usage in software development. They allow developers to encapsulate common functionality into separate modules, which can be shared among multiple programs, thus streamlining development, enhancing maintainability, and reducing memory overhead.

***

# What is Shared Library

A shared library, also known as a dynamic link library (DLL) on Windows or a shared object (SO) on Unix-like systems, contains compiled code that can be loaded into memory and executed by multiple programs simultaneously. It typically includes functions, procedures, and data structures that provide specific functionality.

***

# Why Shared Library

| Features | Description |
| --------- | ---------- |
| **Code Reusability** | Shared libraries facilitate code reuse by allowing developers to encapsulate common functionality into reusable modules.|
| **Modularity** | They promote modularity by breaking down complex systems into smaller, manageable components. |
| **Memory Efficiency** | Shared libraries reduce memory overhead by allowing multiple programs to share the same code and resources. |
| **Maintainability** | They enhance maintainability by centralizing common functionality, making it easier to update and manage. |

***

# Directory Structure 

| **Directory** | **Description** |
| ------------- | --------------- |
| **src/** |  This directory contains the source code files for the shared library. It typically includes Groovy scripts or other programming language files that implement the functionality provided by the library. |
| **vars/** | This directory stores global variables and functions that can be directly called from Jenkins pipelines using the **@Library** annotation. |
| **resources/** | This directory contains additional resources used by the shared library, such as configuration files, templates, or documentation. |

***

## src File Structure

**Example: Let's assume we are creating a shared library for performing string manipulation operations.**

```shell
// src/StringUtils.groovy

package com.example.sharedlib

class StringUtils {
    static String reverse(String input) {
        return input.reverse()
    }
    
    static int countWords(String input) {
        return input.split("\\s+").size()
    }
}
```
> [!Note]
> `StringUtils.groovy` is a source code file located in the src/ directory. It contains a class named StringUtils with static methods for performing string manipulation operations.The `reverse` method reverses a given string, while the countWords method calculates the number of words in a string.

***

## vars File Structure

**Example: We'll define a global function to print a greeting message.**

```shell
// vars/greet.groovy

def call(String name) {
    echo "Hello, ${name}! Welcome to our shared library."
}
```
> [!Note]
> `greet.groovy` is a global function file located in the `vars/` directory. It defines a single function named `call` that prints a greeting message.

***

## resources File Structure

**Example: Let's include a configuration file for defining default settings.**

```shell
# resources/config.properties

# Default configuration settings
app.mode = production
app.timeout = 3000
```
> [!Note]
> `config.properties` is a configuration file located in the `resources/` directory. It contains key-value pairs defining default configuration settings for the shared library.

***

# Integration With Jenkins Using Jenkinsfile

To integrate a shared library with Jenkins using a Jenkinsfile, follow these steps:

| **Steps** | **Description** |
| --------- | --------------- |
| **Create Jenkinsfile** | Define the pipeline stages, including checkout, build, test, and deploy stages, in the Jenkinsfile. |
| **Configure Jenkins Pipeline** |  Configure Jenkins to use the Jenkinsfile from your version control system (e.g., Git). |
| **Load Shared Library** | Load the shared library in the Jenkinsfile using the **@Library** annotation. |
| **Utilize Shared Library Functions** | Call the functions and variables defined in the shared library from the Jenkins pipeline script. |
| **Trigger Pipeline** | Trigger the Jenkins pipeline manually or automatically based on events  |

***

## Jenkinsfile Structure

```shell
// Jenkinsfile

pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                // Checkout source code from version control
                git 'https://github.com/your/shared-library.git'
            }
        }
        
        stage('Build') {
            steps {
                // Build steps if required (e.g., compilation)
                echo 'Building shared library...'
            }
        }
        
        stage('Test') {
            steps {
                // Run unit tests
                echo 'Running unit tests...'
                sh './gradlew test' // Example command for running tests using Gradle
            }
        }
        
        stage('Deploy') {
            steps {
                // Deploy the shared library (optional)
                echo 'Deploying shared library...'
                sh './gradlew publish' // Example command for publishing library artifacts
            }
        }
    }
    
    post {
        always {
            // Clean up steps (optional)
            echo 'Cleaning up...'
        }
    }
}
```
| **Steps** |
| --------- |
| **We define a pipeline with stages for checkout, build, test, and deploy.** |
| **In the Checkout stage, we fetch the source code of the shared library from the version control system.** |
| **In the Build stage, you can include any necessary build steps, such as compilation or packaging the library.** |
| **The Test stage runs unit tests to ensure the correctness of the shared library.** |
| **In the Deploy stage, you can deploy the shared library to a repository or artifact storage.** |
| **Finally, in the post section, you can include any cleanup steps that should be executed after the pipeline completes, such as cleaning up temporary files.** |

***

# Advantages

| **Advanatge** | **Description** |
| ------------- | --------------- |
| **Code Reusability** | Shared libraries promote code reusability by encapsulating common functionality into reusable modules. This reduces duplication of code across projects and promotes consistent implementation of features. |
| **Enhanced Collaboration** | Shared libraries encourage collaboration among developers by providing a centralized repository of reusable components. This fosters knowledge sharing, promotes best practices, and accelerates development cycles. |
| **Standardization** | Shared libraries help standardize development practices by providing a common set of functions, interfaces, and conventions. This streamlines development workflows, improves code consistency, and enhances overall software quality. |

***

# Disadvantages

| **Disadvantage** | **Description** |
| ---------------- | --------------- |
| **Dependency Management** | Shared libraries introduce dependencies between projects, which can complicate dependency management and increase the risk of version conflicts. Careful versioning and dependency tracking are necessary to mitigate these issues. |
| **Maintenance Burden** | Maintaining shared libraries involves managing updates, addressing bug fixes, and ensuring backward compatibility. This maintenance burden can increase over time, particularly for widely used libraries with a large user base. |
| **Performance Overhead** |  Dynamically linking shared libraries at runtime may incur a slight performance overhead compared to statically linking libraries. However, modern runtime environments and optimizations mitigate this overhead to a large extent. |

# Scenarios

| **Scenario** | **Description** |
| ------------ | --------------- |
| **Continuous Integration/Continuous Deployment (CI/CD)** | Shared libraries are essential for implementing CI/CD pipelines in Jenkins, enabling automated builds, tests, and deployments. |
| **Multi-Project Environments** |  In environments with multiple projects, shared libraries simplify the management of common functionality across projects. |
| **Version Control** | Shared libraries should be version-controlled to track changes, facilitate collaboration, and ensure reproducibility. |

***

# Conclusion

Shared libraries are invaluable tools in software development, offering numerous benefits such as code reusability, modularity, and memory efficiency. By following the recommended directory structure, including essential file types, and integrating with Jenkins using a Jenkinsfile, developers can effectively create, manage, and utilize shared libraries in their projects, promoting efficient development practices and enhancing overall productivity.

***

# Contact Information

| **Name** | **Email Address** |
| -------- | ----------------- |
| **Shreya Jaiswal** | shreya.jaiswal.snaatak@mygurukulam.co |

***

# Reference

| **Source** | **Description** |
| ---------- | --------------- |
| [Link](https://keentolearn.medium.com/how-to-improve-your-jenkins-builds-with-shared-libraries-5e225b7435fb#:~:text=A%20shared%20library%20in%20Jenkins,efficient%20and%20easier%20to%20maintain.) | Link For Shared Library |
| [Link](https://phoenixnap.com/kb/jenkins-shared-library) | Reference Link For Understanding the concept of Shared Library |
| [Link](https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqbHluUi1nZVZJcmRLai1COXZxMVRjcERlLXhXZ3xBQ3Jtc0trT05uZ3dWaG1sZmZHYXVQeWluVnl2ZHF6c3BYdGlyUE1OREh3NkRFb0dFMG5VQWxyMXhNRHRnWkxBY2hKTnB5UkJySW9BOVJkczJzRlZiZm92NVdWNHg1ZEJLeU5tRmFlS2sxWDZJUmE0YThuQ1JPQQ&q=https%3A%2F%2Fwww.jenkins.io%2Fdoc%2Fbook%2Fpipeline%2Fshared-libraries%2F&v=Wj-weFEsTb0) | Reference Link |
| [Link](https://www.youtube.com/watch?v=pQUDhOMZiZQ) | Video Reference For Shared Library |
| [Link](https://youtu.be/Wj-weFEsTb0?feature=shared) | Video Reference For Shared Library |






