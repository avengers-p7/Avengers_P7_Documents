| Author | Created On | Last Updated | Document Version |
| ------ | ---------- | ------------ | ---------------- |
| Shreya Jaiswal | 16-01-2024 | 16-01-2024 | V1 |
----------------------------------------------------------------------------------------------------------------------------

# Agenda

**1.Introduction**

**2.Why GitHub Authorization?**

**3.Key Features**

**4.Images of GitHub Authorization Features**

**5.Conclusion**

**6.Contact Information**

**7.References**

----------------------------------------------------------------------------------------------------------------------------

# Introduction

This document serves as a comprehensive guide to understanding and implementing effective authorization practices within our GitHub repositories.The primary purpose of this documentation is to establish a robust framework for managing access to GitHub repositories within Your Organization.By defining clear access levels, implementing audit trails, and integrating with identity providers, we aim to strike a balance between collaboration and security. 

----------------------------------------------------------------------------------------------------------------------------

# Why GitHub Authorization?

GitHub authorization refers to the process of controlling and managing access to GitHub repositories, organizations, and resources. It involves defining and assigning permissions to users or teams, specifying what actions they can perform within a repository or organization. Authorization is a crucial aspect of ensuring the security and integrity of source code and project assets stored on GitHub.

----------------------------------------------------------------------------------------------------------------------------

# Key Features

| Feature | Description |
| ------- | ----------- |
| **Access Levels** | Access levels on GitHub define the permissions users have within a repository or organization. There are three primary access levels:**Read**: Users with read access can view the repository's code, issues, and other resources but cannot make modifications.**Write**: Users with write access can make changes to the repository, create new branches, and open pull requests. However, they don't have administrative control.**Admin**: Users with admin access have full control over the repository. They can manage access, settings, and perform administrative tasks. |
| **Default Access Levels** | GitHub provides default access levels such as contributors, collaborators, and administrators. Contributors can submit pull requests, collaborators have write access, and administrators have full control. |
| **Custom Access Levels** | Organizations can create custom access levels to tailor permissions to specific needs. This allows for fine-grained control, enabling administrators to define precisely what actions users can perform. |
| **Teams and Collaborators** | Users can be organized into teams, and specific permissions can be granted to entire teams, streamlining access management for larger projects with multiple contributors. |
| **Individual Repository Permissions** | GitHub allows fine-grained control over individual repository permissions. Repository administrators can specify who can contribute, review, merge changes, and perform other actions. |
| **Organization-wide Permissions** | For organizations, administrators can set permissions that apply across all repositories within the organization. This ensures consistent access control policies for all projects.\
| **Audit Trails** | GitHub provides audit trail features that log and track user actions within repositories. This helps in monitoring and reviewing changes, ensuring accountability, and identifying any security-related issues. |
| **Integration with Identity Providers** | GitHub supports integration with external identity providers, enabling organizations to leverage existing authentication systems. This integration enhances security by ensuring that only authorized users can access GitHub resources. |
| **OAuth Tokens** | GitHub uses OAuth tokens for authentication and authorization. Users or applications obtain tokens with specific scopes, granting them access to perform actions on behalf of the authenticated entity. |

----------------------------------------------------------------------------------------------------------------------------

# GitHub Authorization Features

## 1.Access Level

 By assigning appropriate access levels (read, write, admin), organizations can ensure that users have the necessary permissions for their roles without granting excessive privileges.
 

![image](https://github.com/avengers-p7/Documentation/assets/156057205/6e3eca2d-876b-46ac-b988-c6d4ce398568)


***

## 2.OAuth Tokens

OAuth (Open Authorization) is an open standard for access delegation, commonly used as a way for Internet users to grant third-party websites or applications access to their information without sharing their credentials.


![image](https://github.com/avengers-p7/Documentation/assets/156057205/2393b26d-262f-4114-977e-b409f0f74ed6)

***

## 3.Audit Trail

GitHub provides audit logs that record actions performed by users within repositories. Actions logged include push events, pull request creations, and changes to access controls. These logs are essential for tracking changes, identifying security incidents, and maintaining accountability.


![image](https://github.com/avengers-p7/Documentation/assets/156057205/afc70c73-000e-4965-aadf-e3c3745726e4)


***

## 4.Collaborators

In GitHub, a collaborator is an individual or entity with specific permissions granted by the repository owner. Collaborators have varying levels of access based on the roles assigned to them. 


![image](https://github.com/avengers-p7/Documentation/assets/156057205/5ff6d6a6-7563-4374-a823-6f507c901174)


----------------------------------------------------------------------------------------------------------------------------

# Conclusion

In conclusion, GitHub's robust access control features, audit trails, and integration with identity providers collectively contribute to creating a secure and collaborative development environment. The balance between providing the right level of access and maintaining accountability is crucial for organizations leveraging GitHub for their source code management.

----------------------------------------------------------------------------------------------------------------------------

# Contact Information

| Name | Email Address |
| ---- | ------------- |
| Shreya Jaiswal | shreya.jaiswal.snatak@mygurukulam.co |

----------------------------------------------------------------------------------------------------------------------------

# References

| Link | Description |
| ---- | ----------- |
| https://www.geeksforgeeks.org/audit-trail/ |  Link for Audit Trail |
| https://www.tutorialspoint.com/oauth2.0/index.htm | GitHub Feature |
| https://docs.deepsource.com/docs/access-control-managing-access-to-your-teams-repositories | Access Level |

