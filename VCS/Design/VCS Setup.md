# Github Documentation

| Author | Created on | last updated | Document Version | **Last Updated By** |
| ------ | ---------- | ------------ | ---------------- | ------------------- |
| Nidhi  | 15-01-24   | 20-01-24     |  V1              | Nidhi |

***

# Table Of Contents

**1. Introduction**

**2. Features And Description**

**3. Prerequisites**

**4. Installation Setup**

**5. Conclusion**

**6. Contact Information**

**7. Reference**


***


# Introduction

 This document will walk you through the step-by-step process of installing GitHub, an essential platform for version control and collaborative software development.GitHub is a web-based 
 platform and version control system that plays a crucial role in modern software development. It provides a collaborative environment for developers to host, manage, and share their code 
 repositories. 

***

# Features And Description

| Feature | Description |
| ------- | ----------- |
| **Version Control** | GitHub serves as a distributed version control system, built on top of Git. It allows developers to track changes in their code, collaborate on projects, and manage different versions of their software.|
|**Repository Hosting**|GitHub provides a platform for hosting code repositories. Developers can create repositories to store and organize their project files, making it easy to manage and share code with others|
|**Collaboration**|GitHub facilitates collaboration among developers. Multiple contributors can work on the same project simultaneously by cloning repositories, creating branches, and merging changes|
|**Branching and Merging**|GitHub supports branching, enabling developers to work on isolated features or bug fixes in separate branches. Changes made in these branches can be merged back into the main codebase when ready|
|**Pull Requests**|Pull Requests (PRs) are a mechanism for proposing changes to a project. Developers can submit PRs to suggest changes made in their branches, allowing others to review the code before it's merged|
|**Issue Tracking**|GitHub includes an issue tracking system that allows users to report and discuss bugs, request new features, and manage project-related tasks. It provides a centralized way to organize and prioritize work|
|**GitHub Actions**|GitHub Actions is an integrated CI/CD (Continuous Integration/Continuous Deployment) service. It enables developers to automate workflows, such as running tests, building applications, and deploying software directly from the repository|
|**Community and Social Features**|GitHub fosters a sense of community among developers. Users can follow each other, star repositories, and contribute to open-source projects. This social aspect encourages collaboration and knowledge sharing|
|**Documentation**|GitHub provides a space for project documentation. Developers can include README files and other documentation to explain the purpose, usage, and contribution guidelines for their projects|
|**Licensing**|GitHub includes features for managing software licenses. This is important for open-source projects to define how others can use, modify, and distribute the code|

***

# Prerequisites 

* Working Email ID 

***

# Setup via Web browser

 **Step-1** Create a GitHub Account

Go to GitHub's website and sign up for a new account if you don't have one.

