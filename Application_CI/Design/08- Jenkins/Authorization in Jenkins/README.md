# Authorization in Jenkins
![image](https://github.com/avengers-p7/Documentation/assets/156056444/b4e57fae-f987-4feb-9bec-e90d149b3759)


| Author | Created on  | Version    | Last Updated by | Last Updated on |
| -------- | ------- | -------------- | --------------| ---------------- |
| **[Harshit Singh](https://github.com/Panu-S-Harshit-Ninja-07)**  | 29-01-2024  | 1.0   | Harshit Singh | 29-01-2024 |
***

## Table  of Contents

1. [Introduction](#Introduction)
2. [Why](#why)
3. [Authorization options](#Authorization-options)
4. [What is BuilPiper?](#what-is-buildpiper)
5. [Comparison](#Comparison)
6. [Conclusion](#Conclusion)
7. [Contact Information](#Contact-Information)
8. [References](#References)
***

## Introduction 

This documentation provides a brief information of Authorization methods provided by Jenkins.

Jenkins is an automation server that is self-contained and open source. It allows the building, testing, and deployment of every software release cycle. Through its fleet of plugins (over 1700) that seamlessly integrate with most CI/CD tools, Jenkins offers flexibility and covers almost all functional requirements.

Access Control is the primary mechanism for securing a Jenkins environment against unauthorized usage. Two facts of configuration are necessary for configuring Access Control in Jenkins:


1. The Security Realm, or `Authentication`, indicates who can access the Jenkins environment. 

2. The other piece of the puzzle is `Authorization`, which indicates what they can access in the Jenkins environment. 

![image](https://github.com/avengers-p7/Documentation/assets/156056444/05ce71b6-4e02-467e-af7f-37f94a33d41e)
***
## Why 
Authorization in Jenkins is essential for maintaining a secure and controlled environment for continuous integration and deployment.

| Reasons                   | Description                                               |
| ------------------------- | --------------------------------------------------------- |
| **Access Control**        | Restricting user access based on roles.                   |
| **Security**              | Preventing unauthorized access and potential breaches.    |
| **Compliance**            | Meeting regulatory standards through controlled access.   |
| **Configuration Control** | Managing who can modify job configurations.               |
| **Resource Control**      | Regulating access to distributed nodes or agents.         |

In essence, it ensures a secure, controlled, and compliant CI/CD environment.
## Authorization options
| Methods                                         | Description |
| ----------------------------------------------- | ----------------------------------------- |
| **Anyone can do anything**                      | Everyone gets full control of Jenkins, including anonymous users who haven’t logged in. Do not use this setting for anything other than local test Jenkins controllers. |
| **Legacy mode**                                 | Behaves exactly the same as Jenkins <1.164. Namely, if a user has the "admin" role, they will be granted full control over the system, and otherwise (including anonymous users) will only have the read access. Do not use this setting for anything other than local test Jenkins controllers. |
 | **Logged in users can do anything**            | In this mode, every logged-in user gets full control of Jenkins. Depending on an advanced option, anonymous users get read access to Jenkins, or no access at all. This mode is useful to force users to log in before taking actions, so that there is an audit trail of users' actions. |
| **Matrix-based security**                       | This authorization scheme allows for granular control over which users and groups are able to perform which actions in the Jenkins environment (see the screenshot below). |
| **Project-based Matrix Authorization Strategy** | This authorization scheme is an extension to Matrix-based security which allows additional access control lists (ACLs) to be defined for each project separately in the Project configuration screen. This allows granting specific users or groups access only to specified projects, instead of all projects in the Jenkins environment. The ACLs defined with Project-based Matrix Authorization are additive such that access grants defined in the Security screen will be combined with project-specific ACLs.<br>Matrix-based security and Project-based Matrix Authorization Strategy are provided by the Matrix Authorization Strategy Plugin and may not be installed on your Jenkins. |
|**Role-based Authorization Strategy** | The Role Strategy plugin is meant to be used from Jenkins to add a new role-based mechanism to manage users' permissions. Supported features <ul><li>Creating global roles, such as admin, job creator, anonymous, etc., allowing to set Overall, Agent, Job, Run, View and SCM permissions on a global basis.</li><li>Creating item roles, allowing to set item specific permissions (e.g Job, Run or Credentials) on Jobs, Pipelines and Folders.</li><li>Creating agent roles, allowing to set agent specific permissions.<\li><li>Assigning these roles to users and user groups<\li><\ul>
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
