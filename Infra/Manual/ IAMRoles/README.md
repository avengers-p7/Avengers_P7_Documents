## Create IAM Role
***
| Author | Created on | Last updated by | Last edited on |
|--------|------------|-----------------|----------------|
|Shikha Tripathi| 18-02-2024 | Shikha Tripathi | 18-02-2024|
***
## Table of Contents
+ [Introduction](#Introduction)
+  [Why](#Why)
+ [Features](#Features)
+ [Advantages](#Advantages)
+ [Disadvantages](#Disadvantages)
+ [Conclusion](#Conclusion)
+ [Contact Information](#Contact-Information)
+ [Resources and References](#Resources-and-References)

***
## Introduction
IAM (Identity and Access Management) roles in AWS (Amazon Web Services) are a fundamental aspect of managing access to resources securely. IAM roles provide a way to grant temporary permissions to entities such as users, applications, or AWS services without the need to share long-term credentials. This allows for dynamic access control, enhancing security while maintaining flexibility within AWS environments.

***
## Why Create IAM Roles
IAM roles are created to delegate access permissions dynamically within AWS environments. Unlike IAM users, roles are not associated with specific individuals but rather with entities that need access to AWS resources. Roles enable organizations to implement the principle of least privilege by granting only the permissions required for specific tasks or workflows. This approach enhances security by reducing the risk of credential exposure and unauthorized access.

***
Features of IAM Roles
| Feature	| Description |
|---------|-------------|
| **Temporary Credentials**	| IAM roles issue temporary security credentials, valid for a limited time, reducing the risk of credential exposure.|
| **Granular Permissions**	| IAM roles allow organizations to define precise permissions via IAM policies, ensuring entities access only necessary resources and actions.|
| **Cross-Account Access**	| IAM roles facilitate secure sharing of resources across AWS accounts, promoting collaboration while upholding security measures.|

***
## Advantages of IAM Roles
| Advantage	| Description |
|-----------|-------------|
| **Enhanced Security**	| IAM roles enforce the principle of least privilege by granting temporary access tailored to specific needs, thereby reducing the risk of unauthorized access and potential security breaches.|
| **Least Privilege**	| IAM roles adhere to the principle of least privilege, ensuring entities have access only to necessary resources, minimizing the attack surface and enhancing security.|
| **Dynamic Access Control**	| IAM roles provide dynamic access control by issuing temporary credentials, allowing organizations to grant access for a limited time and revoke access when no longer needed, thus enhancing security.|

***
## Disadvantages of IAM Roles
| Disadvantage	| Description |
|---------------|-------------|
| **Complexity**	| Managing IAM roles and associated policies can introduce complexity, particularly with a growing number of roles and policies. Careful planning and documentation are required for effective access control.|
|**Policy Management** |	IAM roles necessitate the creation and management of IAM policies to define granular permissions. As policies become more complex, managing them can pose challenges, potentially leading to misconfigurations or access issues.|

***
### Sign in to the AWS Management Console.
### Open the IAM console
![image](https://github.com/avengers-p7/Documentation/assets/156056746/2aa53365-b887-46c6-b816-d985456167ef)

*****
**In the navigation pane of the console, click on the ‘Roles’ and choose ‘Create role’ option**
![image](https://github.com/avengers-p7/Documentation/assets/156056746/e72ba297-3b88-44c3-9d00-c0bb43a65e43)



## Conclusion
IAM roles play a crucial role in managing access to AWS resources securely. By providing temporary credentials, granular permissions, and cross-account access, IAM roles enable organizations to implement dynamic access control while adhering to security best practices. While IAM roles offer significant advantages in terms of security and flexibility, organizations must also be mindful of the challenges associated with managing complexity and policy management. Overall, IAM roles are essential for maintaining a secure and compliant AWS environment while enabling organizations to meet their business needs effectively.

***
## Contact Information

|     Name         | Email  |
| -----------------| ------------------------------------ |
| Shikha Tripathi   | shikha.tripathi.snaatak@mygurukulam.co |
***

## References

| Description | References  
| ------------|-----------|
| Link |https://www.knowledgehut.com/tutorials/aws/iam-roles|

