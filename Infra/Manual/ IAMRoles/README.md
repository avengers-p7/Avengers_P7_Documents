## Create IAM Role
![image](https://github.com/avengers-p7/Documentation/assets/156056746/2c667c75-38b7-4758-b009-1d38fa556a86)

***
| Author | Created on | Last updated by | Last edited on |
|--------|------------|-----------------|----------------|
|Shikha Tripathi| 18-02-2024 | Shikha Tripathi | 18-02-2024|
***
## Table of Contents
+ [Introduction](#Introduction)
+  [Why](#Why)
+ [Features](#Features)
+ [Types of IAM Role in aws](#TypesofIAMRoleinaws)
+ [Flow Diagram](#FlowDiagram)
+ [Advantages](#Advantages)
+ [Disadvantages](#Disadvantages)
+ [Conclusion](#Conclusion)
+ [Contact Information](#Contact-Information)
+ [Resources and References](#Resources-and-References)

***
## Introduction
IAM (Identity and Access Management) roles in AWS (Amazon Web Services) are a fundamental aspect of managing access to resources securely. IAM roles provide a way to grant temporary permissions to entities such as users, applications, or AWS services without the need to share long-term credentials. This allows for dynamic access control, enhancing security while maintaining flexibility within AWS environments.

***
## Why 
IAM roles are created to delegate access permissions dynamically within AWS environments. Unlike IAM users, roles are not associated with specific individuals but rather with entities that need access to AWS resources. Roles enable organizations to implement the principle of least privilege by granting only the permissions required for specific tasks or workflows. This approach enhances security by reducing the risk of credential exposure and unauthorized access.

***
## Features 
| Feature	| Description |
|---------|-------------|
| **Temporary Credentials**	| IAM roles issue temporary security credentials, valid for a limited time, reducing the risk of credential exposure.|
| **Granular Permissions**	| IAM roles allow organizations to define precise permissions via IAM policies, ensuring entities access only necessary resources and actions.|
| **Cross-Account Access**	| IAM roles facilitate secure sharing of resources across AWS accounts, promoting collaboration while upholding security measures.|

***
## Flow Diagram
![image](https://github.com/avengers-p7/Documentation/assets/156056746/53355221-4d4d-4e7e-8fa1-5dd7cb03f87e)

***
## Types of IAM Role in aws
| Role Type	| Description |
|-----------|-------------|
| **IAM Roles**	| IAM roles are used to delegate permissions to entities within your AWS environment, such as IAM users, services, or federated users. They are commonly used for cross-account access and granting permissions to AWS services.|
| **Service Roles**| Service roles are IAM roles used by AWS services to perform specific actions on your behalf. For example, AWS Lambda functions often assume a service role to access other AWS resources.|
| **Cross-Account Roles** |	Cross-account roles allow IAM users in one AWS account to access resources in another AWS account. This type of role is commonly used for resource sharing or managing multi-account setups.|
| **EC2 Instance Roles** | (IAM)	EC2 instance roles (IAM roles) are used to grant permissions to EC2 instances. These roles allow applications running on EC2 instances to interact with other AWS services without requiring access keys.|
|**EC2 Instance Profile Roles**|	EC2 instance profile roles (also known as EC2 roles) are associated with EC2 instances and are used to grant permissions to applications running on those instances. They are similar to IAM roles but specific to EC2 instances.|
| **Lambda Execution Roles**	| Lambda execution roles are IAM roles used by AWS Lambda functions to access other AWS resources. These roles define the permissions needed by the Lambda function during execution.|
| **ECS Task Execution Roles**	| ECS task execution roles are IAM roles used by Amazon ECS tasks to access AWS resources. These roles define the permissions needed by ECS tasks to interact with other AWS services.|
| **S3 Bucket Access Roles**	| S3 bucket access roles are IAM roles used to grant cross-account access to Amazon S3 buckets. They allow other AWS accounts to access specific S3 buckets for various purposes.|

***

## Advantages 
| Advantage	| Description |
|-----------|-------------|
| **Enhanced Security**	| IAM roles enforce the principle of least privilege by granting temporary access tailored to specific needs, thereby reducing the risk of unauthorized access and potential security breaches.|
| **Least Privilege**	| IAM roles adhere to the principle of least privilege, ensuring entities have access only to necessary resources, minimizing the attack surface and enhancing security.|
| **Dynamic Access Control**	| IAM roles provide dynamic access control by issuing temporary credentials, allowing organizations to grant access for a limited time and revoke access when no longer needed, thus enhancing security.|

***
## Disadvantages 
| Disadvantage	| Description |
|---------------|-------------|
| **Complexity**	| Managing IAM roles and associated policies can introduce complexity, particularly with a growing number of roles and policies. Careful planning and documentation are required for effective access control.|
|**Policy Management** |	IAM roles necessitate the creation and management of IAM policies to define granular permissions. As policies become more complex, managing them can pose challenges, potentially leading to misconfigurations or access issues.|

***
**Step** 1: Inside the search bar type IAM and click on it.
![image](https://github.com/avengers-p7/Documentation/assets/156056746/22d1fb31-929e-460b-9639-de7c563679cd)

***
**Step** 2: Access the IAM Roles Section
![image](https://github.com/avengers-p7/Documentation/assets/156056746/202afacc-e6e7-44ea-8ab4-4571c9bd5dda)

***
**Step** 3: Select the Trusted Entity and the Use Case
![image](https://github.com/avengers-p7/Documentation/assets/156056746/4ba74e78-707a-4b44-8a9b-f4e692271758)

***
**Step** 4: Attach Permissions Policies
![image](https://github.com/avengers-p7/Documentation/assets/156056746/2ef3667a-de96-4bc1-8a08-dd66c1e9e159)

***
**Step**5: Add Role Details and Tags (Optional)
![image](https://github.com/avengers-p7/Documentation/assets/156056746/7c67eb5c-cab5-4de4-a2d2-c8aa3ef64e4e)

***
**Step**6: Role Creation Confirmation
![image](https://github.com/avengers-p7/Documentation/assets/156056746/a9ef7f81-281c-47a9-a4b0-a9f5dc4e232c)

***
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
| Link | https://medium.com/@favboladale/step-by-step-guide-how-to-create-iam-roles-in-aws-1652ccdee867|

