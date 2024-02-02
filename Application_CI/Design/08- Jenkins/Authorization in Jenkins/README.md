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
|**Role-based Authorization Strategy** | The Role Strategy plugin is meant to be used from Jenkins to add a new role-based mechanism to manage users' permissions. Supported features <ul><li>Creating global roles, such as admin, job creator, anonymous, etc., allowing to set Overall, Agent, Job, Run, View and SCM permissions on a global basis.</li><li>Creating item roles, allowing to set item specific permissions (e.g Job, Run or Credentials) on Jobs, Pipelines and Folders.</li><li>Creating agent roles, allowing to set agent specific permissions.</li><li>Assigning these roles to users and user groups</li></ul> |

![image](https://github.com/avengers-p7/Documentation/assets/156056444/096ec3e4-e76e-44ad-94d8-72cc4a5003e4)

***

## Role-based Authorization Strategy
Using a role-based strategy in Jenkins helps manage and control access to Jenkins resources based on predefined roles assigned to users or groups. This approach enhances security, simplifies administration, and ensures that users have the appropriate level of access for their responsibilities. Here are some key reasons for using a role-based strategy in Jenkins:

| Features                      | Description |
|------------------------------ | ------------- |
| **Access Control**            | <ul><li>**Granular Permissions:** Role-based strategies allow administrators to define specific permissions for each role, providing fine-grained control over who can perform which actions.</li><li>**Least Privilege Principle:** Users are granted only the permissions necessary for their tasks, following the principle of least privilege, reducing the risk of accidental or intentional misuse.</li></ul> |
| **Simplified Administration** | <ul><li>**Centralized Management:** Roles can be centrally managed, making it easier for administrators to assign and revoke permissions without needing to update individual user accounts.</li><li>**Scalability:** As the number of users and projects in Jenkins grows, role-based access control simplifies the management of permissions, making it more scalable.</li> |
| **Customization**             | **Project-Specific Roles:** Different projects within Jenkins may have unique requirements. Role-based strategies allow administrators to define roles specific to a project, tailoring permissions to meet the needs of each project.
| **Collaboration**             | **Facilitates Collaboration:** By assigning roles based on job responsibilities, teams can collaborate more effectively, knowing that each team member has the necessary permissions to perform their tasks. |

Role-Based Access Control Plugin in Jenkins provide the necessary functionality to implement role-based access control. These plugins allow administrators to define roles, assign permissions, and manage user access within Jenkins.
***

## Conclusion
In summary, Role-Based Strategy for authorization in Jenkins help us for establishing a secure, controlled, and scalable CI/CD environment. Role-based access control provides granular permissions, follows the least privilege principle, simplifies administration through centralized management, and allows customization for project-specific needs. By leveraging plugins like the Role-Based Access Control Plugin, Jenkins administrators can efficiently define roles, assign permissions, and manage user access, ensuring a streamlined and secure workflow.
***

## Contact Information

|     Name         | Email  |
| -----------------| ------------------------------------ |
| Harshit Singh    | harshit.singh.snaatak@mygurukulam.co |
***

## References

|     Description                  | References  
| ---------------------------------| ------------------------------------------------------------------- |
|         Authorization            | https://www.jenkins.io/doc/book/security/managing-security/ |
|     Role Based Strategy          | https://plugins.jenkins.io/role-strategy/ |
