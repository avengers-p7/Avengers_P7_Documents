# Unit Testing for Golang Base Application

<img width="360" length="100" alt="Golang" src="https://github.com/avengers-p7/Documentation/assets/156056413/56e9dd64-9654-449c-be6d-4212de6aca71">


| Author                 | Created On | Last Updated | Document Version | Last Updated By |
| ---------------------- | ---------- | ------------ | ---------------- | --------------- |
| **Vishal Kumar Kesarwani** | 29-01-2024 | 04-02-2024   | v1               |  **Vishal**        |
***
## Table of Contents

+ [Introduction](#Introduction)
+ [Unit Testing](#Unit-Testing)
+ [Different Tools for Unit Testing](#Different-Tools-for-Unit-Testing)
+ [Prerequisites](#Prerequisites)
+ [Flow Diagram](#Flow-Diagram)
+ [Steps of unit testing](#Steps-of-unit-testing)
  - [Cloning the Go Application](#Cloning-the-Go-Application)
  - [Install Prerequisites](#Install-Prerequisites)
  - [Run the Tests](#Run-the-test)
  - [Generating the report](#Generating-the-report)
+ [Unit Testing in Other Languages](#Unit-Testing-in-Other-Languages)
+ [Conclusion](#Conclusion)
+ [Contact Information](#Contact-Information)
+ [References](#References)
***
## Introduction

This document explores conducting unit tests in a Golang app using the standard `testing` framework provided by the testing package. Pre-written unit tests within the repository cover modules like API, client, config, middleware, and routes. Leveraging this framework ensures code quality and functionality, fostering confidence in the application's reliability.

* **Repo Link :** Use this Repository....
  ```shell
  https://github.com/OT-MICROSERVICES/employee-api.git
    ```
***

## Unit Testing   
Unit Testing is a fundamental software testing method where individual modules or components are tested to verify their functional correctness. It involves assessing independent units, such as functions or procedures, to identify issues early in the development process. Typically performed by developers, it serves as the initial level of testing before integration testing in the software development lifecycle. While developers primarily conduct unit testing, quality assurance engineers may also participate due to developers' occasional reluctance to perform these tests.  
For more detail click [**here**](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/03-%20Java%20CI%20checks/Intro-of-Unit-Testing.md)  
***
## Different Tools for Unit Testing

<img width="360" length="100" alt="Golang" src="https://github.com/avengers-p7/Documentation/assets/156056413/6ac593b4-f7a0-4fc3-8a9a-5402b914345b">

| Tool           | Description                                                                                      | Features                                                                   | Pros                                                                   | Cons                                                                            |
|----------------|--------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------|------------------------------------------------------------------------|---------------------------------------------------------------------------------|
| **Testing Package** | Lightweight and suitable for basic testing within the Go standard library, but lacks advanced features | Basic testing capabilities, no external dependencies                       | No additional dependencies, lightweight                                  | Limited features, lacks advanced capabilities                                   |
| **Testify**        | Offers rich assertion library and mock capabilities, enhancing test readability, but adds dependency and potential code bloat | Rich assertion library, mock capabilities                                  | Enhanced test readability, advanced features                              | Adds dependency, potential code bloat                                            |
| **Ginkgo**         | Provides BDD-style syntax for clear and descriptive tests, suitable for complex scenarios, but has a learning curve and slower execution | BDD-style syntax, clear and descriptive tests, parallel testing            | Clear and descriptive tests, suitable for complex scenarios              | Learning curve, slower execution                                                 |
| **GoConvey**       | Offers a user-friendly interface with real-time feedback and supports TDD practices, but may slow down test execution due to UI overhead | User-friendly interface, real-time feedback, TDD support                   | Real-time feedback, supports TDD practices                                | Slower execution, UI overhead                                                    |
| **GoMock**         | Useful for generating mock objects and seamlessly integrates with Go testing, but may have limitations in handling complex mocking scenarios | Mock capabilities, seamless integration with Go testing                    | Seamless integration, useful for mock object generation                   | Limitations in complex mocking scenarios                                        |


***
## Prerequisites

* Install Golang (go version go1.21.6 )
  
***  

## Flow Diagram

<img width="813" alt="image" src="https://github.com/avengers-p7/Documentation/assets/156057205/1d577e9b-6459-4f1c-8946-05a4ecb37643">

**Description of Flow Dioagram**

| **Steps** | **Description** |
| ------------- | --------------- |
| **Directory** | Create a new directory named `snatak_p7` |
| **Clone Git Repository** | Clone the Git repository `employee-api.git` into the current directory |
| **Install Go** | Install Go programming language using the Snap package manager |
| **Run Unit Tests** | Execute unit tests for the current codebase |
| **Run All Tests** | Run tests recursively for all packages |
| **Run Tests with Verbose and Coverage** | Execute tests with verbose output and coverage information |
| **Generate Coverage Profile** | Create a coverage profile file `coverage.out` for further analysis |
| **Generate HTML Report** | Convert the coverage profile to an HTML report for detailed visualization |
| **Completion** | The flow is completed, and the necessary steps for testing and coverage analysis have been executed |

***

## Steps of unit testing  

####  Cloning the Go Application
  First make a directory, then Within that directory clone the repository. 
  ```shell
  mkdir snatak_p7
  cd snatak_p7
  git clone https://github.com/OT-MICROSERVICES/employee-api.git  
  cd employee-api/routes/
  ```
  <img width="660" length="200" alt="Golang" src="https://github.com/avengers-p7/Documentation/assets/156056413/c12a898d-f9bd-4865-82f4-0eaf01f6e481">  

#### Install Prerequisites
   ```shell
  sudo apt update
  sudo snap install go --classic
  go version
  ```
   <img width="660" length="200" alt="Golang" src="https://github.com/avengers-p7/Documentation/assets/156056413/01d25209-8a1f-406a-9430-f12d47a94736"> 

#### Run the test
  * Open a terminal or command prompt, navigate to the directory containing your Go files, and run the tests using the go test command:
  ```shell
  go test
  ```
   <img width="660" length="200" alt="Golang" src="https://github.com/avengers-p7/Documentation/assets/156056413/51132d5d-afc0-4d56-8399-9ad784b243a9"> 

  * Run tests for the entire project, including all packages, you can run  
  ```shell
  go test ./...
  ```
  <img width="560" length="200" alt="Golang" src="https://github.com/avengers-p7/Documentation/assets/156056413/c42b610e-0d84-4ff1-baec-19dea948e931"> 

   * To perform unit tests for the entire Go language repository and generate detailed output regarding the success and failure of test cases, you can use the go test command with the `-v (verbose) and -cover (test coverage)` flags. Here's the command:
  ```shell
  go test -v -cover ./...
  ```
  <img width="660" length="200" alt="Golang" src="https://github.com/avengers-p7/Documentation/assets/156056413/15ebafbc-aab4-4b14-b217-772eb64d666e"> 
  <img width="660" length="200" alt="Golang" src="https://github.com/avengers-p7/Documentation/assets/156056413/4f46a24f-66c1-4380-9e9e-10c930f36f9f"> 

#### Generating the report    
  * To generate a test coverage report in Go, you can use the built-in go test tool with the -coverprofile flag to generate a coverage profile, and then use the gohttps://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/04-%20Python%20CI%20Checks/UnitTesting.md tool cover command to generate an HTML coverage report.
  ```shell
  go test -coverprofile=coverage.out
  ```
  <img width="660" length="200" alt="Golang" src="https://github.com/avengers-p7/Documentation/assets/156056413/28755278-1660-4da5-ad2c-825f3ea2ab30"> 
  
  ```shell
  go tool cover -html=coverage.out -o coverage.html
  ```
  <img width="660" length="200" alt="Golang" src="https://github.com/avengers-p7/Documentation/assets/156056413/c8a09a6d-c41d-4405-a311-6753030e8cf8"> 

After running unit tests in Go using the standard testing framework provided by the `testing package`, we receive a comprehensive report confirming whether each unit, like a function or method, behaves correctly and generates the expected results.  
[**Coverage.htm**l](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/05-%20GoLang%20CI%20Checks/coverage.html)

***
## Unit Testing in Other Languages
* For Java unit testing, refer to this link : [**Java**](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/03-%20Java%20CI%20checks/Unit-Testing-Poc.md)
* For Python unit testing, refer to this link : [**Python**](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/04-%20Python%20CI%20Checks/UnitTesting.md)
***
## Conclusion

Choosing the best tool depends on specific project requirements, team preferences, and trade-offs between features, dependencies, and performance. For lightweight testing without extra dependencies, the built-in testing package suffices. For more advanced assertion and mocking capabilities, Testify or GoMock can be beneficial. Ginkgo and GoConvey are suitable for teams favoring BDD-style testing or requiring real-time feedback and visual test representations.

***

## Contact Information

| Name | Email address |
| ---- | ------------- |
| Vishal | vishal.kesarwani.snaatak@mygurukulam.co |

***

## References

| Source | Description |
| ------ | ----------- |
| [Link](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/03-%20Java%20CI%20checks/Intro-of-Unit-Testing.md) | Introduction of Unit Testing |
| [Link](https://speedscale.com/blog/golang-testing-frameworks-for-every-type-of-test/) | Popular testing frameworks for Golang |
| [Link](https://www.digitalocean.com/community/tutorials/how-to-write-unit-tests-in-go-using-go-test-and-the-testing-package) | POC Setup | 
