## Create Custom IAM Policies
![image](https://github.com/avengers-p7/Documentation/assets/156056746/575ab188-fd7b-49d3-8003-9149e33254b6)

***
| Author | Created on | Last updated by | Last edited on |
|--------|------------|-----------------|----------------|
|Shikha Tripathi| 15-02-2024 | Shikha Tripathi | 15-02-2024|

***
## Table of Contents
+ [Introduction](#Introduction)
+  [Why Custom IAM Policies](#WhyCustomIAMPolicies)
+ [Features Custom IAM Policies ](#FeaturesCustomIAMPolicies)
+  [ Create Custom IAM Policies best practices](#CreateCustomIAMPoliciesbestpractices)
+ [Flow Diagram](#FlowDiagram)
+ [Advantages](#Advantages)
+ [Disadvantages](#Disadvantages)
+ [ Create Custom IAM Policies](#CreateCustomIAMPolicies)
+ [Conclusion](#Conclusion)
+ [Contact Information](#Contact-Information)
+ [Resources and References](#Resources-and-References)

***
## Introduction
Custom IAM (Identity and Access Management) policies allow organizations to finely control access to AWS (Amazon Web Services) resources according to their specific requirements. While AWS provides predefined policies, custom IAM policies offer tailored access control, granting or denying permissions based on specific conditions.

***
## Why Create custom IAM policies
| Aspect | Description |
|--------|-------------|
| **Clarity and Organization**| Information is presented in a structured manner, making it easier for readers to understand policy components.|
| **Conciseness**	| Tabular formats allow for concise representation of policy elements, aiding in understanding permissions/resources.|
| **Readability**	| Tables provide visually appealing presentation, enhancing readability and comprehension of IAM policy details.|
| **Easy Comparison**	| Side-by-side display enables easy comparison of permissions, actions, and resources across different policies.|
| **Quick Reference**	| Tables serve as quick reference guides, facilitating efficient location of specific permissions or resources.|
| **Documentation Standardization**	| Adopting a consistent tabular format aids in standardizing IAM policy documentation, supporting collaboration.|

***
## Features of Custom IAM Policies
| Aspect | Description |
|--------|-------------|
| **Granular Control** |	Custom IAM policies enable organizations to define precise permissions, specifying actions users or roles can perform on AWS resources with fine granularity.|
|**Conditional Access**	| Policies can include conditions based on attributes like time, IP address, or resource tags, adding layers of security and flexibility to access control mechanisms.|
|**Versioning and Rollback**	| IAM policies support versioning, allowing organizations to track changes over time and rollback to previous versions if necessary, ensuring policy management robustness.|
| **Integration with AWS Services**	| Custom policies seamlessly integrate with various AWS services such as IAM roles, S3 bucket policies, and resource-based policies for services like Lambda and SQS.|

***
## Flow Diagram
![image](https://github.com/avengers-p7/Documentation/assets/156056746/e8bbb0e6-abab-4972-81f5-aed75cb23db7)


***
##  Advantages of Custom IAM Policies
| Aspect | Description |
|--------|-------------|
| **Tailored Access Control**	| Organizations can create policies precisely matching their security and compliance needs, reducing the risk of over-permissive access to AWS resources.|
|**Least Privilege Principle**	| Custom policies adhere to the principle of least privilege, granting only the necessary permissions for users or roles to fulfill their tasks, enhancing security posture.|
| **Flexibility and Scalability**	| Custom policies offer flexibility to adjust access control according to evolving business requirements and scale permissions as AWS infrastructure expands.|
| **Enhanced Security**| Custom IAM policies leverage conditions and constraints to bolster security measures, reducing the risk of unauthorized access and potential security breaches.|
***
## Disadvantages of Custom IAM Policies
 | Aspect | Description |
 |--------|-------------|
 | **Complexity**	| Custom IAM policies can introduce complexity, especially as the number of policies and resources grows. Managing and maintaining numerous policies may require significant administrative effort and expertise.|
 | **Expertise Requirement** |	Developing effective custom IAM policies requires expertise in IAM policy syntax, cloud platform-specific configurations, and understanding of organizational security requirements. Organizations may need to invest in training or hire skilled personnel for policy management.|
 | **Increased Administrative Overhead**	| Creating and managing custom IAM policies can result in increased administrative overhead. This includes tasks such as policy creation, testing, deployment, and regular updates to align with changing security needs.|
 | **Risk of Misconfiguration**| Incorrectly configured custom IAM policies can lead to security vulnerabilities or access restrictions that impede operations. Human error or misinterpretation of requirements during policy creation and updates can pose significant risks.|

 ***
 ## Create Custom IAM Policies best practices
 | Best Practice |	Description |
 |---------------|-------------|
 | **Least Privilege Principle**|	Assign the minimum permissions required for a user or role to perform their tasks.|
 | **Use Policy Conditions**	| Utilize conditions to restrict access further based on various factors such as IP address, time of day, or user agent.|
 | **Regular Review**	| Regularly review and audit IAM policies to ensure they remain relevant and least-privileged. Remove unnecessary permissions.|
 |**IAM Policy Simulator**	| Use the IAM Policy Simulator to test policies before applying them to users or roles.|
 | **Separation of Duties**	| Implement separation of duties by creating different policies for different roles, preventing any single user from having excessive permissions.|
 | **Immutable Policies**	| Prefer immutable policies over inline policies. Immutable policies are versioned and cannot be modified directly. This ensures better control and auditability.|

 **Note:** After creating the policy, attach it to the appropriate IAM users or roles. Regularly review and update the policy as necessary based on changing requirements and security best practices.

 ***
 
 ## Create custom IAM policies
**Step**1: ![Screenshot from 2024-02-15 19-53-44](https://github.com/avengers-p7/Documentation/assets/156056746/5a2c63ae-b9ba-4370-bace-db7d1f4129fa)
***
![Screenshot from 2024-02-19 04-56-01](https://github.com/avengers-p7/Documentation/assets/156056746/09694d96-6cf2-488a-aab7-e637374c4a4c)


***
**Step**2: ![Screenshot from 2024-02-19 05-00-25](https://github.com/avengers-p7/Documentation/assets/156056746/202a1f27-f991-4f10-bdb2-730f0d36a7ea)

***
**Step** 3: ![Screenshot from 2024-02-19 05-01-23](https://github.com/avengers-p7/Documentation/assets/156056746/04aa18d0-dccf-4c87-a191-c35786fbaa50)


***

 ## Conclusion
 Custom IAM policies enable organizations to precisely manage access to AWS resources, ensuring compliance with security standards. While they offer tailored control and enhanced security, they can also pose challenges such as complexity and administrative overhead. Despite these drawbacks, their benefits in enforcing least privilege and scalability outweigh the challenges, making them crucial for maintaining secure AWS environments. Overall, custom IAM policies are essential for organizations seeking fine-grained access control and robust security measures in their AWS infrastructure.
 


## Contact Information

|     Name         | Email  |
| -----------------| ------------------------------------ |
| Shikha Tripathi   | shikha.tripathi.snaatak@mygurukulam.co |
***

## References

| Description                                   | References  
| --------------------------------------------  | -------------------------------------------------|
| Link |https://deliciousbrains.com/wp-offload-media/doc/custom-iam-policy-for-amazon-s3/|




