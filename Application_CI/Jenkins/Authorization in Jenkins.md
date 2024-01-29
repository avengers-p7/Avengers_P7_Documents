# Authentication  in Jenkins

| Author | Created on  | Version    | Last Updated by | Last Updated on |
| -------- | ------- | -------------- | --------------| ---------------- |
| **[Harshit Singh](https://github.com/Panu-S-Harshit-Ninja-07)**  | 29-01-2024  | 1.0   | Harshit Singh | 29-01-2024 |
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
## Comparison
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

Jenkins stands out as the preferred CI/CD orchestration tool for several reasons. Its extensive plugin ecosystem, comprising over 1700 plugins, ensures adaptability and flexibility for a variety of project requirements. Being open-source and free, Jenkins fosters a collaborative community and provides scalability for projects of varying complexities. The robust community support, coupled with documentation, makes Jenkins a reliable choice. 

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