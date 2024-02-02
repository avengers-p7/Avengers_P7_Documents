|   Author        |  Created on   |  Version   | Last updated by  | Last edited on |
| --------------- | --------------| -----------|----------------- | -------------- |
| Khushi Malhotra |  30 Jan 2024  |  Version 1 | Khushi Malhotra  | 31 Jan 2024    |
***
# Table of Contents
- [Introduction](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/05-%20GoLang%20CI%20Checks/Code_compilation-go.md#introduction)
- [Pre-requisites](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/05-%20GoLang%20CI%20Checks/Code_compilation-go.md#pre-requisites)
- [Flow Diagram](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/05-%20GoLang%20CI%20Checks/Code_compilation-go.md#flow-diagram)
- [POC of Code Compilation in Go](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/05-%20GoLang%20CI%20Checks/Code_compilation-go.md#poc-of-code-compilation-in-go)
- [Conclusion](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/05-%20GoLang%20CI%20Checks/Code_compilation-go.md#conclusion)
- [Contact Information](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/05-%20GoLang%20CI%20Checks/Code_compilation-go.md#contact-information)
- [Resources and References](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/05-%20GoLang%20CI%20Checks/Code_compilation-go.md#resources-and-references)
***
# Introduction
Code compilation in Go is the process of converting human-readable Go source code into machine-executable code that can run directly on a computer's hardware. 

# Pre-requisites

| **Tool** | 
| -------- | 
| **go** | 
| **golint**|

# FLow Diagram
![WhatsApp Image 2024-02-03 at 04 25 01_2008c80a](https://github.com/avengers-p7/Documentation/assets/156056460/c474bd3c-11c6-4391-b9bd-c8c5e0325503)

- Start: The process starts with either cloning the Go repository using git clone or downloading a pre-built binary.
- Install dependencies: Next, the script installs the Go mod and Golint tools, which are used to manage dependencies and keep the Go installation clean and organized.
- Run Go mod tidy: This command ensures that all necessary dependencies are downloaded and up-to-date.
- Run Go vet: This command performs static code analysis to identify potential issues and errors in the Go code.
- Build Go: The script proceeds to build the Go compiler and tools using the Go build command.
- Run Go test: After building, the script runs the Go test suite to verify that everything is working correctly.

***
# POC of Code Compilation in Go

**Step-1** Clone the Repository:

- Open a terminal (or command prompt).
- Navigate to the desired directory using cd commands.
- Clone the repository using 

``` shell 
git clone https://github.com/avengers-p7/Employee-API.git
```
![image](https://github.com/avengers-p7/Documentation/assets/156056460/04b674e8-b3d8-4f6e-9b03-c39271c69d23)
***
**Step-2** Install Go:

- Download the Go installer 
``` shell
sudo snap install go --classic
```
![image](https://github.com/avengers-p7/Documentation/assets/156056460/c7ce4925-86fb-4b5c-8dc3-933b4e706c37)
***
**Step-3** Tidy Dependencies:

- Run go mod tidy to clean up and update dependencies.
``` shell
go mod tidy
```
![image](https://github.com/avengers-p7/Documentation/assets/156056460/fa3176fc-5528-444c-b325-c38218ffe4bf)
***
**Step-4** Run Static Analysis:

- Check for potential code issues
 ``` shell
go vet main.go
```
![image](https://github.com/avengers-p7/Documentation/assets/156056460/be03aea3-21a5-4be1-bb25-38075ee6a04d)
***
**Step-5** Install lint
- Install golint for code style checks
``` shell
  sudo snap install golint
```
- Then run command for enforcing code style
``` shell
  golint ./...
```

![image](https://github.com/avengers-p7/Documentation/assets/156056460/1e1157c1-fc50-47a5-bdfa-9aa25e16c214)
***
**Step-6** Compile the Code:
- Build the project
``` shell
go build -o employee-api
```
![WhatsApp Image 2024-01-31 at 02 44 17_a2bf763a](https://github.com/avengers-p7/Documentation/assets/156056460/8957a7ce-e4a7-4c1e-87b4-cdc96bfe3283)
***

**Step-7** Run the Tests:
- Open a terminal (or command prompt) in the project directory.
- Execute the command
```shell
 go test ./...
```
![WhatsApp Image 2024-01-31 at 20 23 27_a38d6a1e](https://github.com/avengers-p7/Documentation/assets/156056460/8feab0ce-55c4-44fa-b581-9bf9f98e279c)
***
# Conclusion
- "Go's lightning-fast compilation and integrated tooling streamline development and empower rapid iterations, ensuring code quality and reliability without sacrificing speed."
- "The seamless integration of dependency management, static analysis, and testing within Go's toolchain accelerates feedback loops and promotes code confidence, leading to swifter release cycles."

# Contact Information
| Name            | Email Address                        |
|-----------------|--------------------------------------|
| Khushi Malhotra | khushi.malhotra.snaatak@mygurukulam.co |

# Resources and References
[Code Compilation](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/05-%20GoLang%20CI%20Checks/Code_Compilation_GoLang.md) 

[POC](https://blog.jetbrains.com/go/2022/11/22/comprehensive-guide-to-testing-in-go/)
