# Proof of Concept (POC) for Golang Base Application

<img width="360" length="100" alt="Golang" src="https://github.com/avengers-p7/Documentation/assets/156056413/56e9dd64-9654-449c-be6d-4212de6aca71">


| Author                 | Created On | Last Updated | Document Version | Last Updated By |
| ---------------------- | ---------- | ------------ | ---------------- | --------------- |
| **Vishal Kumar Kesarwani** | 29-01-2024 | 30-01-2024   | v1               |  **Vishal**        |
***
## Table of Contents

+ [Introduction](#Introduction)
+ [Prerequisites](#Prerequisites)
+ [Steps of unit testing](#Steps-of-unit-testing)
  + [Cloning the Go Application](#Cloning-the-Go-Application)
  + [Run the Tests](#Run-the-Tests)
+ [Unit Testing in Other Languages](#Unit-Testing-in-Other-Languages)
+ [Conclusion](#Conclusion)
+ [Contact Information](#Contact-Information)
+ [References](#References)
***
## Introduction

This document explores conducting unit tests in a Golang app using the standard testing framework provided by the testing package. Pre-written unit tests within the repository cover modules like API, client, config, middleware, and routes. Leveraging this framework ensures code quality and functionality, fostering confidence in the application's reliability.

* **Repo Link :** Use this Repository....
  ```shell
  https://github.com/OT-MICROSERVICES/employee-api.git
    ```
***

## Unit Testing   
Unit Testing is a fundamental software testing method where individual modules or components are tested to verify their functional correctness. It involves assessing independent units, such as functions or procedures, to identify issues early in the development process. Typically performed by developers, it serves as the initial level of testing before integration testing in the software development lifecycle. While developers primarily conduct unit testing, quality assurance engineers may also participate due to developers' occasional reluctance to perform these tests.  
For more detail click [**here**](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/03-%20Java%20CI%20checks/Intro%20of%20Unit%20Testing.md)  
***
## Different Tools for Unit Testing

***
## Prerequisites

* Install Golang  
  
***  
## Steps of unit testing  

* Within the directory, make a clone of the repository. 
  ```shell
  mkdir snatak_p7
  cd snatak_p7
  git clone https://github.com/OT-MICROSERVICES/employee-api.git  
  cd employee-api/
  ```
  <img width="760" length="200" alt="Golang" src="https://github.com/avengers-p7/Documentation/assets/156056413/c12a898d-f9bd-4865-82f4-0eaf01f6e481">  

* Install Prerequisites
   ```shell
  sudo apt update
  sudo snap install go
  ```
***
## Unit Testing in Other Languages
* For Java unit testing, refer to this link : [**Java**](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/03-%20Java%20CI%20checks/Unit-Testing-Poc.md)
* For Python unit testing, refer to this link : [**Python**]()
***
## Conclusion
Upon conducting unit tests in Go using the standard testing framework from the testing package, we receive comprehensive reports confirming the proper functionality of individual units, such as functions or methods. These reports affirm that each unit performs as expected and yields the desired output, ensuring the reliability and accuracy of our codebase.

***

## Contact Information

| Name | Email address |
| ---- | ------------- |
| Vishal | vishal.kesarwani.snaatak@mygurukulam.co |

***

## References

| Source | Description |
| ------ | ----------- |
| [Link](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/03-%20Java%20CI%20checks/Intro%20of%20Unit%20Testing.md) | Introduction of Unit Testing |
| [Link](https://speedscale.com/blog/golang-testing-frameworks-for-every-type-of-test/) | Popular testing frameworks for Golang |
