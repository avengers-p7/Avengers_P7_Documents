# Jenkins Pipeline and Setup

| Author                                                           | Created on  | Version    | Last Updated by | Last Updated on |
| ---------------------------------------------------------------- | ----------- | ---------- | --------------- | --------------- |
| **[Harshit Singh](https://github.com/Panu-S-Harshit-Ninja-07)**  | 07-02-2024  | 1.0        | Harshit Singh   | 09-02-2024      |


## Table  of Contents

1. [Introduction](#Introduction)
2. [What is Jenkins Pipeline](#What-is-Jenkins-Pipeline)
3. [Why Pipeline](#Why-Pipeline)
4. [Jenkinsfile](#Jenkinsfile)
5. [Types of Pipeline](#Types-of-Pipeline)
6. [Declarative Pipeline](#Declarative-Pipeline)
	- [Declarative syntax](#Declarative-syntax)
 	-  [Advantages of Declarative Pipelines](#Advantages-of-Declarative-Pipelines)
  	-  [Disadvantages of Declarative Pipelines](#Disadvantages-of-Declarative-Pipelines)  		
7. []()
	- []()
 	- []()
  	- []() 

8. []()
9. []()
10. [Contact Information](#Contact-Information)
11. [References](#References)
***

## Introduction 

A _**job**_ in Jenkins is a user-specified description of work, typically divided into sequential steps. For example, a job may fetch source code from a Git repository, compile it using the configured compiler, run it inside a staging environment, examine the output for any errors, and send an email notification to the user.

Jenkins uses projects (also known as "**jobs**") to perform its work. Projects are defined and run by Jenkins users. Jenkins offers several different types of projects, including:

- [Pipeline](https://www.jenkins.io/doc/book/pipeline/)
- [Multibranch Pipeline](https://www.jenkins.io/doc/book/pipeline/multibranch/)
- [Organization folders](https://www.jenkins.io/doc/book/pipeline/multibranch/#organization-folders)
- [Freestyle](https://phoenixnap.com/kb/jenkins-build-freestyle-project#:~:text=Jenkins%20freestyle%20projects%20allow%20users,steps%20and%20post%2Dbuild%20actions.)
- [Multi-configuration(matrix)](https://plugins.jenkins.io/matrix-project)
- [Maven](https://plugins.jenkins.io/maven-plugin)
- [External job](https://plugins.jenkins.io/external-monitor-job)

## What is Jenkins Pipeline

A Jenkins pipeline is a set of plug-ins to create automated, recurring workflows that constitute CI/CD pipelines. A Jenkins pipeline includes all the tools you need to orchestrate testing, merging, packaging, shipping, and code deployment.

A pipeline is typically divided into multiple stages and steps, with each step representing a single task and each stage grouping together similar steps. For example, you may have “Build”, “Test”, and “Deploy” stages in your pipeline. You can also run existing jobs within a pipeline.

***
## Why Pipeline
Jenkins is, fundamentally, an automation engine which supports a number of automation patterns. Pipeline adds a powerful set of automation tools onto Jenkins, supporting use cases that span from simple continuous integration to comprehensive CD pipelines. By modeling a series of related tasks, users can take advantage of the many features of Pipeline:

| Features | Description |
| --------- | ---------- |
|Code | Pipelines are implemented in code and typically checked into source control, giving teams the ability to edit, review, and iterate upon their delivery pipeline.
| Durable | Pipelines can survive both planned and unplanned restarts of the Jenkins controller.
| Pausable | Pipelines can optionally stop and wait for human input or approval before continuing the Pipeline run.
| Versatile | Pipelines support complex real-world CD requirements, including the ability to fork/join, loop, and perform work in parallel.
| Extensible | The Pipeline plugin supports custom extensions for integration with other plugins. |

***

## Jenkinsfile

The definition of a Jenkins Pipeline is written into a text file (called a **Jenkinsfile**) which in turn can be committed to a project’s source control repository. This is the foundation of "Pipeline-as-code"; treating the CD pipeline as a part of the application to be versioned and reviewed like any other code.

Creating a Jenkinsfile and committing it to source control provides a number of immediate benefits:

- Automatically creates a Pipeline build process for all branches and pull requests.
- Code review/iteration on the Pipeline (along with the remaining source code).
- Audit trail for the Pipeline.
- Single source of truth for the Pipeline, which can be viewed and edited by multiple members of the project.

While the syntax for defining a Pipeline, either in the web UI or with a Jenkinsfile is the same, it is generally considered best practice to define the Pipeline in a Jenkinsfile and check that in to source control.

## Types of Pipeline

A Jenkinsfile can be written using two types of syntax — 
1. **Declarative**, and
2. **Scripted**.

Declarative Pipeline is a more recent feature of Jenkins Pipeline which:

- provides richer syntactical features over Scripted Pipeline syntax, and
- is designed to make writing and reading Pipeline code easier.

Many of the individual syntactical components (or "steps") written into a Jenkinsfile, however, are common to both Declarative and Scripted Pipeline. Read more about how these two types of syntax differ in [Pipeline concepts](https://www.jenkins.io/doc/book/pipeline/#pipeline-concepts) and [Pipeline syntax](https://www.jenkins.io/doc/book/pipeline/#pipeline-syntax-overview) overview below.
***
## Declarative Pipeline

In many ways, declarative syntax represents the modern way of defining pipelines. It is robust, clean, and easy to read and write. The declarative coding approach dictates that the user specifies only what they want to do, not how they want to do it. This makes it easier to create declarative pipelines, as compared to scripted pipelines, which follow the imperative coding approach.

## Declarative syntax
In a declarative pipeline definition, the entire code is encapsulated within the pipeline block. Consider the following example:
```shell
pipeline { 	
    agent any		//------< 1 >-----
    stages {
        stage('Build') {//------< 2 >-----
            steps {
                //------< 3 >-----
            }
        }
        stage('Test') {	//------< 4 >-----
            steps {
                //------< 5 >-----
            }
        }
        stage('Deploy') { //------< 6 >-----
            steps {
                //------< 7 >-----
            }
        }
    }
}
```

![image](https://github.com/avengers-p7/Documentation/assets/156056444/dba901f7-948f-439f-8672-8b46c56ed7b7)
***
## Advantages of Declarative Pipelines
| Advantage                                                        | Description                                                                                                                                                         |
|------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Runtime syntax checking                                          | Syntax checking is performed at runtime in declarative pipelines, providing explicit error messages to users before execution starts                                 |
| Linting support                                                  | Users can lint their declarative Jenkinsfiles using a built-in API endpoint or a CLI command                                                                       |
| Docker pipeline integration                                      | Declarative pipelines offer extensive Docker pipeline integration, allowing users to run stages within a single container or each stage in a different container |
| Simplified configuration                                         | Declarative syntax simplifies configuration, making it easier to define parameters, environment variables, credentials, and options for a pipeline                  |
| Visual editor and snippet generator                              | Users can utilize the visual pipeline editor for user-friendly declarative code writing, along with a pipeline syntax snippet generator for auto-generating code   |
| Conditional logic                                                | Declarative syntax allows the introduction of conditional logic, including actions based on step success or failure, or skipping stages based on variable values   |
| When directive for skipping steps based on conditions            | The When directive enables skipping steps in declarative pipelines if certain conditions are not met|
***
## Disadvantages of Declarative Pipelines
| Disadvantage                                                   | Description |
|---------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Limitations for complex business logic                         | Developers accustomed to injecting complex business logic into pipeline code may struggle with certain limitations of declarative pipelines                                           |
| Migration challenges                                           | Organizations experienced with scripted pipelines may find migrating to declarative code time-consuming and error-prone                                                               |
| Limited cross-pipeline support                                 | Declarative pipelines do not allow injection of blocks of declarative code inside a scripted pipeline, limiting cross-pipeline support                                                |
***
##  Scripted Pipeline
Before the pipeline plug-in v2.5 introduced declarative pipelines, a scripted syntax was the only way to define pipeline code. Even today, many developers prefer it over declarative because it offers more flexibility and extensibility.

The scripted syntax offers a fully-featured programming environment, allowing developers to implement complicated business logic inside pipeline code. Scripted pipelines follow the imperative coding approach, in which the developer has complete control over what they want to achieve and how they want to achieve it.
***
## Scripted syntax
A scripted pipeline definition begins with the node keyword. Consider the following example:

```shell
node {		//------< 1 >-----
    stage('Build') {//------< 2 >-----
        //------< 3 >-----
    }
    stage('Test') {//------< 4 >-----
        //------< 5 >-----
    }
    stage('Deploy') {//------< 6 >-----
        //------< 7 >-----
    }
}
```

![image](https://github.com/avengers-p7/Documentation/assets/156056444/86cbc492-3656-46c5-beda-d4b13f06a34a)
***

## Advantages of Scripted Pipelines

| Feature                                         | Description                                                                                     |
|-------------------------------------------------|-------------------------------------------------------------------------------------------------|
| Scripted pipelines                             | Offer a full-fledged programming ecosystem to developers                                      |
| Groovy scripts and Java API injection           | Developers can inject Groovy scripts and reference Java APIs inside a scripted pipeline definition |
| Cross-pipeline support                         | Blocks of scripted pipelines can be injected inside the script step of a declarative pipeline definition to enhance cross-pipeline support |
***
## Disadvantages of Scripted Pipelines
| Disadvantage                                | Description                                                                                                    |
|--------------------------------------------|----------------------------------------------------------------------------------------------------------------|
| Harder learning curve for beginners        | Scripted syntax can be more challenging for novices compared to declarative syntax                            |
| Lack of runtime syntax checking            | Scripted pipelines do not offer runtime syntax checking, potentially leading to more errors during execution    |
| Absence of When directive                  | Scripted pipelines do not include the When directive, which can be used to skip a stage based on conditions    |
| Inability to restart from previous stage   | It is not possible to restart a scripted pipeline from a previous stage, limiting flexibility in pipeline runs |
***
## Scripted vs. declarative – which one should you choose?
There is no single right or wrong answer to which pipeline you should use for your business. Depending on your personalized needs, developers’ expectations, and time constraints, one may be a better fit than the other.
### Choose a Declarative Pipeline if:
- You want to set up your CI/CD pipeline in the minimum amount of time.
- You want to write straightforward, readable pipeline code, loading plugins or shared libraries for complicated business logic, adhering to core principles of CI/CD and pipeline-as-code.
- You don’t expect to reference Java APIs or Groovy scripts in your pipeline code.
- You want access to state-of-the-art Jenkins features such as the options block, the when directive, the environment directive, and intuitive code editors.
- You want to future-proof your CI/CD implementation.
### Choose a Scripted Pipeline if:
- You must include advanced business logic in your pipeline code.
- Your developers have hands-on experience with Groovy.
- All your existing pipelines are scripted, and you don’t want to migrate or move to a hybrid setup.
- You have business requirements forcing you to use older versions of Jenkins that don’t support declarative pipelines.
***
## Conclusion
Jenkins is a staple of numerous automation-driven, CI-CD-enabled IT infrastructures. It empowers organizations to increase productivity, build resilient software, decrease time-to-market, and reduce maintenance costs. In this document, we compared the two types of Jenkins pipelines in detail.
## Contact Information

|     Name         | Email  |
| -----------------| ------------------------------------ |
| Harshit Singh    | harshit.singh.snaatak@mygurukulam.co |
***

## References

| Description                                   | References  
| --------------------------------------------  | -------------------------------------------------|
| Pipeline | https://www.jenkins.io/doc/book/pipeline/|
| Types of pipeline | https://www.site24x7.com/learn/jenkins-pipelines.html |
| How to use Jenkinsfile in Jenkins | https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GenericDoc/pipelinePOC.md |
