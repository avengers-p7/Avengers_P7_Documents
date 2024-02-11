
| Author                                                           | Created on  | Version    | Last Updated by | Last Updated on |
| ---------------------------------------------------------------- | ----------- | ---------- | --------------- | --------------- |
| Nidhi Bhardwaj                                                    | 10-01-2024  | 1.0        | Nidhi Bhardwaj   | 10-02-2024      |


## Table  of Contents

1. [Introduction](#Introduction)
2. [What](#what)
3. [Why](#why)
4. [Authorization options](#Authorization-options)
5. [Role-based Authorization Strategy](#Role-based-Authorization-Strategy)
6. [Best Practices](#Best-Practices)
7. [Common Configuration Mistakes](#Common-Configuration-Mistakes) 
8. [Conclusion](#Conclusion)
9. [Contact Information](#Contact-Information)
10. [References](#References)
***

## Introduction 
This documentation provides a brief information of Authorization methods provided by Jenkins.

Jenkins is an automation server that is self-contained and open source. It allows the building, testing, and deployment of every software release cycle. Through its fleet of plugins (over 1700) that seamlessly integrate with most CI/CD tools, Jenkins offers flexibility and covers almost all functional requirements.

Access Control is the primary mechanism for securing a Jenkins environment against unauthorized usage. Two facts of configuration are necessary for configuring Access Control in Jenkins:


1. The Security Realm, or `Authentication`, indicates who can access the Jenkins environment. 

2. The other piece of the puzzle is `Authorization`, which indicates what they can access in the Jenkins environment. 

***
## What
Authorization (users are permitted to do something) is done by an authorization strategy. This controls whether a user (directly or through group memberships) has permission.
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
| **Access Control**            | <ul><li>**Granular Permissions** | Role-based strategies allow administrators to define specific permissions for each role, providing fine-grained control over who can perform which actions.</li><li>**Least Privilege Principle** | Users are granted only the permissions necessary for their tasks, following the principle of least privilege, reducing the risk of accidental or intentional misuse.</li></ul> |
| **Simplified Administration** | <ul><li>**Centralized Management** | Roles can be centrally managed, making it easier for administrators to assign and revoke permissions without needing to update individual user accounts.</li><li>**Scalability** | As the number of users and projects in Jenkins grows, role-based access control simplifies the management of permissions, making it more scalable.</li> |
| **Customization**             | **Project-Specific Roles** | Different projects within Jenkins may have unique requirements. Role-based strategies allow administrators to define roles specific to a project, tailoring permissions to meet the needs of each project.
| **Collaboration**             | **Facilitates Collaboration** | By assigning roles based on job responsibilities, teams can collaborate more effectively, knowing that each team member has the necessary permissions to perform their tasks. |

Role-Based Access Control Plugin in Jenkins provide the necessary functionality to implement role-based access control. These plugins allow administrators to define roles, assign permissions, and manage user access within Jenkins.
***
## Best practices
Best practices for authorization in Jenkins involve setting up effective access controls to ensure that users have the appropriate permissions for their tasks while preventing unauthorized access. Here are some key practices:
| Practice | Description |
| --------- | ----------- |
| **Role-Based Access Control (RBAC)** | Implement role-based access control to define and manage permissions based on user roles. Assign roles to users or groups, and regularly review and update these roles as responsibilities change.
| **Least Privilege Principle** | Follow the principle of least privilege by granting users the minimum permissions required to perform their tasks. Avoid providing excessive privileges that could lead to unintended actions or security vulnerabilities.
| **Use Groups for Authorization** | Leverage user groups to simplify authorization management. Assign permissions to groups rather than individual users, making it easier to manage access control as team structures evolve.
| **Regularly Review and Update Permissions** | Periodically review and update user permissions to align with current job responsibilities. Remove unnecessary permissions for users who no longer require them, and grant additional permissions as needed.
| **Audit User Access** | Enable auditing of user access to track who is accessing Jenkins and what actions they perform. Regularly review audit logs to identify any unusual or unauthorized activities.
| **Implement Workflow Approval** | For critical actions, implement workflow approval processes. Require additional approval steps before users can execute certain operations, reducing the risk of accidental or unauthorized changes.
| **Regularly Test and Validate Permissions** | Conduct regular testing to ensure that permissions are properly configured and enforced. Regular validation helps identify any misconfigurations or vulnerabilities in the authorization setup.
| **Backup and Restore Authorization Configurations** | Regularly backup authorization configurations to ensure quick recovery in case of accidental changes or system failures. Having a reliable backup allows for a faster restoration of the authorization setup.

By implementing these best practices for authorization, you can enhance the security of your Jenkins environment, prevent unauthorized access, and ensure that users have the appropriate level of access for their roles and responsibilities.

***
# POC of Authorization

First come first, we need to install the plugin;

Go to Manage Jenkins > Manage Plugins > Available and search for “Role-based Authorization Strategy”, check the box and click on Install without restart button, as shown in screen shot.

![Screenshot from 2024-02-10 16-22-46](https://github.com/avengers-p7/Documentation/assets/156644891/3660b040-948b-485e-b791-aa6aa3e8dd2e)


![Screenshot from 2024-02-11 20-44-37](https://github.com/avengers-p7/Documentation/assets/156644891/79f3a29a-5d2e-450a-9b0b-e6fcaea14de6)



After successful installation, go to Manage Jenkins > Confiure Global Security, and scroll down to the Authorization section and select the Role-Based Strategy option, see the below screenshot.


![Screenshot from 2024-02-11 20-50-05](https://github.com/avengers-p7/Documentation/assets/156644891/4c881dcf-d5fe-4fb9-892f-658e9749a5b9)


Manage and Assign Roles

Go to Manage Jenkins and scroll down to the last section named Uncategorized and click on Manage and Assign Roles > Manage Roles

![Screenshot from 2024-02-11 20-53-40](https://github.com/avengers-p7/Documentation/assets/156644891/67ddc91d-4fbc-43f2-b206-ed988fd4c5c7)



Manage Roles
Under the Manage Roles page we see two sections, one is Global roles and the other is Item roles, let’s start with Global roles;

Global roles:
Go to Manage Jenkins > Manage Plugins > Available and search for “Role-based Authorization Strategy”, check the box and click on Install without restart button, as shown in screen shot.

Under the Global roles section add a role with the name Employee and assign Read access inside the overall category, as shown in the screenshot below;


![image](https://github.com/avengers-p7/Documentation/assets/156644891/8e30bac5-35e5-4302-9a2e-b6b303458bf4)


Item roles:
Under the Item roles section add a role and a pattern to the role, for the role to add provide any role that is understandable with the porject in my case I have created Test_DEVs and for pattern provide the RE of the projects to be authorized to this user, as shown in the below screenshot;


![image](https://github.com/avengers-p7/Documentation/assets/156644891/ec17afa1-3ee2-4882-aa61-308bf4983629)


Note:

Test_DEVs is the role to be added and Test-.* is the RE, it means, only Test_DEVs can access all the project that starts with Test-,

.* means any combination after Test-.
We have done with Mange Roles, scroll down to the end of the page and click on Apply and then Save.


Assign Roles
Again go to Manage Jenkins > Manage and Assign Roles > Assign Roles under Under Assign Roles we need to work for Global roles and Item roles, lets do it;



Global role:
Under Global roles, provide the created user name i.e. test_user and click on the Add button, user will be added Global roles table and select the checkbox under the Employee, please see the screen shot;


![image](https://github.com/avengers-p7/Documentation/assets/156644891/df8433a2-333a-49b3-895b-83bb9d352001)


Item roles:
Under Item roles, provide the created user name i.e. test_user and click on the Add button, user will be added into Item roles table and select the checkbox under the Test-DEVs in front of test_user, please see the screen shot;


![image](https://github.com/avengers-p7/Documentation/assets/156644891/e0465f31-6e5c-49f3-b41a-7297315c66b1)


Now again go to the IP_Address/8080, provide the details for the test_user, you will see now permissions error is resolved and the user can now see all the assign projects.


![image](https://github.com/avengers-p7/Documentation/assets/156644891/6569085f-4c73-45e2-b902-c98e5da3cf87)






***

## Conclusion
In summary, Role-Based Strategy for authorization in Jenkins help us for establishing a secure, controlled, and scalable CI/CD environment. Role-based access control provides granular permissions, follows the least privilege principle, simplifies administration through centralized management, and allows customization for project-specific needs. By leveraging plugins like the Role-Based Access Control Plugin, Jenkins administrators can efficiently define roles, assign permissions, and manage user access, ensuring a streamlined and secure workflow.
***

## Contact Information

|     Name         | Email  |
| -----------------| ------------------------------------ |
| Nidhi Bhardwaj    | nidhi.bhardwaj.snaatak@mygurukulam.co |
***

## References

| Description                  | References  
| ------------------------ | ------------------------------------------------------------------- |
| Authorization in Jenkins | https://www.jenkins.io/doc/book/security/managing-security/ |
| Role Based Strategy      | https://plugins.jenkins.io/role-strategy/ |
| Common Mistakes | https://www.jenkins.io/doc/book/security/access-control/ |








