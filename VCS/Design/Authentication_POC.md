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
| **Repository Permissions**      |                                                        |
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
| **Account Permissions**         |                                                        |
| [Specify Account Permissions]   | [Description of Account Permissions]                   |
| [Another Account Permission]    | [Description of Another Account Permission]            |



# Step-by-Step Setup
**Signin** using username and password 
***
![Screenshot 2024-01-19 at 2 30 56 PM](https://github.com/avengers-p7/Documentation/assets/156056364/3163d867-e81d-4106-958e-0782a29e088b)
***

## Set up Two-factor Authentication
**Step-1:** Click on your GitHub profile photo, in the upper-right corner, and select Settings from the menu.
![image](https://github.com/avengers-p7/Documentation/assets/156056364/3d0a8d22-dc24-41ab-b3b1-a4b5a227040e)
***

**Step-2:** In the user settings sidebar, click Security.
![image](https://github.com/avengers-p7/Documentation/assets/156056364/b1d301c7-1e89-4f70-9d3b-e52ddf174e39)
***

**Step-3:** Under "Two-factor authentication" section, click Enable two-factor authentication.
![image](https://github.com/avengers-p7/Documentation/assets/156056364/59265454-41b4-467a-bfba-4830ab0fb78c)
***

## Creating Personal Access Token
**Step-1:** Select Settings from the menu
![image](https://github.com/avengers-p7/Documentation/assets/156056364/0549a08b-3ed4-439a-ad58-3f1110bec1cf)
***

**Step-2:** Next select “Developer Settings” as highlighted below.

![Screenshot 2024-01-19 at 2 54 16 PM](https://github.com/avengers-p7/Documentation/assets/156056364/573eeef8-54e1-42b5-9e3d-76ad53a4b43d)
***

**Step-3:** Next choose Personal Access Token
![image](https://github.com/avengers-p7/Documentation/assets/156056364/dc0e163c-8a35-41b7-a285-be7dc23ade17)
***

**Step-4:** Select Generate new token
![image](https://github.com/avengers-p7/Documentation/assets/156056364/c9eb825a-d8ad-41bf-bf75-25d9b6ea302c)
***

**Step-5:** Define the Name / Note of your token, Expiration and scopes then hit the green generate token button.
![image](https://github.com/avengers-p7/Documentation/assets/156056364/3bb48bcf-270c-4dfe-8d99-1411febae70a)
***

## SSH Key Configuration
**Step-1:** Create a GitHub SSH key on your local machine by using the ssh-keygen command.

**Step-2:** The public SSH key’s value should be copied to the clipboard.

**Step-3:** After logging in, go to your account settings on GitHub.
![image](https://github.com/avengers-p7/Documentation/assets/156056364/bf261024-cbfc-4d0c-8225-4cd2ce37f919)
***

**Step-4:** Select the SSH and GPG links.
![image](https://github.com/avengers-p7/Documentation/assets/156056364/944b6b15-c2ac-43bc-9362-a614bb952a2d)
***

**Step-5:** To link the public SSH key to your account, click Add Key.

**Step-6:** Put the copied value in the text box after naming the key.

**Step-7:** Save your changes

**Step-8:** Use the SSH-based GitHub URL in your Git client to clone your repository.

# Best Practices
* Implement access control
* Add security testing during development
* Rotate Personal Access Tokens and SSH keys
* Never hardcode credentials in GitHub

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
