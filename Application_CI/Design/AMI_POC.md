# POC For AMI Creation

| **Author** | **Created On** | **Last Updated** | **Document Version** |
| ---------- | -------------- | ---------------- | -------------------- |
| **Shreya Jaiswal** | **29-01-2024** | **30-01-2024** | **v1** |

***

# Table Of Contents

1. [Introduction](https://github.com/avengers-p7/Documentation/edit/main/Application_CI/Design/AMI_POC.md#introduction)
2. [Pre-requisites](https://github.com/avengers-p7/Documentation/edit/main/Application_CI/Design/AMI_POC.md#pre-requisites)
3. [AMI Creation Process](https://github.com/avengers-p7/Documentation/edit/main/Application_CI/Design/AMI_POC.md#AMIcreation)
4. [Conclusion](https://github.com/avengers-p7/Documentation/edit/main/Application_CI/Design/AMI_POC.md#conclusion)
5. [Contact Information](https://github.com/avengers-p7/Documentation/edit/main/Application_CI/Design/AMI_POC.md#contactinformation)
6. [Reference](https://github.com/avengers-p7/Documentation/edit/main/Application_CI/Design/AMI_POC.md#reference)
 
***

# Introduction

 Packer, a powerful open-source tool developed by HashiCorp, has emerged as a preferred choice for creating AMIs. Offering multi-platform 
 support, an infrastructure-as-code paradigm, and extensibility through various builders and provisioners, Packer streamlines the AMI creation 
 process. 

***

# Pre-requisites

1. AWS Account
2. EC2 Instance
3. Ensure that your AWS account has the necessary IAM permissions to create, manage, and launch instances from AMIs.
4. Jenkins setup

***

# AMI Setup

**Step-1 Instance and AMI Creation for the requirement of AMI_ID**

![Screenshot 2024-01-30 005719](https://github.com/avengers-p7/Documentation/assets/156057205/4a2fe7c1-ca33-4046-b7fd-d6a95d98b914)



***

**Step-2 AWS Configure**

![Screenshot 2024-01-30 010140](https://github.com/avengers-p7/Documentation/assets/156057205/6cff8c8b-6a34-414a-b253-d64c23879f95)

***

**Step-3 Installation of Packer**
Ensure that Packer is installed on your local machine. You can download the latest version from the official Packer website.

![Screenshot 2024-01-30 005924](https://github.com/avengers-p7/Documentation/assets/156057205/45545f06-acb5-4ff2-ac62-270845f6b152)

***

![Screenshot 2024-01-30 005947](https://github.com/avengers-p7/Documentation/assets/156057205/c73fef4b-5dfd-4943-8412-6899fd9708d6)

***

![Screenshot 2024-01-30 010011](https://github.com/avengers-p7/Documentation/assets/156057205/6d8d1029-c757-45fd-8598-6a4ef7751213)


***

**Step-4 Checking Packer Version**


![Screenshot 2024-01-30 010025](https://github.com/avengers-p7/Documentation/assets/156057205/29401eeb-3778-4cc0-8dcb-c5b194fb211b)


***

**Step-5 Template File for AMI Craetion with ".pkr.hcl" extension**

<img width="943" alt="image" src="https://github.com/avengers-p7/Documentation/assets/156057205/781f6ce4-897e-4c86-83c8-eaff3ad0e646">


***

**Step-6 Packer Initialization**

![Screenshot 2024-01-30 010052](https://github.com/avengers-p7/Documentation/assets/156057205/05298741-a85c-49fb-bb18-55189107d740)


***

**Step-7 Building the .pkr.hcl file**

![Screenshot 2024-01-30 005806](https://github.com/avengers-p7/Documentation/assets/156057205/3a42fdac-f3cd-4740-b68d-c68534496611)


***

**Step-8 Confirmation of AMI Creation from AWS Console**

![Screenshot 2024-01-30 005653](https://github.com/avengers-p7/Documentation/assets/156057205/bafb650e-19e1-403d-8a91-18611f1468bd)

***

# Conclusion

In conclusion, Packer stands out as a robust and versatile tool for AMI creation.With Packer, organizations can achieve consistency, scalability, and maintainability in their infrastructure, while benefiting from a vibrant community and seamless integration with other HashiCorp tools.As the landscape of cloud computing continues to evolve, Packer remains a valuable asset for those aiming to optimize their AMI creation processes on AWS.

***

# Contact Information

| **Name** | **Email Address** |
| -------- | ----------------- |
| **Shreya Jaiswal** | shreya.jaiswal.snaatak@mygurukulam.co |

***

# Reference

| **Source** | **Description** |
| ---------- | --------------- |
|            |                 |
|            |                 |

