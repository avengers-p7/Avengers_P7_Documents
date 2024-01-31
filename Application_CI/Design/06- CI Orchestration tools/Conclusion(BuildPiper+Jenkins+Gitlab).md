
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
5. [Comparison](#Comparison)
6. [Conclusion](#Conclusion)
7. [Contact Information](#Contact-Information)
8. [References](#References)
***

## Introduction 

This documentation provides a brief introduction of CI Orchestration tools(Jenkins, GitLab and BuildPiper) and comparison between them.

## What is Jenkins?
Jenkins is an automation server that is self-contained and open source. It allows the building, testing, and deployment of every software release cycle. Through its fleet of plugins (over 1700) that seamlessly integrate with most CI/CD tools, Jenkins offers flexibility and covers almost all functional requirements.

Moreover, since Jenkins is written in Java, it is compatible with any system with Java Runtime Environment (JRE) installed. This makes Jenkins widely usable due to its easy availability.

![image](https://github.com/avengers-p7/Documentation/assets/156056444/05ce71b6-4e02-467e-af7f-37f94a33d41e)
***
## What is GitLab?
GitLab CI is a self-contained platform supporting the DevOps lifecycle through web-based services. It manages the Git repository through its Continuous Integration and Deployment pipelines, issue-tracking features, and wiki to store relevant files.

GitLab works on a freemium basis, i.e., it offers both free and paid services. It enables automating the entire DevOps lifecycle, which involves planning, building, testing, deployment, and monitoring through release cycles.

![image](https://github.com/avengers-p7/Documentation/assets/156056444/53283b3b-45ad-4234-a702-891bcb746af9)
***
## What is BuildPiper?
BuildPiper is an end-to-end Kubernetes and Microservices Application Delivery Platform designed for developer and engineering teams. It offers a comprehensive set of features for managing the entire lifecycle of containerized applications.
   
   - BuildPiper is a one-stop solution for onboarding and managing Kubernetes and Microservices applications securely.
   - It facilitates zero-touch, fully automated, and secured CI/CD pipelines.

![image](https://github.com/avengers-p7/Documentation/assets/156056444/0ca8d312-0b03-46d1-a85a-f17665008f4f) 
***

Let’s understand the advantages of CI with Jenkins with the following example

Let us imagine, that there are around 10 developers who are working on a shared repository. Some developer completes their task in 25 days while others take 30 days to complete.

| Before CI	| After CI |
| --------------- | -------------- |
| <p>Once all Developers had completed their assigned coding tasks, they used to commit their code all at same time. Later, Build is tested and deployed.</p> <p>Code commit built, and test cycle was very infrequent, and a single build was done after many days.</p> | <p>The code is built and test as soon as Developer commits code. Jenkin will build and test code many times during the day.</p> <p>If the build is successful, then Jenkins will deploy the source into the test server and notifies the deployment team.</p> <p>If the build fails, then Jenkins will notify the errors to the developer team.</p> |
| Since the code was built all at once, some developers would need to wait until other developers finish coding to check their build |	The code is built immediately after any of the Developer commits. |
| It is not an easy task to isolate, detect, and fix errors for multiple commits. |	Since the code is built after each commit of a single developer, it’s easy to detect whose code caused the built to fail |
| Code build and test process are entirely manual, so there are a lot of chances for failure. | Automated build and test process saving timing and reducing defects. |
| The code is deployed once all the errors are fixed and tested.	| The code is deployed after every successful build and test. |
| Development Cycle is slow | The development cycle is fast. New features are more readily available to users. Increases profits. |



## Real-world case study of Continuous Integration

I am sure all of you aware of old phone Nokia. Nokia used to implement a procedure called nightly build. After multiple commits from diverse developers during the day, the software built every night. Since the software was built only once in a day, it’s a huge pain to isolate, identify, and fix the errors in a large code base.

Later, they adopted Continuous Integration approach. The software was built and tested as soon as a developer committed code. If any error is detected, the respective developer can quickly fix the defect.
## Comparison b/w CI tools
| Criteria  | Jenkins | GitLab | BuildPiper |
| --------- | -------- | ------ | --------- |
| **Plugins** | 1700+ plugins |   Limited plugins |  Limited plugins/tools |
| **Prerequisites** | JRE should be installed	| Ruby, Go, Git, Node.js, and Redis should be installed | None |
| **Operating Systems Supported** |	Windows, Mac OS X, and Unix-like OS |	Supports only particular Unix-like OS such as Ubuntu, Debian, Red Hat Linux, Scientific Linux, Oracle Linux, CentOS, and OpenSUSE. It does not support Windows and macOS. | SAAS/Web |
| **Open Source**	| Open Source and Free	| Open Source and Freemium | Open Source and Freemium |
| **Issue Tracking**	| Don’t have such functionality	| Offers various features for issue tracking and management | Gain immediate insights into the potential reasons for a deployment failure- from service logs to container to pod status. |
| **Extensiveness** |	Highly extensive as it can be used as a simple CI server or can be transformed into a complex CD system with the help of plugins	| Offers scalability to enhance the DevOps lifecycle for a project | enables teams to onboard & securely manage Kubernetes & Microservices applications in a seamless manner. Also, the platform empowers teams with the ability to run zero-touch, fully automated & secured CI/CD pipelines. |
| **Support** |	Offers documentation and open source community support, but no technical support is provided as part of the SLA |	Provides 24×5 support for paid users and only self-support documents to free users as part of the SLA | Documentation , 24x7 and online suppprt |

***

## Conclusion
In the realm of CI/CD orchestration tools, Jenkins, GitLab, and BuildPiper each bring their unique strengths and characteristics to the table. After a thorough analysis, the choice between these tools ultimately depends on the specific needs and preferences of your project and team.

### Why Jenkins?
- Jenkins stands out as the preferred CI/CD orchestration tool for several reasons. Its extensive plugin ecosystem, comprising over 1700 plugins, ensures adaptability and flexibility for a variety of project requirements. 

- Being open-source and free, Jenkins fosters a collaborative community and provides scalability for projects of varying complexities. The robust community support, coupled with documentation, makes Jenkins a reliable choice. 

In conclusion, Jenkins offers a compelling combination of flexibility, extensibility, community support, and compatibility, making it a robust solution for CI/CD orchestration. However, it is crucial to assess your project's unique needs before making the final decision.
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
|     Jenkins vs Gitlab CI         | https://www.browserstack.com/guide/jenkins-vs-gitlab |
|     BuildPIper                   | https://www.buildpiper.io/documentation/docs/getting/introducing |
