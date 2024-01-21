# GitHub Authentication POC
***

|   Authors        |  Created on   |  Version   | Last updated by | Last edited on |
| -----------------| --------------| -----------|---------------- | -------------- |
| Shantanu  | 15 Jan 2024   |     v1     | Shantanu  | 21 Jan 2024    |
***

# Table of Content
1. Introduction
2. Advatages of PATs
3. Step-by-Step Setup
4. Best Practices
5. Conclusion
6. Contact Information
7. Refrences
***

# Introduction
Welcome to our GitHub Authentication Proof of Concept (POC). In this exploration, we are focusing on the implementation of Personal Access Tokens (PAT) as our chosen authentication method for GitHub. PATs offer a compelling combination of granular access control, enhanced security features including token expiration and revocation, seamless integration capabilities, and robust audit trails. This POC aims to underscore why PATs stand out as a versatile and secure choice among various GitHub authentication methods, emphasizing their effectiveness in modern development workflows. Join us as we delve into the advantages that make PATs the preferred authentication solution.
***

# Advatages of PATs

| Feature | Description |
| ------- | ----------- |
| Granular Access Control | Fine-grained control over permissions, allowing users to specify precise actions and access levels. |
| Token Expiry | Configurable expiration periods enhance security by automatically invalidating tokens after a specified timeframe. |
| Revocation Capabilities	 | Mechanisms to revoke PATs in real-time, providing administrators with prompt responses to security incidents. |
| Integration Flexibility	 | Seamless integration with various tools and workflows, supporting popular CI/CD systems and third-party applications. |
| Enhanced Security Practices	 | Generates unique tokens per user or application, reducing reliance on static credentials and aligning with best security practices. |
| Auditability | Detailed audit logs for token usage, offering transparency into access patterns and aiding in accountability. |
| User and Application Specificity	 | Generated on a per-user or per-application basis, ensuring tailored permissions and minimizing over-permissioned accounts. |
| Ease of Use	| Simple token generation, management, and usage through the GitHub interface, facilitating a straightforward authentication process. |

# Permissions

| Permission                     | Description                                            |
|---------------------------------|--------------------------------------------------------|
| **repo**                        | Grants full control of private repositories.            |
| **repo:status**                 | Enables access to commit status.                        |
| **repo_deployment**             | Allows access to deployment status for private repositories. |
| **public_repo**                 | Provides access to public repositories.                  |
| **repo:invite**                 | Allows access to repository invitations.                |
| **security_events**             | Grants access to security events.                       |
| **delete_repo**                 | Allows the deletion of repositories.                    |
| **admin:repo_hook**             | Grants full control of repository hooks.                |
| **write:repo_hook**             | Provides write access to repository hooks.              |
| **read:repo_hook**              | Allows read access to repository hooks.                 |
| **admin:org_hook**              | Provides full control of organization hooks.           |
| **write:org_hook**              | Grants write access to organization hooks.              |
| **read:org_hook**               | Allows read access to organization hooks.               |
| **admin:gpg_key**               | Grants full control of GPG keys for the repository.    |
| **write:gpg_key**               | Provides write access to GPG keys for the repository.   |
| **read:gpg_key**                | Allows read access to GPG keys for the repository.     |




# Step-by-Step Setup

**Step-1: Signin using username and password and 2FA, then click on settings under profile section.**

![Screenshot 2024-01-21 at 9 21 23 PM](https://github.com/avengers-p7/Documentation/assets/156056364/678cdbed-e7a4-47d7-9309-1b19cbfb7724)

**Step-2: Then click on developer settings.**
![Screenshot 2024-01-21 at 9 22 11 PM](https://github.com/avengers-p7/Documentation/assets/156056364/f546741e-865f-4143-89f7-77736b2eeebb)

**Step-3: Under PAT(Personal Access Tokens) choose either of Fine-grained tokens which is under Beta phase or classic Tokens to generate new tokens where in next step password will be prompted.**
![Screenshot 2024-01-21 at 9 27 20 PM](https://github.com/avengers-p7/Documentation/assets/156056364/64cf8e9f-b3f8-4c6a-94e4-adfee47ac083)

**Step-4: Provide token name, its expiration duration and a description. One can also control the access of repositories where the access can be made using repo access control and could provide permissions to control account access.**
![Screenshot 2024-01-21 at 9 33 33 PM](https://github.com/avengers-p7/Documentation/assets/156056364/314cf060-ae6d-4827-9e13-cda9a01a42d4)
![Screenshot 2024-01-21 at 9 34 02 PM](https://github.com/avengers-p7/Documentation/assets/156056364/99945d02-ea61-4e51-a331-057addb10887)

**Step-5: Generate token.**
***

# Best Practices
| Practices | Description |
| ---- | ------------- |
| Implement Access Control | Enforce role-based access and permissions on GitHub repositories to control who can view, contribute, or administer, ensuring a secure and organized collaborative development environment |
| Add Security Testing During Development | Integrate security testing tools into the development pipeline on GitHub to identify and address vulnerabilities early in the development process. |
| Rotate Personal Access Tokens and SSH Keys | Regularly update and replace Personal Access Tokens and SSH keys on GitHub to mitigate the risk of unauthorized access and enhance overall security. |
| Never Hardcode Credentials in GitHub | Avoid embedding sensitive credentials directly into code on GitHub to prevent exposure and adhere to security best practices in managing authentication information. |




# Conclusion
The successful implementation of best practices underscores the importance of robust authentication measures in safeguarding against unauthorized access. Lessons learned from the PoC will aid in future enhancements, ensuring a resilient and up-to-date security framework. Overall, this PoC lays a solid foundation for security in the verifying authentication of identity to access in GitHub. 

# Contact Information
| Name | Email Address |
| ---- | ------------- |
| Shantanu  | shantanu.chauhan.snaatak@mygurukulam.co |
# References
| Source | Description  | 
| -------- | ------- | 
| https://docs.github.com/en/authentication | Authentication |
| https://www.gitguardian.com/glossary/what-are-github-security-best-practices | Best Practices |
