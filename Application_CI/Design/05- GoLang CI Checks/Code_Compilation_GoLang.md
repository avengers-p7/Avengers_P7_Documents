|   Author        |  Created on   |  Version   | Last updated by  | Last edited on |
| --------------- | --------------| -----------|----------------- | -------------- |
| Khushi Malhotra |  30 Jan 2024  |  Version 1 | Khushi Malhotra  | 30 Jan 2024    |
***

# Code Compilation - Go language CI Checks 

# What is Code Compilation in CI Checks
Code compilation in CI checks refers to the process of compiling the source code of a project as part of a Continuous Integration (CI) pipeline. 
CI is a software development practice that involves automatically building and testing code changes made by developers, ensuring that the code is free of errors and adheres to the rules of the programming language.

# Why we need Code Compilaton
| Feature                     | Description                                                                                                                                                                 |
|-----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Early Error Detection**   | Compilation catches syntax errors, type mismatches, and other code-level issues early in the development process. Identifying these problems before testing and deployment prevents costly downstream issues and saves time. |
| **Dependency Management**   | Go's dependency management system (go mod) relies on compilation to ensure proper version resolution and compatibility of packages. CI compilation verifies that dependencies are correctly fetched and integrated, reducing dependency-related errors. |
| **Static Analysis**         | Go's compiler supports built-in static analysis tools like go vet and golint. Integrating these tools into the CI compilation stage checks for potential code problems, code style violations, and security vulnerabilities, enhancing code quality. |
| **Cross-Platform Compatibility** | Go produces platform-specific binaries. Compiling in CI for different target platforms (e.g., Windows, Linux, macOS) ensures code compatibility across environments, preventing deployment issues. |
| **Reproducible Builds**     | Go's deterministic compilation process ensures consistent binaries for the same code and dependencies. This reproducibility is crucial for reliable testing, deployment, and auditing in CI environments. |
| **Fast Feedback Cycle**     | Go's compilation is relatively fast, providing quick feedback on code changes. This enables developers to quickly identify and fix errors, contributing to a smoother development process. |
| **Versioning**              | Go's compilation can be used for version control, tracking changes and managing different software versions effectively.                                                    |

# Different tools used in Code Compilation of Go Lang
| **Compilation Tool for Go** | **Description**                                                                                                   |
|-----------------------------|-------------------------------------------------------------------------------------------------------------------|
| **1. go build**             | - Compiles entire Go projects, including dependencies.<br>- Generates an executable binary for immediate use.    |
| **2. go tool compile**      | - Compiles individual Go packages into object files (.o).<br>- Lower-level tool suitable for specific tasks like debugging or custom build processes. |

# Comparison between **go build** and **go tool compile*
| **Aspect**                    | **go build**                                                                                               | **go tool compile**                                                                                                       |
|-------------------------------|------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------|
| **Description**               | - Compiles entire project with dependencies.<br>- Generates an executable binary.                          | - Compiles individual Go packages into object files (.o).<br>- A lower-level tool for specific tasks like debugging.       |
| **Output**                    | - Produces an executable binary (.exe, .out) ready to run your program.                                    | - Generates individual object files (.o) containing compiled code for a specific package.<br>- Further linking is needed to create an executable.                                  |
| **Use Cases**                 | - Building executables for testing, deployment, and running applications.<br>- Everyday development needs.  | - Debugging specific code sections by inspecting generated assembly.<br>- Integrating compilation into custom build systems or workflows.<br>- Understanding the internal workings of the Go compiler.  |
| **Advantages**                | - Convenience: Handles everything in one step, including dependency resolution and linking.<br>- Simplicity: Easy to use and understand, ideal for everyday development tasks.<br>- Automation: Integrates seamlessly with build tools and CI pipelines.<br>- Output: Produces directly runnable executables for immediate testing and deployment. | - Granularity: Offers fine-grained control over individual package compilation.<br>- Debugging: Enables inspection of assembly code for specific packages.<br>- Customization: Useful for building complex programs with custom workflows.<br>- Learning: Provides insights into the internal workings of the Go compiler. |


# Is go build better than go tool compile?
It depends on your needs!go build is generally better for most developers due to its simplicity and convenience for building complete applications.
However, go tool compile has its own advantages for specific situations where fine-grained control or deep understanding of the compilation process is crucial.
Here simplicity and building a complete application are key, I'll stick with the convenience of go build.

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
**Step-7** Create the Test File:
- Open your code editor or IDE and navigate to the directory containing your main Go package (where your main.go file resides).
- Create a new file named ```main_test.go``` within the same directory.
- Structure the Test File:
- Import necessary packages
``` shell
// main_test.go
package main

import "testing"

func TestYourFunction(t *testing.T) {
    // Your test logic here
}
```
![image](https://github.com/avengers-p7/Documentation/assets/156056460/5e0c644b-96b3-45af-a8ae-b92c8c0064a3)
***
![WhatsApp Image 2024-01-31 at 02 20 31_9fd2bc60](https://github.com/avengers-p7/Documentation/assets/156056460/9866c6c1-f436-4929-9415-f625cf0eee12)
***
![image](https://github.com/avengers-p7/Documentation/assets/156056460/bee29298-023a-4bc6-9ff1-01a96a892194)
***
**Step-8** Run the Tests:
- Open a terminal (or command prompt) in the project directory.
- Execute the command
```shell
 go test
```
![WhatsApp Image 2024-01-31 at 02 20 49_5ae975fe](https://github.com/avengers-p7/Documentation/assets/156056460/5675a57c-95b3-4c8e-9bf8-9ae24e4cbf85)

#Conclusion
- Go's straightforward compilation process, combined with built-in tools for dependency management, static analysis, and testing, promotes code quality and reliability.
- Following these steps ensures a smooth development workflow and confidence in code functionality.
- By integrating these tools into build systems or CI pipelines, you can automate quality checks and catch issues early, leading to more robust and maintainable Go applications.

# Contact Information
| Name            | Email Address                        |
|-----------------|--------------------------------------|
| Khushi Malhotra | khushi.malhotra.snaatak@mygurukulam.co |

# Resources and References
| [Code Compilation](https://www.techtarget.com/searchsoftwarequality/CI-CD-pipelines-explained-Everything-you-need-to-know) |
| [POC](https://blog.jetbrains.com/go/2022/11/22/comprehensive-guide-to-testing-in-go/) |
