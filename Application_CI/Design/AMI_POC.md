[AMI Setup](https://github.com/avengers-p7/Documentation/edit/main/Application_CI/Design/AMI.md#AMIsetup)
[Pre-requisites](https://github.com/avengers-p7/Documentation/edit/main/Application_CI/Design/AMI.md#pre-requisites)

# Pre-requisites

1. AWS Account
2. EC2 Instance
3. Ensure that your AWS account has the necessary IAM permissions to create, manage, and launch instances from AMIs.
4. Jenkins setup

***

# AMI Setup

**Step-1 Launch EC2 Instance**

Launching an instance before creating an AMI provides the opportunity to customize, configure, and test the environment, ensuring that the resulting AMI accurately represents the desired system state.

<img width="958" alt="Screenshot 2024-01-25 143104" src="https://github.com/avengers-p7/Documentation/assets/156057205/72d9cc22-11df-48ca-a2c0-80113ec4c586">

***

**Step-2 Jenkins Setup**

Setting up Jenkins for creating Amazon Machine Images (AMIs) with a Jenkins pipeline is a common practice for automating infrastructure processes.For AMI creation,we need plugins **"AWS Steps" "Amazon EC2"** and also,we need to configure **Clouds** section under **Manage Jenkins**
to add the necessary **AWS Credentials"** and **"Private key"**.

<img width="920" alt="Screenshot 2024-01-25 143300" src="https://github.com/avengers-p7/Documentation/assets/156057205/c3af0e46-e02e-4599-9e23-864fc65f489b">

***

**Step-3 Pipeline Creation**

Creating a Jenkins pipeline job for AMI creation brings automation, consistency, and integration benefits to the infrastructure provisioning process. It aligns with modern DevOps practices and facilitates the efficient management of infrastructure as code.
**Created a AMICreation Pipeline and configured it depending on the use case**.

<img width="949" alt="Screenshot 2024-01-25 134732" src="https://github.com/avengers-p7/Documentation/assets/156057205/db928af7-b8bb-4af9-85df-522a4abfac82">

***

<img width="925" alt="Screenshot 2024-01-25 134754" src="https://github.com/avengers-p7/Documentation/assets/156057205/25002fa9-6718-46cc-9a0d-5bd31dda7ed9">

 ***

 <img width="945" alt="Screenshot 2024-01-25 134820" src="https://github.com/avengers-p7/Documentation/assets/156057205/527be10f-a54a-4264-99c3-5e0b2f4189ae">

 ***

**Step-4 Build Step**

In this step,i have configured the pipeline with **Parameterized Job** in which,i have used **String Parameter**, **"Creator_Name"** and **"instance_id"** as a parameter,below is the result of this step.

<img width="950" alt="image" src="https://github.com/avengers-p7/Documentation/assets/156057205/d998c878-f251-4dce-b16a-f9d6a4a20469">

***

**Step-5 Console Output**

Output of the generated pipeline which shows the creation of AMI with **Success** status.

<img width="940" alt="Screenshot 2024-01-25 143124" src="https://github.com/avengers-p7/Documentation/assets/156057205/13fc046f-30a3-420b-afba-6467a433f8c5">

***

**Step-6 Confirmation of AMI Creation**

Here is the result of the AMI creation with pipeline with the help of jenkins.

<img width="939" alt="Screenshot 2024-01-25 143054" src="https://github.com/avengers-p7/Documentation/assets/156057205/56f1ed0c-40c3-4f0e-9836-b5800a17981a">

***

