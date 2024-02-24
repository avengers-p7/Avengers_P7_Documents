## CI pipeline for Frontend API (Shared Library)
***
| Author | Created on | Last updated by | Last edited on |
|--------|------------|-----------------|----------------|
|Shikha Tripathi | 9-02-2024 | Shikha Tripathi | 9-02-2024|

***
## Table of Contents
+ [Introduction](#Introduction)
+ [Features](#Features)
+ [Advantages](#Advantages)
+ [Disadvantages](#Disadvantages)
+ [Setup](#Setup)
+ [Html.Report](#Html.Report)
+ [Jenkinsfile](#Jenkinsfile)
+ [Conclusion](#Conclusion)
+ [Contact Information](#Contact-Information)
+ [Resources and References](#Resources-and-References)

***
## Introduction
Continuous Integration (CI) pipelines are crucial components in modern software development workflows, particularly in projects involving frontend APIs and shared libraries. This pipeline automates the integration of code changes from multiple developers into a shared repository, facilitating early bug detection, efficient collaboration, and reliable deployment processes.

***

## Features

|   Feature	| Description |
|-----------|-------------|
| **Automated Testing** | The CI pipeline executes automated tests, including unit tests, integration tests, and end-to-end tests, ensuring the stability and functionality of the frontend API and the shared library.|
| **Dependency Management** | It manages dependencies for both the frontend API and the shared library, ensuring consistent and compatible versions across the project.|
| **Continuous Deployment**| The pipeline automates the deployment process, allowing for rapid and consistent deployment of changes to production or staging environments.|
| **Code Quality Checks** | It performs code quality checks, such as linting and static code analysis, to maintain code standards and identify potential issues early in the development cycle.|
| **Scalability**| The CI pipeline scales seamlessly as the project grows, accommodating additional tests, integrations, and deployment steps without manual intervention.|
***


## Advantages
|Feature |Description |
|--------|------------|
| **Efficiency** | Automation reduces manual intervention, accelerating the development and release cycles.|
|**Consistency** | Standardized processes ensure consistent builds, tests, and deployments across different environments.|
| **Visibility**| CI pipelines provide visibility into the health and status of the project, enabling timely intervention in case of failures or issues.|
| **Collaboration** | CI encourages collaboration among team members by facilitating frequent integration and feedback loops.|
| **Risk Mitigation** | Early detection of bugs and issues minimizes the risk of introducing defects into production environments.|
***
## Disadvantages
| Feature |	Description |
|---------|-------------|
| **Complexity** | Setting up and maintaining a CI pipeline requires upfront investment in infrastructure and configuration.|
| **False Positives/Negatives** | Automated tests may occasionally produce false positives or negatives, requiring additional investigation and validation.|
| **Overhead**| CI pipelines can introduce overhead, especially in larger projects, impacting development velocity.|
| **Dependency on Infrastructure**| The reliability and performance of the CI pipeline depend on the underlying infrastructure and tooling.|

***
## Build and check result
![image](https://github.com/avengers-p7/Documentation/assets/156056746/1b9fef4f-9916-4c7c-9c04-048050b07893)


***
## Console Output
![image](https://github.com/avengers-p7/Documentation/assets/156056746/79a0e484-ce9b-4fb3-baa8-3838b5cb9d73)

***
##  Html Report
![image](https://github.com/avengers-p7/Documentation/assets/156056746/12461274-2ccf-494e-87c1-516a2275030f)

***
## Jenkinsfile
  * [**Jenkinsfie**](https://github.com/CodeOps-Hub/Frontend/blob/feature/frontendCI/Jenkinsfile)
  ```shell
    @Library("my-shared-library") _
// testing  webhook-001

// testing  salary CI webhook-001
def frotendCI = new org.avengers.template.frontendCI.frontendCI()

node {
    
    def url = 'https://github.com/CodeOps-Hub/Frontend.git'
    def branch = 'feature/frontendCI'
    def gitLeaksVersion = '8.18.2'
    def reportName = 'credScanReport.json'
    
    frotendCI.call(branch: branch,url: url, gitLeaksVersion, reportName)
    
}
```

## Conclusion
In conclusion, implementing a CI pipeline for a frontend API using a shared library brings numerous benefits to the development process, including automation, efficiency, and consistency. While there are challenges such as complexity and overhead, the advantages outweigh the disadvantages, making CI pipelines indispensable tools for modern software development teams. By embracing CI best practices and continuously refining the pipeline, teams can streamline their workflows, improve code quality, and deliver value to end-users more effectively.

***
## Contact Information

|     Name         | Email  |
| -----------------| ------------------------------------ |
| Shikha Tripathi   | shikha.tripathi.snaatak@mygurukulam.co |
***

## References

| Description                                   | References  
| --------------------------------------------  | -------------------------------------------------|
| Pipeline | https://www.gosysops.com/2020/ci-cd-with-jenkins-part-9-deploy-frontend-page-with-pipeline.html|



