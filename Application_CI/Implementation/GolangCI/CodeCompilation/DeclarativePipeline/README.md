|   Author        |  Created on   |  Version   | Last updated by  | Last edited on |
| --------------- | --------------| -----------|----------------- | -------------- |
| Khushi Malhotra |  07 Jan 2024  |  Version 1 | Khushi Malhotra  | 08 Jan 2024    |
***

# Table of Contents
- [Declarative Pipeline-Go Lang Code Compilation](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GolangCI/CodeCompilation/DeclarativePipeline/README.md#declarative-pipeline-go-lang-code-compilation)
- [Pre-requisites](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GolangCI/CodeCompilation/DeclarativePipeline/README.md#pre-requisites)
- [Code-Compilation Setup](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GolangCI/CodeCompilation/DeclarativePipeline/README.md#code-compilation-setup)
- [Conclusion](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GolangCI/CodeCompilation/DeclarativePipeline/README.md#conclusion)
- [Contact Information](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GolangCI/CodeCompilation/DeclarativePipeline/README.md#contact-information)
- [Resources and References](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GolangCI/CodeCompilation/DeclarativePipeline/README.md#resources-and-references)

# Declarative Pipeline-Go Lang Code Compilation
Building and deploying Go APIs can be streamlined through continuous integration and continuous delivery (CI/CD) pipelines. Declarative pipelines in Jenkins offer a robust and readable approach to automate Go code compilation. 
Declarative pipelines use Jenkins DSL, a Groovy-based domain-specific language, to define pipeline stages and steps in a more structured and human-readable format. This promotes maintainability and easier understanding of the build process.

# Pre-requisites
1. Jenkins Installed
2. go plugin

# Code-Compilation Setup 
**Step-1** Create a New Pipeline Job:

- Navigate to the Jenkins dashboard and click on New Item.
- Enter a name for your job (e.g., "Declarative pipeline-Golang-Code Compilation").
- Select Pipeline and click OK.

**Step-2** Configure Pipeline Script:

- In the job configuration page, scroll down to the Pipeline section.
- Select Pipeline script.
- Paste the provided scripted pipeline code into the script editor.

![image](https://github.com/avengers-p7/Documentation/assets/156056460/f7de7ec8-b886-4651-a563-45a0f6df8077)



[JenkinsFile](https://github.com/avengers-p7/Jenkinsfile/blob/main/Declarative%20Pipeline/golang_code-compilation/Jenkinsfile)

``` shell
pipeline {
    agent any
    
    tools {
        // Define the Go tool installation named 'Go' using the configured path
        go 'go1.22.0'
    }
    
    stages {
        stage('Checkout') {
            steps { 
                git branch: 'main', credentialsId: 'khushi_cred', url: 'https://github.com/OT-MyGurukulam/employee-api.git'
            }
        }
        stage('Code Compilation') {
            steps {
                script {
                    // Use the 'go' tool to run Go commands
                    sh 'go install' 
                    sh "go list -f '{{.Target}}'"
                }
            }
        }
    }
}
```
**Step-3** Save the Configuration:

- Click on Save to save the job configuration.

**Step-4** Build the Pipeline:

- Once the pipeline configuration is saved, you can manually trigger the build by clicking on Build Now.

**Step-5** View Build Console Output:

- After triggering the build, you can view the progress and console output of the build by clicking on the build number in the Jenkins dashboard.
- The console output will display the steps executed by the pipeline script, including code checkout and compilation.
- Verify Successful Compilation:
![image](https://github.com/avengers-p7/Documentation/assets/156056460/27199e21-f6b5-4abb-870a-809544ad29ff)
![image](https://github.com/avengers-p7/Documentation/assets/156056460/ccbb50b8-f13c-4337-b53b-31fd4ccb8697)
![image](https://github.com/avengers-p7/Documentation/assets/156056460/4ee715d7-d9b9-463d-ba4b-b93c19430790)
![image](https://github.com/avengers-p7/Documentation/assets/156056460/479f10ed-1800-4b0e-8189-c568d76e71a6)



# Conclusion
Declarative pipeline offers a simpler, more structured approach to defining Jenkins pipelines, making it ideal for teams looking to streamline their CI/CD processes and improve pipeline readability, maintainability, and scalability.

# Contact Information
| Name            | Email Address                        |
|-----------------|--------------------------------------|
| Khushi Malhotra | khushi.malhotra.snaatak@mygurukulam.co |

# Resources and References 
[Compile Code](https://go.dev/doc/tutorial/compile-install)

[Jenkins pipeline](https://www.jenkins.io/doc/book/pipeline/#:~:text=Scripted%20Pipeline%20syntax.-,Declarative%20Pipeline%20fundamentals,done%20throughout%20your%20entire%20Pipeline.&text=Execute%20this%20Pipeline%20or%20any,stages%2C%20on%20any%20available%20agent.&text=Defines%20the%20%22Build%22%20stage.&text=Perform%20some%20steps%20related%20to%20the%20%22Build%22%20stage.)
