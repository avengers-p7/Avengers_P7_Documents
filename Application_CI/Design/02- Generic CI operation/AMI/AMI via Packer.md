# POC For AMI Creation

| **Author** | **Created On** | **Last Updated** | **Document Version** |
| ---------- | -------------- | ---------------- | -------------------- |
| **Shreya Jaiswal** | **29-01-2024** | **01-02-2024** | **v1** |

***

# Table Of Contents

+ [Introduction](#introduction)
+ [Pre-requisites](#pre-requisites)
+ [Flow Diagram](#flow-diagram)
+ [Companies That Uses Packer](#companies-that-uses-packer)
+ [AMI Setup](#ami-setup)
+ [Conclusion](#conclusion)
+ [Contact Information](#contact-information)
+ [Reference](#reference)

***

# Introduction

![image](https://github.com/avengers-p7/Documentation/assets/156057205/6b8c1ba2-9c57-4d55-8092-04ea2eccaf84)


 Packer, a powerful open-source tool developed by HashiCorp, has emerged as a preferred choice for creating AMIs. Offering multi-platform 
 support, an infrastructure-as-code paradigm, and extensibility through various builders and provisioners, Packer streamlines the AMI creation 
 process. 

***

# Pre-requisites

| **Tool** | **Version** |
| -------- | ----------- |
| **Packer** | Packer.v1.10.0 |

***

# Flow Diagram 

<img width="866" alt="image" src="https://github.com/avengers-p7/Documentation/assets/156057205/10b0bc5e-9394-46e5-bf28-6a64d67c9522">

First, I created an EC2 instance, then generated an Amazon Machine Image (AMI) using the instance as the source. I retrieved the AMI ID and incorporated it into a Packer template file designed for AMI creation. Following this, I established a variable file to securely store the AWS access and secret keys. After installing Packer, I verified the version to ensure compatibility. Subsequently, I crafted a template file for AMI creation with a ".pkr.hcl" extension, wherein I specified the required configurations and saved the file. The process continued with the execution of the command "packer init" to initialize, followed by "packer build" incorporating the "variable file". Lastly, I confirmed the successful creation of the new AMI by checking the AWS Management Console.

***

# Companies That Uses Packer

| **Company** | **Description** |
| ----------- | --------------- |
| **HashiCorp** | HashiCorp, the creator of Packer, naturally incorporates Packer into its own DevOps and infrastructure workflows. |
| **Netflix** | Netflix is known for using a variety of DevOps tools, and Packer could be part of their infrastructure provisioning and automation. |
| **GitHub** | GitHub, a platform widely used for version control and collaboration, might use Packer in their infrastructure provisioning processes. |
| **Adobe** | Adobe, a multinational software company, is known to adopt various DevOps and infrastructure automation tools, and Packer could be part of their toolkit. |

***

# AMI Setup

**Step-1 Instance and AMI Creation for source AMI**

**Instance Creation**

Creating an Amazon Machine Image (AMI) involves launching an Amazon EC2 instance, customizing it to meet your requirements, and then creating an image from the instance.I have created an EC2 instance named **"New_Instance"**

![Screenshot 2024-01-30 005719](https://github.com/avengers-p7/Documentation/assets/156057205/4a2fe7c1-ca33-4046-b7fd-d6a95d98b914)

***

**AMI Creation**

when using Packer to create a new Amazon Machine Image (AMI), you typically start with an existing AMI as a base and then customize it according to your requirements. This existing AMI is specified using the source_ami parameter in your Packer configuration.I have created an AMI named **"New_Image"**

<img width="959" alt="image" src="https://github.com/avengers-p7/Documentation/assets/156057205/fd81eb33-762c-4cb4-80e1-881ad496c99c">

***

**Step-2 Variable File for storing AWS credentials**

Packer needs AWS credentials to authenticate and interact with your AWS account when creating and managing resources.For this, I have created a **"variables.pkrvars.hcl"** file to store AWS credentials.In this file, I have added the **"Access Key & Secret Key"**.

<img width="405" alt="image" src="https://github.com/avengers-p7/Documentation/assets/156057205/4b0da971-8e57-42b2-b585-357839c0af63">

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

<img width="950" alt="image" src="https://github.com/avengers-p7/Documentation/assets/156057205/12d832f9-2568-4fb4-bf96-2f9a6addc782">

***

**Step-6 Packer Initialization**

**"packer init"** is a command provided by Packer to initialize configuration files and download any necessary plugins. It helps ensure the correctness and consistency of your configuration files and plugin dependencies.

![Screenshot 2024-01-30 010052](https://github.com/avengers-p7/Documentation/assets/156057205/05298741-a85c-49fb-bb18-55189107d740)

***

**Step-7 Building the .pkr.hcl file**

To use the packer build command, navigate to the directory containing your Packer configuration file. Running this command kicks off the process of building the machine image according to the specifications in your Packer configuration.

> [!NOTE]
> Run the **"packer build"** command with **"-var-file"** option to specify the variable file.This way, you are supplying the necessary AWS credentials to Packer without hardcoding them directly in your Packer configuration file. 

<img width="731" alt="image" src="https://github.com/avengers-p7/Documentation/assets/156057205/e42dddaa-7be9-4dea-9e92-944f57c742af">

***

**Step-8 Confirmation of AMI Creation from AWS Console**

Once the process of AMI Creation completes,check the newly created AMI from the AWS Console to confirm the creation of AMI. 

<img width="959" alt="image" src="https://github.com/avengers-p7/Documentation/assets/156057205/d128a319-0168-41d3-a6c2-8048039b660a">

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

