# Authentication  in Jenkins
![image](https://github.com/avengers-p7/Documentation/assets/156056444/2ab655da-d1bd-4db7-be41-555d8368c98e)

| Author | Created on  | Version    | Last Updated by | Last Updated on |
| -------- | ------- | -------------- | --------------| ---------------- |
| **[Harshit Singh](https://github.com/Panu-S-Harshit-Ninja-07)**  | 29-01-2024  | 1.0   | Harshit Singh | 29-01-2024 |
***

## Table  of Contents

1. [Introduction](#Introduction)
2. [Prerquisites](#Prerquisites)
3. [Authentication Methods](#Authentication-Methods)
4. [Pros and Cons](#Pros-and-Cons)
5. [Conclusion](#Conclusion)
6. [Contact Information](#Contact-Information)
7. [References](#References)
***

## Introduction 
This documentation provides a brief information of Authentication methods provided by Jenkins.

Jenkins is an automation server that is self-contained and open source. It allows the building, testing, and deployment of every software release cycle. Through its fleet of plugins (over 1700) that seamlessly integrate with most CI/CD tools, Jenkins offers flexibility and covers almost all functional requirements.

Access Control is the primary mechanism for securing a Jenkins environment against unauthorized usage. Two facts of configuration are necessary for configuring Access Control in Jenkins:

1. A Security Realm which informs the Jenkins environment how and where to pull user (or identity) information from. Also commonly known as Authentication.

2. Authorization configuration informs the Jenkins environment as to which users and/or groups can access which aspects of Jenkins, and to what extent.
***
## Prerquisites
| Prerequisite | Description |
| ------------ | ------------ |
| **Jenkins Installation** | Jenkins server must be installed and accessible |
| **Administrator Access** | Administrative access to Jenkins instance |
| **Configure Security Realm** | Access to the Jenkins security configuration section |
***
## Authentication Methods
| Security Realm | Description |
| -------------- | ----------- |
| **Delegate to Servlet Container** | The "servlet container" refers to the web server that you are using to host Jenkins, typically Tomcat. The configuration file $CATALINA_BASE/conf/tomcat-users.xml may already be set up and managed by your organization. In this case: "why reinvent the wheel?". Use this if your organization already has a process that manages the Tomcat users configuration. This is also probably the most archaic solution. |
|**Jenkins Own User Database**| The "own user database" is just what it sound like. Instead of relying on something else, Jenkins keeps it's own database of users. You can create and delete users through the Jenkins UI. You can even let new users sign up right from UI. If you don't know what to use, use this one. It's simple and self-contained. |
|**LDAP (Lightweight Directory Access Protocol)**|The "LDAP" provides integration with LDAP/ Windows Active Directory. If you are in a corporate/small business environment that already utilizes LDAP for maintaining users and groups, it will be very beneficial to hook into that and off-load user management to the IT team that manages LDAP/AD. Note that unless you are that IT admin, you will need to contact the said admins for connection information/credentials to the LDAP/AD |
|**Unix User/Group Database**||



***
## Why Use Jenkins Own User Database?
BuildPiper is an end-to-end Kubernetes and Microservices Application Delivery Platform designed for developer and engineering teams. It offers a comprehensive set of features for managing the entire lifecycle of containerized applications.
   
   - BuildPiper is a one-stop solution for onboarding and managing Kubernetes and Microservices applications securely.
   - It facilitates zero-touch, fully automated, and secured CI/CD pipelines.

![image](https://github.com/avengers-p7/Documentation/assets/156056444/0ca8d312-0b03-46d1-a85a-f17665008f4f)
***
## Pros and Cons
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
