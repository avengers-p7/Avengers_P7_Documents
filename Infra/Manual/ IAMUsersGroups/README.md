##  IAM Users and Groups
![image](https://github.com/avengers-p7/Documentation/assets/156056746/75cb9f03-0340-46bd-b882-7c5e5849aa4e)

***

| Author | Created on | Last updated by | Last edited on |
|--------|------------|-----------------|----------------|
|Shikha Tripathi| 15-02-2024 | Shikha Tripathi | 15-02-2024|

***
## Table of Contents
+ [Introduction](#Introduction)
+ [ Why Create IAM Users and Groups](#WhyCreateIAMUsersandGroups)
+ [ Features of IAM Users and Groups](#FeaturesofIAMUsersandGroups)
+ [Advantages of IAM Users and Groups](#AdvantagesofIAMUsersandGroups)
+ [Disadvantages of IAM Users and Groups](#DisadvantagesofIAMUsersandGroups)
+ [Conclusion](#Conclusion)
+ [Contact Information](#Contact-Information)
+ [Resources and References](#Resources-and-References)

***
## Introduction
IAM (Identity and Access Management) users and groups are fundamental components of AWS (Amazon Web Services) security, allowing organizations to manage access to their AWS resources. IAM users represent individual entities (such as employees or applications) that interact with AWS, while IAM groups are collections of users with similar access requirements. Creating IAM users and groups enables organizations to enforce security policies, control resource access, and maintain compliance within their AWS environments.

***
## Why Create IAM Users and Groups
Creating IAM users and groups is essential for implementing secure access control mechanisms in AWS. By assigning unique credentials and permissions to each IAM user and organizing users into groups based on their roles or responsibilities, organizations can ensure that users have the necessary access to perform their tasks while adhering to the principle of least privilege. Additionally, IAM users and groups enable centralized management of access policies, facilitating efficient administration and auditability of AWS resources.

***
## Features of IAM Users and Groups
| Feature	| Description |
|---------|-------------|
| **Granular Access Control**	| IAM users and groups enable organizations to define fine-grained permissions, specifying the actions users can perform on AWS resources.|
| **Role-Based Access**| IAM groups facilitate role-based access control by grouping users with similar access requirements and assigning them relevant permissions.|
| **Centralized Management**	| IAM users and groups support centralized management of access policies, simplifying administration and ensuring consistent enforcement of security policies across the organization's AWS environment.|

***
## Flow Diagram
![image](https://github.com/avengers-p7/Documentation/assets/156056746/3e05497a-8ff7-4b1f-8ce7-814247fc4cc2)


***

## Advantages of IAM Users and Groups
| Advantage |	Description |
|-----------|-------------|
| **Enhanced Security**	| IAM users and groups enable organizations to enforce the principle of least privilege, reducing the risk of unauthorized access and potential security breaches.|
| **Scalability**	With IAM users and groups, organizations can easily scale access control mechanisms as their AWS infrastructure grows, accommodating changes in user roles or resource requirements.|
| **Simplified Administration**	| Centralized management of IAM users and groups streamlines administration tasks, such as provisioning and deprovisioning access, minimizing administrative overhead.|

***
## Disadvantages of IAM Users and Groups
| Disadvantage	| Description |
|---------------|-------------|
| **Complexity**	| Managing a large number of IAM users and groups can introduce complexity, requiring careful organization and documentation to ensure effective access control. |
| **Potential for Misconfiguration** |	Incorrectly configured IAM policies or group memberships can result in unintended access restrictions or security vulnerabilities, necessitating thorough testing and regular review.|

***

## IAM Users and Groups add best practices 
| Best Practice |	Description |
|---------------|-------------|
| **Unique User Identifiers**	| Ensure each IAM user has a unique identifier (username) to avoid confusion and maintain accountability.|
| **Enable Multi-Factor Authentication (MFA)**| Enforce MFA (Multi-Factor Authentication) for IAM users, adding an extra layer of security to their accounts.|
| **Group-Based Permissions**	| Assign permissions to groups rather than individual users, facilitating easier management and scalability.|
| **Least Privilege Principle**	| Assign permissions to groups with the minimum necessary privileges, following the principle of least privilege.|
|**Use IAM Roles**	| Utilize IAM roles for temporary access instead of long-term credentials, enhancing security and reducing risk.|
| **Regular Review** | Regularly review IAM users, groups, and permissions to ensure they align with current business requirements and follow security best practices.|
| **Enable CloudTrail**| Enable AWS CloudTrail to monitor and log API calls made on the AWS account, providing visibility into user activity.|
| **Rotate Credentials Regularly**|	Regularly rotate IAM user access keys and passwords to mitigate the risk of unauthorized access due to compromised credentials.|
| **Implement Strong Password Policies** |	Enforce strong password policies for IAM users to enhance security and reduce the risk of unauthorized access.|
***
### How to create your first IAM user and user group
![image](https://github.com/avengers-p7/Documentation/assets/156056746/1361ef75-84a7-4a07-935e-9ea77ff166aa)

***
### Navigate to AWS Services and search for IAM to access the IAM console.
![image](https://github.com/avengers-p7/Documentation/assets/156056746/3e256943-917a-4af7-821f-af8ba4ea6267)

***
###  From the IAM console select Users on the left-handside and click Add Users
![image](https://github.com/avengers-p7/Documentation/assets/156056746/20dc7c1c-263d-4c27-a250-bada6be0824d)

***
 **Under User name type 'Administrator'**

 **Check the box: Password - AWS Management Console access**

 **In Console password, create a custom password**

 **Uncheck the box 'Require password reset'**

 **Click: permissions**
 ![Screenshot from 2024-02-19 06-32-29](https://github.com/avengers-p7/Documentation/assets/156056746/e74d7817-b67f-4feb-857c-e45d8aa6ea24)
 
 ***
 ## Navigate to Users and click 'Add permissions
 ![Screenshot from 2024-02-19 06-34-50](https://github.com/avengers-p7/Documentation/assets/156056746/4bcb6a13-7f3f-4b5e-a955-aefd56a960a9)

 ***
 ## Select 'Add User to Group' and click Create Group
 
![image](https://github.com/avengers-p7/Documentation/assets/156056746/a51e401a-c129-4f84-ab92-bef229b0a409)

***
## Select 'EC2 full Access' and then click 'Create group'
![Screenshot from 2024-02-19 06-40-05](https://github.com/avengers-p7/Documentation/assets/156056746/c21715a8-f7bf-42b0-b9f0-44048e413efb)


***
## Refresh your web browser so you can see the newly created Dev group that was created under Users group.
![Screenshot from 2024-02-19 06-40-35](https://github.com/avengers-p7/Documentation/assets/156056746/553f5731-d7d4-43d8-b9fc-eec61015c704)

***
## Under the Dev group Ec2 full access is provided to AWS services
![Screenshot from 2024-02-19 06-40-05](https://github.com/avengers-p7/Documentation/assets/156056746/1083e506-50be-4a2c-96f1-deaf3cb1dba6)

***
## Confirmation that new Dev user has been successfully created

![Screenshot from 2024-02-19 06-43-54](https://github.com/avengers-p7/Documentation/assets/156056746/44125a62-2c2a-41f9-9716-90788a8b2393)



***



## Conclusion
IAM users and groups are essential components of AWS security, enabling organizations to enforce access control policies, manage user permissions, and maintain compliance within their AWS environments. While they offer advantages such as enhanced security and scalability, organizations must also address challenges such as complexity and the potential for misconfiguration. Overall, IAM users and groups play a critical role in establishing robust access control mechanisms and ensuring the security of AWS resources.


***


## Contact Information

|     Name         | Email  |
| -----------------| ------------------------------------ |
| Shikha Tripathi   | shikha.tripathi.snaatak@mygurukulam.co |

***

## References

| Description                                   | References  
| --------------------------------------------  | -------------------------------------------------|
| Link |https://dev.to/aws-builders/creating-your-first-iam-admin-user-and-user-group-in-your-aws-account-machine-learning-part-1-3cne|
