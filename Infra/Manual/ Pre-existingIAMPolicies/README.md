## Pre-existing IAM Policies
![image](https://github.com/avengers-p7/Documentation/assets/156056746/ef3954ab-e2ee-4310-b4ce-af2862ccd7f5)

***
| Author | Created on | Last updated by | Last edited on |
|--------|------------|-----------------|----------------|
|Shikha Tripathi| 20-02-2024 | Shikha Tripathi | 20-02-2024|

***
## Table of Contents
+ [Introduction](#Introduction)
+  [Why Pre-existing IAM Policies ](#WhyPre-existingIAMPolicies)
+ [Features Pre-existing IAM Policies ](#FeaturesPre-existingIAMPolicies)
+ [Advantages](#Advantages)
+ [Disadvantages](#Disadvantages)
+ [Conclusion](#Conclusion)
+ [Contact Information](#Contact-Information)
+ [Resources and References](#Resources-and-References)

***
## Introduction
Identifying pre-existing IAM (Identity and Access Management) policies to be used is a critical step in managing access to AWS (Amazon Web Services) resources securely. These policies define the permissions granted to IAM users, groups, or roles within an AWS environment. By leveraging pre-existing IAM policies, organizations can streamline access management, enforce security best practices, and ensure compliance with regulatory requirements.

***
## Why Identify Pre-existing IAM Policies
Identifying pre-existing IAM policies allows organizations to leverage existing access control configurations and best practices. This helps reduce redundancy, promote consistency, and simplify access management processes. By utilizing established IAM policies, organizations can expedite the implementation of access controls, minimize the risk of misconfigurations, and improve overall security posture within their AWS environments.

****
## Features of Pre-existing IAM Policies
| Feature	| Description |
|---------|-------------|
| **Granular Permissions**	| Pre-existing IAM policies offer granular control over access to AWS resources, allowing organizations to define precise permissions for actions and resources.|
| **Scalability**	 | With a range of pre-existing IAM policies available, organizations can scale access management efforts efficiently as their AWS infrastructure grows.|
| **Flexibility**| Pre-existing IAM policies provide flexibility to accommodate diverse use cases and requirements, ensuring that access controls align with organizational needs.|

***
## Pre-existing IAM Policies Best Practices
| IAM Policy	| Description |	Best Practices |
|-------------|-------------|----------------|
| AWSManagedAdministratorAccess	| Full administrative access to AWS services and resources.	| Use sparingly and restrict to trusted administrators.|
| ReadOnlyAccess | Grants read-only access to AWS services and resources.| Assign to auditors or users who only require read access.|
| AmazonS3FullAccess | Full access to Amazon S3 buckets and objects.| Avoid granting to users who don't need full S3 access.|
| AmazonEC2FullAccess | Full access to Amazon EC2 instances and resources.| Assign to administrators responsible for managing EC2.|
| AmazonRDSFullAccess | Full access to Amazon RDS resources.| Limit access to users responsible for managing RDS.|
| AWSLambdaFullAccess	| Full access to AWS Lambda functions and resources.| Assign to developers responsible for managing Lambda.|
| AmazonDynamoDBFullAccess | Full access to Amazon DynamoDB resources.| Assign to users responsible for managing DynamoDB.|
## Advantages of Identifying Pre-existing IAM Policies
| Advantage	| Description |
|-----------|-------------|
| **Time Efficiency**| Leveraging pre-existing IAM policies saves time by avoiding the need to create policies from scratch, facilitating faster implementation of access controls.|
| **Consistency**	| By using standardized IAM policies, organizations can maintain consistency in access management across their AWS environments, reducing the risk of configuration errors and access discrepancies.|
| **Compliance**	| Pre-existing IAM policies often incorporate security best practices and regulatory compliance requirements, assisting organizations in meeting industry standards and regulatory obligations.|

***
## Disadvantages of Identifying Pre-existing IAM Policies
| Disadvantage |	Description |
|--------------|--------------|
| **Limitations**	| Pre-existing IAM policies may not always align perfectly with specific organizational requirements, necessitating customization or the creation of supplementary policies.|
| **Complexity**	| Managing a large number of pre-existing IAM policies can introduce complexity, requiring effective organization, documentation, and ongoing review to ensure proper access controls.|


***
## Pre-existing IAM Policies
**Step**1: 
![image](https://github.com/avengers-p7/Documentation/assets/156056746/8cf615e0-1881-4e0e-829a-6bd9a3c5bf7a)
***
**step**2:
![image](https://github.com/avengers-p7/Documentation/assets/156056746/88763758-06f9-4ae2-a202-3fd1a7afc01a)

***
**Step**3: 
![image](https://github.com/avengers-p7/Documentation/assets/156056746/5cbe08ed-79c1-4fc4-aa0e-627f78067d73)
***

## Conclusion
Identifying pre-existing IAM policies is a strategic approach to access management in AWS environments, offering efficiency, consistency, and compliance benefits. While pre-existing policies streamline access control implementation and promote security best practices, organizations must also address challenges such as policy limitations and complexity. By leveraging pre-existing IAM policies effectively and supplementing them as needed, organizations can establish robust access controls that align with their security objectives and regulatory obligations within AWS environments.

***
## Contact Information

|     Name         | Email  |
| -----------------| ------------------------------------ |
| Shikha Tripathi   | shikha.tripathi.snaatak@mygurukulam.co |
***

## References

| Description                                   | References  
| --------------------------------------------  | -------------------------------------------------|
| Link |https://deliciousbrains.com/wp-offload-media/doc/custom-iam-policy-for-amazon-s3/|



