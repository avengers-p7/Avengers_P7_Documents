##  IAM Users and Groups
***

| Author | Created on | Last updated by | Last edited on |
|--------|------------|-----------------|----------------|
|Shikha Tripathi| 15-02-2024 | Shikha Tripathi | 15-02-2024|

***
## Table of Contents
+ [Introduction](#Introduction)
+ [Features](#Features)
+ [Advantages](#Advantages)
+ [Disadvantages](#Disadvantages)
+ [Conclusion](#Conclusion)
+ [Contact Information](#Contact-Information)
+ [Resources and References](#Resources-and-References)

***
## Introduction to IAM Users and Groups
IAM (Identity and Access Management) in AWS provides robust control over access to resources within your AWS environment. IAM users and groups are fundamental entities that allow you to manage and control access to AWS services and resources securely.

***
## Features
| Feature	| IAM Users |	IAM Groups |
|---------|-----------|------------|
| **Definition** |	Individual identities within AWS | Collections of users with shared permissions |
|**Management** |	Managed individually	| Managed as a group |
| **Permissions**| Permissions assigned directly to individual users	| Permissions assigned to the group, inherited by users |
| **Scalability**	| Suitable for fine-grained access control of individuals |	Efficient for managing permissions for multiple users|
| **Flexibility**	|Flexible in defining permissions tailored to individual needs	| Offers centralized management for similar access needs |
| **Ease of Use**	| Requires managing permissions for each user individually	| Simplifies permissions management through grouping |
| **Auditability**	| Actions are tracked at the individual user level	| Actions are audited collectively for the group |
| **Security**	| Allows precise control over individual user access	Reduces risk of excessive permissions through group management|
| **Integration** |	Integrates seamlessly with various AWS services	|Integrates seamlessly with IAM policies and AWS services |
| **Use Cases**	| Granting access to specific individuals with unique needs	| Managing access for teams, departments, or applications |

