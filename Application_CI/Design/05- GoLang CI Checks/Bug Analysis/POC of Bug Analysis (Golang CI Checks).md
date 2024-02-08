# Bugs analysis (GoLang CI Checks) (POC)

<img width="360" length="100" alt="Golang" src="https://github.com/avengers-p7/Documentation/assets/156056413/56e9dd64-9654-449c-be6d-4212de6aca71">

***

| Author                 | Created On | Last Updated | Document Version | Last Updated By |
| ---------------------- | ---------- | ------------ | ---------------- | --------------- |
| Vishal Kumar Kesarwani | 29-01-2024 | 07-02-2024   | v1               |  Vishal         |

## Table of Contents

+ [Introduction](#introduction)
+ [Bug Analysis](#Bug-Analysis)
+ [Flow Diagram](#Flow-Diagram)
+ [Proof of Concept](#Proof-of-Concept)
+ [Conclusion](#Conclusion)
+ [Contact Information](#contact-information)
+ [Resources and References](#resources-and-references)

***
## Introduction

<img width="360" length="100" alt="Golang" src="https://github.com/avengers-p7/Documentation/assets/156056413/b415529d-49f0-44dc-b07c-52a67228c78e">

Golangci-lint is just a fast linter for Go. Now, a linter is a tool that inspects code files using a set of rules that identify issues that lead to misunderstanding, result in unexpected outcomes, or make the code harder to read. Additionally, linter can aid in identifying potential defects in the code, such as undeclared variable assignment, which can result in runtime errors, retrieving the value from a global variable, which complicates debugging, and other issues.  
For more information cilck [**here**](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/05-%20GoLang%20CI%20Checks/Bug%20Analysis/Introduction%20of%20Bugs%20analysis%20(GoLang%20CI%20Checks).md)
***
## Bug Analysis

<img width="360" length="100" alt="Golang" src="https://github.com/avengers-p7/Documentation/assets/156056413/642caa0f-da7d-4cf9-afe6-364f765294c5">

In software development, a 'bug' refers to an error, flaw, or unexpected behavior in a software application. Bugs can manifest in various forms, such as incorrect output, system crashes, or unexpected behavior. The goal of bug analysis is to identify, categorize, and understand these issues to facilitate effective resolution.  
For more information cilck [**here**](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/05-%20GoLang%20CI%20Checks/Bug%20Analysis/Introduction%20of%20Bugs%20analysis%20(GoLang%20CI%20Checks).md)
***
## Flow-Diagram

![Screenshot from 2024-02-08 00-20-57](https://github.com/avengers-p7/Documentation/assets/156056413/780133ac-387f-47c7-8c20-8c48cf2c3db2)

***
## Proof of Concept
### Pre-Requisites
| **Pre-Requisites** | **Version** |
| ------------------ | ----------- |
| Golang | 1.21.6 |
| GoLangCI-lint | 1.55.2
***
### POC
**Installation Pre-Requisites**
  * Install go
    ```shell
    sudo apt update
    sudo snap install go --classic
    ```
    <img width="360" length="100" alt="Golang" src="https://github.com/avengers-p7/Documentation/assets/156056413/0cca8aab-35f2-4557-8007-a38d99f19d7f">

  * Install GoLangCI-lint
    ```shell
    sudo snap install golangci-lint
    ```
     <img width="560" length="100" alt="Golang" src="https://github.com/avengers-p7/Documentation/assets/156056413/5c737e57-58c1-4a7e-bd58-9ccda049811d">
***

### How to Use golangci-lint?

  * Now, since we are installing through snap we need to ensure that /snap/bin is included in our PATH environment variable. To do     so we can run this command
    ```shell
    export PATH=$PATH:/snap/bin
    ```
    ![Screenshot from 2024-02-07 15-36-27](https://github.com/avengers-p7/Documentation/assets/156056413/126dfd37-d1ca-4091-abe6-156c04b3dba5)
  * Clone the Repo
    ```shell
    git clone https://github.com/OT-MICROSERVICES/employee-api.git
    cd employee-api/
    ```
    <img width="560" length="100" alt="Golang" src="https://github.com/avengers-p7/Documentation/assets/156056413/7cccbc57-cd3c-4eef-8986-70eb07e4b59e">

  * Now, if we run golangci-lint for some project/directory it will use the enabled linters. To run the golangci-lint for your         Golang project directory, run the following command.
    ```shell
    golangci-lint run ./...
    ```
    <img width="760" length="100" alt="Golang" src="https://github.com/avengers-p7/Documentation/assets/156056413/c9b0a220-339b-4399-808a-23d2f358bf50">
    
***

### Generate HTML Report   
   * Generate Report
     ```shell 
      golangci-lint run ./... --out-format html > report.html
     ```
   * [**HTML Report**](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/05-%20GoLang%20CI%20Checks/Bug%20Analysis/Bug%20Analysis%20report.html)
    
    
## Conclusion
we covered the process of installing Go first as a prerequisite. We then covered installation of golangci-lint and finally how can it be configured specifically and then be used in our Go programs to lint our code. By having golangci-lint at our disposal, We can ensure your code is top-notch and easy to understand. With Go and golangci-lint, maintaining great code quality and catching potential issues becomes an integral part of our coding journey.

***
## Contact Information

| Name | Email address |
| ---- | ------------- |
| Vishal | vishal.kesarwani.snaatak@mygurukulam.co |

***

## Resources and Reference

|  **Description** |   **Source** |
| ---------------- | ------------ |
| Introduction Bug Analysis and Tool Comparison | [Link](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/05-%20GoLang%20CI%20Checks/Bug%20Analysis/Introduction%20of%20Bugs%20analysis%20(GoLang%20CI%20Checks).md) |
| GoLangCI-lint Installation & Introduction | [Link](https://www.geeksforgeeks.org/how-to-install-golangci-lint/) |
