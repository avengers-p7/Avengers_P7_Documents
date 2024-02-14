# Shared Library Setup 

<img width="600" alt="image" src="https://github.com/avengers-p7/Documentation/assets/156057205/5ddddfd1-1ea8-486a-a81e-bcf784346e9a">

***

| Author  | Created on  | Version | Last Updated by | Last Updated on |
| ------  | ----------  | ------- | --------------- | --------------- |
| **Shreya Jaiswal** | **14-02-2024** | **1.0** | **Shreya Jaiswal** | **14-02-2024** |
***

# Table  of Contents

1. [Introduction](#Introduction)
2. [Prerequisites](#Prerequisites)
3. [Generate Personal Access Token(PAT)](#generate-personal-access-tokenpat)
4. [Add Credentials in Jenkins](#Add-Credentials-in-Jenkins)
5. [Global Pipeline Library Configuration](#Global-Pipeline-Library-Configuration)
6. [Create Pipeline using Jenkinsfile](#Create-Pipeline-using-Jenkinsfile)
7. [Contact Information](#Contact-Information)
8. [Reference](#Reference)
   
***

# Introduction

***

# Prerequisites

| Tool | Description |
| ---- | ----------- |
| Jenkins | For pipeline |
| GIT | To store Jenkinsfile in private repo |

> [!Important]
> I have installed the plugin bundle provided by Jenkins during setup. If you have not done the same, you may encounter plugin errors.

***

# Generate Personal Access Token(PAT)

## Step 1 - Go to your Github profile

![image](https://github.com/avengers-p7/Documentation/assets/156056444/20666213-cad3-4c0b-a4fa-07fcd7902793)

## Step 2 - Go to Settings

![image](https://github.com/avengers-p7/Documentation/assets/156056444/cd831c21-3327-472c-b58a-12265322517c)

## Step 3 - Select Developer Setting

![image](https://github.com/avengers-p7/Documentation/assets/156056444/3279196e-b243-4af7-a3a0-61a7359be041)

## Step 4 - Select Tokens --> Generate new token --> Generate new token(classic)

![image](https://github.com/avengers-p7/Documentation/assets/156056444/0e05f52e-b375-44de-97ab-824234b6cbbf)

## Step 5 - Enter Token Name --> Select Scopes/Permission(according to your requirement)

![image](https://github.com/avengers-p7/Documentation/assets/156056444/8657f90a-4e3a-4023-88b6-bf84394092e7)

## Step 6 - Scroll Down --> Click on Generate Token

![image](https://github.com/avengers-p7/Documentation/assets/156056444/46a0abf3-1bd6-478b-b7e1-61910704ef7c)

## Step 7 - Copy your  token and save it  

![image](https://github.com/avengers-p7/Documentation/assets/156056444/38704809-d3d3-4363-a780-0c97567d5948)

***
# Add Credentials in Jenkins

## Step 1 - Check GIT plugin, Go to Dashboard --> Manage Jenkins --> PLugins --> Installed Plugins

The git plugin provides fundamental git operations for Jenkins projects. It can poll, fetch, checkout, branch, list, merge, tag, and push repositories.

![image](https://github.com/avengers-p7/Documentation/assets/156056444/dd5e89aa-66b7-4272-9afe-1e99b772ba94)

If not present, install it form  **Dashboard --> Manage Jenkins --> PLugins --> Available Plugins**

## Step 2 - Go to Dashboard --> Manage Jenkins --> Credentials

![image](https://github.com/avengers-p7/Documentation/assets/156056444/7ddbd779-4cce-4ab8-b074-6ead1451db36)

## Step 3 - List down global --> Add Credentials 

![image](https://github.com/avengers-p7/Documentation/assets/156056444/88663437-cf1f-4d20-b6d6-f853ca572735)

## Step 4 - Select username and password option and  add your github userename, PAT , ID(optional) and description(optional)

![image](https://github.com/avengers-p7/Documentation/assets/156056444/d0a4cac0-52e7-4883-a05a-e24a166f3388)

## Step 5 - Here your credentials are added

![image](https://github.com/avengers-p7/Documentation/assets/156056444/094747b8-5a49-4ca6-a6cd-355f06b5ebea)

***

# Global Pipeline Library Configuration

## Go to Jenkins Dashboard ---> Manage Jenkins ---> System

***

## Scroll down to "Global Pipeline Library" section 
 
***

# Create Pipeline using Jenkinsfile 

## Step 1 - Go to Jenkins Dashboard --> New Item

![image](https://github.com/avengers-p7/Documentation/assets/156056444/95f92018-1a2e-4099-9e44-916a0419877a)

## Step 2 - Now, provide Git private repo url, credential, branchname and jenkinsfile path to  configure your pipeline 

![image](https://github.com/avengers-p7/Documentation/assets/156056444/25fe31e2-127d-45ef-bfd2-4a985a443f79)

![image](https://github.com/avengers-p7/Documentation/assets/156056444/a0172809-4206-4ebf-a050-4afd3bb24d44)

## Step 3 - You can build your pipeline now

![image](https://github.com/avengers-p7/Documentation/assets/156056444/ba41da3b-ec43-4493-bd89-245a42172771)

## Step 4 - Result

![image](https://github.com/avengers-p7/Documentation/assets/156056444/8fcc37f0-1187-41c3-bccd-ca9d6c75bcef)

***

# Conclusion

Shared libraries are invaluable tools in software development, offering numerous benefits such as code reusability, modularity, and memory efficiency. By following the recommended directory structure, including essential file types, and integrating with Jenkins using a Jenkinsfile, developers can effectively create, manage, and utilize shared libraries in their projects, promoting efficient development practices and enhancing overall productivity.

***

# Contact Information

| **Name** | **Email Address** |
| -------- | ----------------- |
| **Shreya Jaiswal** | shreya.jaiswal.snaatak@mygurukulam.co |

***

# Reference

| **Source** | **Description** |
| ---------- | --------------- |
| [Link](https://keentolearn.medium.com/how-to-improve-your-jenkins-builds-with-shared-libraries-5e225b7435fb#:~:text=A%20shared%20library%20in%20Jenkins,efficient%20and%20easier%20to%20maintain.) | Link For Shared Library |
| [Link](https://phoenixnap.com/kb/jenkins-shared-library) | Reference Link For Understanding the concept of Shared Library |
| [Link](https://www.youtube.com/watch?v=pQUDhOMZiZQ) | Video Reference For Shared Library |
| [Link](https://youtu.be/Wj-weFEsTb0?feature=shared) | Video Reference For Shared Library |










