# Shared Library 

![image](https://github.com/avengers-p7/Documentation/assets/156057205/5ddddfd1-1ea8-486a-a81e-bcf784346e9a)

***
| Author  | Created on  | Version | Last Updated by | Last Updated on |
| ------  | ----------  | ------- | --------------- | --------------- |
| **Shreya Jaiswal** | **14-02-2024** | **1.0** | **Shreya Jaiswal** | **14-02-2024** |
***

## Table  of Contents

1. [Introduction](#Introduction)
2. [Purpose](#Purpose)
3. [What is Shared Library](#What-is-Shared-Library)
4. [Why Shared Library](#Why-Shared-Library)
5. [Directory Structure](#Directory-Structure)
6. [Flow Diagram](#Flow-Diagram)
7. [Integration With Jenkins Using Jenkinsfile](Integration-With-Jenkins-Using-Jenkinsfile)
8. [Scenarios](#Scenarios)
9. [Conclusion](#Conclusion)
10. [Contact Information](#Contact-Information)
11. [References](#References)
   
***

## Introduction 

Shared libraries are vital components in software development, offering reusable sets of functions and procedures that can be dynamically linked into programs. This documentation aims to provide comprehensive guidance on creating and utilizing shared libraries, covering directory structure, file types, and integration with Jenkins using a Jenkinsfile.

***

# Purpopse

The purpose of shared libraries is to promote modularity, code reuse, and efficient memory usage in software development. They allow developers to encapsulate common functionality into separate modules, which can be shared among multiple programs, thus streamlining development, enhancing maintainability, and reducing memory overhead.

***

## What is Shared Library

A shared library, also known as a dynamic link library (DLL) on Windows or a shared object (SO) on Unix-like systems, contains compiled code that can be loaded into memory and executed by multiple programs simultaneously. It typically includes functions, procedures, and data structures that provide specific functionality.

***

## Why Shared Library

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
| **src/** | Contains the source code files (e.g., Groovy scripts) implementing the library's functionality. |
| **vars/** |  Stores global variables and functions that can be directly called from Jenkins pipelines. |
| **resources/** | Optional directory for storing additional resources such as configuration files, templates, or documentation. |

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