![Screenshot from 2024-01-15 18-52-23](https://github.com/avengers-p7/Documentation/assets/156644891/9bb7f8b4-3d71-41c3-aaf6-b347e3fb50d0)

***

**Step-2** Verification

Verify your email address to complete the registration process.

![Screenshot from 2024-01-15 18-52-48](https://github.com/avengers-p7/Documentation/assets/156644891/905779c6-5dfe-45d2-9c57-0ed8cad33063)

***

**Step-3** Explore GitHub

Once logged in, you can explore GitHub repositories, contribute to projects, and create your own repositories.

![Screenshot from 2024-01-16 11-27-23](https://github.com/avengers-p7/Documentation/assets/156644891/57f2017b-f91a-4e03-9a13-b127543d9d5c)

***

# Organization Creation
Organizations provide a way to group and manage repositories. They are particularly useful for businesses, open-source projects, or any scenario where you have multiple repositories and collaborators.

**Use Case/Example**: If you are working on a software development project with a team, creating an organization allows you to centralize repositories related to that project. For instance, if you're developing a web application, you might create an organization named "MyWebApp" to house all related repositories.


![Screenshot from 2024-01-18 18-08-30](https://github.com/avengers-p7/Documentation/assets/156644891/55d3a536-309b-4cfd-b616-e28bb80e2014)


## How to Create an Organization


![Screenshot from 2024-01-16 11-35-53](https://github.com/avengers-p7/Documentation/assets/156644891/7644efd9-7d0b-44a3-a509-54d9ee14f811)


***

![Screenshot from 2024-01-16 11-46-08](https://github.com/avengers-p7/Documentation/assets/156644891/9be801f3-155e-434a-8dfb-3e67180ab9df)


***


![Screenshot from 2024-01-16 11-49-09](https://github.com/avengers-p7/Documentation/assets/156644891/559e5207-5c21-461d-b27d-dba31caa0e12)

***

![Screenshot from 2024-01-16 11-49-46](https://github.com/avengers-p7/Documentation/assets/156644891/3b22f335-68b1-4ac9-844c-12e547890994)

***

# Repository Creation 

Repositories are where your project's source code and related files are stored. Each repository typically corresponds to a specific project or component of your software.

**Use Case/Example**: Continuing with the example, you would create a repository within the "MyWebApp" organization to store the source code, configuration files, and documentation for your web application. This allows your team members to collaborate on the codebase, track changes, and manage versions effectively.

***

![Screenshot from 2024-01-16 11-51-31](https://github.com/avengers-p7/Documentation/assets/156644891/913f8f43-f11c-49c8-93de-c704f92bb4ea)

***

# Team Creation

Teams help organize members within an organization and control access to repositories. By creating teams, you can manage permissions and collaboration more effectively.

**Use Case/Example**: Within the "MyWebApp" organization, you might have different teams such as "Developers," "Testers," and "Designers." Each team can have specific permissions for different repositories. For example, the "Developers" team may have write access to the source code repository, while the "Testers" team may only have read access.

***
![Screenshot from 2024-01-16 14-06-39](https://github.com/avengers-p7/Documentation/assets/156644891/2cb91edd-6eae-466c-bd97-508ea25173fc)


***

![Screenshot from 2024-01-16 14-07-40](https://github.com/avengers-p7/Documentation/assets/156644891/252d3950-1977-4e6a-83d3-7cb437476fc8)


***
#  Version Control System

Version Control Systems (VCS) are tools that help manage changes to source code and other files over time. There are two main types of version control systems: centralized and distributed. Below, I'll provide a brief description of each type along with a simplified diagram to illustrate the concepts.

**1. Centralized Version Control System (CVCS)**:
In a centralized system, there is a single central repository that stores the entire version history of the project. Developers clone the latest version from this central repository, make changes locally, and then commit those changes back to the central server.


![Screenshot from 2024-01-20 20-56-03](https://github.com/avengers-p7/Documentation/assets/156644891/ad69b520-a1e0-4747-9e34-12a4b08b4a88)

**Centralized Repository**: The central server stores the entire history of the project.

**Developer A and B**: Developers clone the latest version, make changes, and commit back to the central repository.


**2. Distributed Version Control System (DVCS)**:

In a distributed system, each developer has their own complete copy (clone) of the repository, including the entire history. Developers can work independently, commit changes locally, and share their changes with others by pushing and pulling between repositories.

![Screenshot from 2024-01-20 20-59-50](https://github.com/avengers-p7/Documentation/assets/156644891/73f9bdd4-584b-482c-91e5-a5603e016ae5)


**Developer A and B**: Each developer has a local repository with the complete project history.

**Local Repositories**: Developers work independently in their local repositories.

**Remote Repositories**: Developers push and pull changes to and from remote repositories, enabling collaboration.


**3. Local Version Control System (LVCS):**

A Local VCS involves a single database on the user's hard disk that keeps track of changes to files. It allows users to revert files to a previous state and track changes within a single system.

 ![Screenshot from 2024-01-22 16-09-01](https://github.com/avengers-p7/Documentation/assets/156644891/a3d8c3a5-f00e-48d7-b337-194dbbb3d78f)

**Working Directory**: A box labeled "Working Directory" represents the directory where your project files are stored.

**Local Database**: Another box labeled "Local Database" represents the database or system that the Local VCS uses to keep track of changes.

**Arrows**: An arrow pointing from the "Working Directory" to the "Local Database" indicates that changes made in the working directory are recorded in the local database.

***

# Conclusion  

In conclusion, this GitHub Setup Documentation has guided you through the essential steps to establish a solid foundation for version control and collaborative development. GitHub's features will empower you to optimize your development workflow, collaborate efficiently, and maintain code quality. Embrace the collaborative nature of GitHub to elevate your coding projects to new heights. 

# Contact Information

| Name | Email ID |
|----- | -------- |
| NIDHI BHARDWAJ | nidhi.bhardwaj.snaatak@mygurukulam.co |

***

# Reference

| Reference  | Description |
| ---------  | ----------- |
| https://docs.github.com/en | Link For Documentation |
| https://phoenixnap.com/kb/how-to-install-git-windows | Link For Setup |

***






