
# Conclusion Document CI Orchestration Tools
## Jenkins vs Gitlab vs BuildPiper

| Author | Created on  | Version    | Last Updated by | Last Updated on |
| -------- | ------- | -------------- | --------------| ---------------- |
| **[Harshit Singh](https://github.com/Panu-S-Harshit-Ninja-07)**  | 27-01-2024  | 1.0   | Harshit Singh | 28-01-2024 |
***

## Table  of Contents

1. [Introduction](#Introduction)
2. [What is Jenkins?](#What-is-Jenkins)
3. [What is GitLab?](#What-is-GitLab)
4. [What is BuilPiper?](#what-is-buildpiper)
5. [Comparision](#Comparision)
6. [Conclusion](#Conclusion)
7. [Contact Information](#Contact-Information)
8. [References](#References)
***

## Introduction 

Detailed documentation with Comparison table and final recommendation as per template
This documentation provide a introduction of  _**BuildPiper**_  and its features as a CI orchestration tool.

## What is Jenkins?
Jenkins is an automation server that is self-contained and open source. It allows the building, testing, and deployment of every software release cycle. Through its fleet of plugins (over 1700) that seamlessly integrate with most CI/CD tools, Jenkins offers flexibility and covers almost all functional requirements.

Moreover, since Jenkins is written in Java, it is compatible with any system with Java Runtime Environment (JRE) installed. This makes Jenkins widely usable due to its easy availability.

![image](https://github.com/avengers-p7/Documentation/assets/156056444/05ce71b6-4e02-467e-af7f-37f94a33d41e)
***
## What is GitLab?
GitLab CI is a self-contained platform supporting the DevOps lifecycle through web-based services. It manages the Git repository through its Continuous Integration and Deployment pipelines, issue-tracking features, and wiki to store relevant files.

GitLab works on a freemium basis, i.e., it offers both free and paid services. It enables automating the entire DevOps lifecycle, which involves planning, building, testing, deployment, and monitoring through release cycles.

![image](https://github.com/avengers-p7/Documentation/assets/156056444/92c566e2-4599-40a1-8959-8d9696b8d9fe)
***
## What is BuildPiper?
BuildPiper is an end-to-end Kubernetes and Microservices Application Delivery Platform designed for developer and engineering teams. It offers a comprehensive set of features for managing the entire lifecycle of containerized applications.
   
   - BuildPiper is a one-stop solution for onboarding and managing Kubernetes and Microservices applications securely.
   - It facilitates zero-touch, fully automated, and secured CI/CD pipelines.

![image](https://github.com/avengers-p7/Documentation/assets/156056444/0ca8d312-0b03-46d1-a85a-f17665008f4f)
***
## Comparision
| Criteria  | Jenkins | GitLab | BuildPiper |
| --------- | -------- | ------ | --------- |
| **Plugins** | 1700+ plugins |   Limited plugins |  |
| **Prerequisites** | JRE should be installed	| Ruby, Go, Git, Node.js, and Redis should be installed | none |
| **Operating Systems Supported** |	Windows, Mac OS X, and Unix-like OS |	Supports only particular Unix-like OS such as Ubuntu, Debian, Red Hat Linux, Scientific Linux, Oracle Linux, CentOS, and OpenSUSE. It does not support Windows and macOS. | |
| **Open Source**	| Open Source and Free	| Open Source and Freemium | |
| **Issue Tracking**	| Don’t have such functionality	| Offers various features for issue tracking and management | |
| **Extensiveness** |	Highly extensive as it can be used as a simple CI server or can be transformed into a complex CD system with the help of plugins	| Offers scalability to enhance the DevOps lifecycle for a project | |
| **Support** |	Offers documentation and open source community support, but no technical support is provided as part of the SLA |	Provides 24×5 support for paid users and only self-support documents to free users as part of the SLA | |

Management of microservice repositories and CI/CD pipeline becomes much more complex and challenging as the number of applications increases. For businesses looking for solutions to manage CI/CD pipelines, BuildPiper is the ideal choice for effective CI/CD pipeline management. It enables intuitive and easy setup of feature-rich delivery pipelines for a seamless and secure product release.

Automated CI checks and complete CI analysis help in identifying the defects and vulnerabilities in the initial stages, thus enabling a quick, complaint, and hassle-free code release. 
***

## System Requirements
For stand-alone setup :-

|   System Requirement              |             Minimum           |
| --------------------------------- | ----------------------------- |
| Processor/Instance Type           |         1 VM of 4 CPU         | 
| RAM                               |            8 GB               |

> [!NOTE]
> There are no software requirements for _BuiildPiper_ setup.

## Features

| Features | Description |
|  --------- | ----------- |
| **Shift Left Philosophy** |  allows developers and QA engineers to manage their Microservices Management-related tasks `that include build, deployment, observability, and environment management` independently. |
| **Security across all Stages of Deployment**| enables teams to conduct regular security audits and perform automated CI checks in the pipeline stages. `AWS secret manager, trivy, gitLeaks, Owasp and Sonar`I|
| **Observability with Detailed Insights** | Obtain insights across every aspect of your Services( right from build to deployment), all Kubernetes resources and stages of Pipelines delivery via smart dashboards. These details help the development teams in analyzing and enhancing the application performance. |
| **Seamless & Flexible CI/CD Operations** | Equipped with feature-rich, secure delivery & setup of CD Pipelines for Macro & Micro builds & deployments, `automated and customizable CI gate checks`, comprehensive `CI analysis with multiple language support` and more. |
| **GitOps Integration to accelerate the App Delivery Process** | BuildPiper supports comprehensive `GitOps-based workflow orchestration` to make the software delivery process developer-centric. With essential check gates and approval, the platform enables seamless & faster deployments with standardization. Right from build, to quality validation and ultimately releasing the source code to the production, developers `can manage the complete application lifecycle, through git workflows and events`. |
***

## How BuildPiper manages CI/CD

With BuildPiper, the initial set-up and execution of CI/CD pipelines are structured around these 4 primary levers that make it ready for a quick and bug-free software release.

<!-- 1. Automated CI Checks
   - Comprehensive CI analysis
   - Multi-language CI support
2. Intuitive and easy setup of feature-rich delivery pipelines
   - Multiple options to trigger the pipeline
   - Easy pipeline construct of stages & jobs
3. Realtime details via an interactive and user-friendly UI
4. Simple and easy to understand UI and YAML view -->

|                               Points                           |                                                  Description                                                |
| -------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------- |
| 1. Automated CI Checks                                         | <ul><li>Comprehensive CI analysis</li><li>Multi-language CI support</li></ul>                               |
| 2. Intuitive and easy setup of feature-rich delivery pipelines | <ul><li>Multiple options to trigger the pipeline</li><li>Easy pipeline construct of stages & jobs</li></ul> |
| 3. Realtime details via an interactive and user-friendly UI    |                                                                                                             |
| 4. Simple and easy to understand UI and YAML view              |                                                                                                             |
***

![image](https://github.com/avengers-p7/Documentation/assets/156056444/2ff08f16-7315-491a-9281-9c8e2c96139e)

![image](https://github.com/avengers-p7/Documentation/assets/156056444/22aa47ec-83a2-4c35-b298-946e4b228d7c)
***
## Who uses BuildPiper? 

![image](https://github.com/avengers-p7/Documentation/assets/156056444/5d786728-802a-449b-be0a-a5de01159342)

## Conclusion

In conclusion, BuildPiper stands out as a robust end-to-end Kubernetes and Microservices Application Delivery Platform, designed to streamline the development and deployment processes for developer and engineering teams. With a comprehensive feature set, BuildPiper offers a one-stop solution for onboarding and managing Kubernetes and Microservices applications securely.

With a user-friendly interface and support for multiple language CI, BuildPiper facilitates a smooth and customizable CI/CD pipeline setup. The inclusion of automated CI checks, real-time details through an interactive UI, and GitOps-based workflow orchestration further strengthen its position as a developer-centric CI orchestration tool.

***

## Contact Information

|     Name         | Email  |
| -----------------| ------------------------------------ |
| Harshit Singh    | harshit.singh.snaatak@mygurukulam.co |
***

## References

|     Description                  | References  
| ---------------------------------| ------------------------------------------------------------------- |
|     Documentation Template       | https://github.com/OT-MICROSERVICES/documentation-template/wiki/Application-Template |
|     Introduction    | https://www.buildpiper.io/documentation/docs/getting/introducing |
|     CI    | https://www.buildpiper.io/documentation/docs/set-up-pipeline/ci-scope |
