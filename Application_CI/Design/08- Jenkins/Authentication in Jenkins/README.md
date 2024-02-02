# Authentication  in Jenkins
![image](https://github.com/avengers-p7/Documentation/assets/156056444/2ab655da-d1bd-4db7-be41-555d8368c98e)

| Author | Created on  | Version    | Last Updated by | Last Updated on |
| -------- | ------- | -------------- | --------------| ---------------- |
| **[Harshit Singh](https://github.com/Panu-S-Harshit-Ninja-07)**  | 29-01-2024  | 1.0   | Harshit Singh | 29-01-2024 |
***

## Table  of Contents

1. [Introduction](#Introduction)
2. [Authentication Methods](#Authentication-Methods)
3. [Why Use Jenkins Own User Database?](##Why-Use-Jenkins-Own-User-Database)
4. [Limitations](#Limitations)
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
## Authentication Methods
| Security Realm | Description |
| -------------- | ----------- |
| **Delegate to Servlet Container** | The "servlet container" refers to the web server that you are using to host Jenkins, typically Tomcat. The configuration file $CATALINA_BASE/conf/tomcat-users.xml may already be set up and managed by your organization. In this case: "why reinvent the wheel?". Use this if your organization already has a process that manages the Tomcat users configuration. This is also probably the most archaic solution. |
|**Jenkins Own User Database**| The "own user database" is just what it sound like. Instead of relying on something else, Jenkins keeps it's own database of users. You can create and delete users through the Jenkins UI. You can even let new users sign up right from UI. If you don't know what to use, use this one. It's simple and self-contained. |
|**LDAP (Lightweight Directory Access Protocol)**|The "LDAP" provides integration with LDAP/ Windows Active Directory. If you are in a corporate/small business environment that already utilizes LDAP for maintaining users and groups, it will be very beneficial to hook into that and off-load user management to the IT team that manages LDAP/AD. Note that unless you are that IT admin, you will need to contact the said admins for connection information/credentials to the LDAP/AD |
|**Unix User/Group Database**| Delegates the authentication to the underlying Unix OS-level user database on the Jenkins controller. This mode will also allow re-use of Unix groups for authorization. For example, Jenkins can be configured such that "Everyone in the developers group has administrator access." To support this feature, Jenkins relies on PAM which may need to be configured external to the Jenkins environment. |
***
## Why Use Jenkins Own User Database?
BuildPiper is an end-to-end Kubernetes and Microservices Application Delivery Platform designed for developer and engineering teams. It offers a comprehensive set of features for managing the entire lifecycle of containerized applications.
   
   - BuildPiper is a one-stop solution for onboarding and managing Kubernetes and Microservices applications securely.
   - It facilitates zero-touch, fully automated, and secured CI/CD pipelines.

![image](https://github.com/avengers-p7/Documentation/assets/156056444/0ca8d312-0b03-46d1-a85a-f17665008f4f)
***
## Why Use Jenkins Own User Database?
Using Jenkins's own user database for authentication and authorization has several advantages, but the decision to use it depends on the specific needs and requirements of your environment. Here are some reasons why one might choose to use Jenkins's own user database:

1. **Simplicity and Quick Setup:**
   - Jenkins's internal user database is straightforward to set up and use. If you have a small to medium-sized team and want a quick and simple solution, relying on Jenkins's built-in user database can be an efficient choice.

2. **Out-of-the-Box Solution:**
   - Jenkins comes with its own authentication system by default, and it doesn't require additional configuration or integration with external identity providers initially. This makes it a convenient option for users who want to get started with Jenkins without setting up external authentication systems right away.

3. **Lightweight Installation:**
   - For smaller projects or environments where external authentication systems might be considered overkill, using Jenkins's own user database can be a lightweight and efficient solution without introducing unnecessary complexity.

4. **Local Control:**
   - When using Jenkins's own user database, administrators have direct control over user accounts, passwords, and access permissions without relying on external systems. This can be advantageous for organizations that prefer to manage everything locally.

5. **No Dependency on External Systems:**
   - Using Jenkins's own user database eliminates dependencies on external identity providers or directories. This can be beneficial in environments where external systems might be less reliable or more difficult to set up.

6. **Built-In User Management Features:**
   - Jenkins provides built-in features for user management, allowing administrators to create, modify, and delete user accounts directly from the Jenkins interface. This simplicity can be advantageous for smaller teams.

## Limitations
However, it's essential to consider the following considerations and potential limitations:

- **Limited Integration:** Jenkins's built-in user database might not integrate as seamlessly with other systems compared to using external authentication providers like LDAP, Active Directory, or OAuth.

- **Scalability Concerns:** For larger organizations or projects with complex authentication requirements, using an external identity provider might offer more scalability and flexibility.

- **Security Considerations:** Depending on the security policies of your organization, using an external identity provider might be preferred for centralized authentication and additional security features.

Ultimately, the choice between using Jenkins's own user database and an external authentication system depends on the specific needs, scale, and security requirements of your Jenkins environment.
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
