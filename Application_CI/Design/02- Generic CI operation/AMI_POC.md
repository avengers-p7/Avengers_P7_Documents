# POC For AMI Creation

| **Author** | **Created On** | **Last Updated** | **Document Version** |
| ---------- | -------------- | ---------------- | -------------------- |
| **Shreya Jaiswal** | **29-01-2024** | **30-01-2024** | **v1** |

***

# Table Of Contents

1. [Introduction](#introduction)
2. [Pre-requisites](#pre-requisites)
3. [AMI Creation Process](#AMIcreation)
4. [Conclusion](#conclusion)
5. [Contact Information](#contactinformation)
6. [Reference](#reference)
 
***

# Introduction

 Packer, a powerful open-source tool developed by HashiCorp, has emerged as a preferred choice for creating AMIs. Offering multi-platform 
 support, an infrastructure-as-code paradigm, and extensibility through various builders and provisioners, Packer streamlines the AMI creation 
 process. 

***

# Pre-requisites

1. AWS CLI Configured
2. EC2 Instance for source of AMI ID Generation
3. Packer Installed

***

# AMI Setup

**Step-1 Instance and AMI Creation for source of AMI_ID**

**Instance Creation**

Creating an Amazon Machine Image (AMI) involves launching an Amazon EC2 instance, customizing it to meet your requirements, and then creating an image from the instance.I have created an EC2 instance named **"New_Instance"**

![Screenshot 2024-01-30 005719](https://github.com/avengers-p7/Documentation/assets/156057205/4a2fe7c1-ca33-4046-b7fd-d6a95d98b914)

***

**AMI Creation**

when using Packer to create a new Amazon Machine Image (AMI), you typically start with an existing AMI as a base and then customize it according to your requirements. This existing AMI is specified using the source_ami parameter in your Packer configuration.I have created an AMI named **"New_Image"**

<img width="958" alt="image" src="https://github.com/avengers-p7/Documentation/assets/156057205/f2639637-8554-4369-843d-f1d46152dcec">

***

**Step-2 AWS Configure**

Packer needs AWS credentials to authenticate and interact with your AWS account when creating and managing resources. Configuring the AWS CLI allows Packer to leverage the credentials stored in the AWS CLI configuration.

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

After all the installation process,just make sure that Packer is installed successfully.For this we can use the command **"packer --version"**.

![Screenshot 2024-01-30 010025](https://github.com/avengers-p7/Documentation/assets/156057205/29401eeb-3778-4cc0-8dcb-c5b194fb211b)

***

**Step-5 Template File for AMI Craetion with ".pkr.hcl" extension**

Create a Packer template file in either JSON or HashiCorp Configuration Language (HCL). This file defines the configuration for building the AMI, including the source image, provisioners, and post-processors.Created a template file named **"ami.pkr.hcl"**.

<img width="943" alt="image" src="https://github.com/avengers-p7/Documentation/assets/156057205/781f6ce4-897e-4c86-83c8-eaff3ad0e646">

***

**Step-6 Packer Initialization**

**"packer init"** is a command provided by Packer to initialize configuration files and download any necessary plugins. It helps ensure the correctness and consistency of your configuration files and plugin dependencies.

![Screenshot 2024-01-30 010052](https://github.com/avengers-p7/Documentation/assets/156057205/05298741-a85c-49fb-bb18-55189107d740)

***

**Step-7 Building the .pkr.hcl file**

To use the packer build command, navigate to the directory containing your Packer configuration file. Running this command kicks off the process of building the machine image according to the specifications in your Packer configuration.

![Screenshot 2024-01-30 005806](https://github.com/avengers-p7/Documentation/assets/156057205/3a42fdac-f3cd-4740-b68d-c68534496611)

***

**Step-8 Confirmation of AMI Creation from AWS Console**

Once the process of AMI Creation completes,check the newly created AMI from the AWS Console to confirm the creation of AMI. 

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
| https://www.pluralsight.com/cloud-guru/labs/aws/using-packer-to-create-an-ami | Reference Link AMI Setup |
| https://developer.hashicorp.com/packer/tutorials/aws-get-started/aws-get-started-build-image | Link for Installation of Packer and AMI Creation |

