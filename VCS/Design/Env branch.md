# Environment branch workflow

|   Author     |  Created on   |  Version   | Last updated by | 
| ------------ | --------------| -----------|---------------- |
| Vikram BISHT | 16 Jan 2024   |     v1     | Vikram Bisht    | 

---
# Introduction
### Environment Branch Workflow in VCS
In version control systems, branching is a powerful feature that allows developers to work on new features or bug fixes without affecting the main codebase. This document describes an environment branch workflow in Git, which is a popular version control system. This workflow is based on creating separate branches for different environments, such as development, staging, and production.

# Need of Environment Branch
The environment branch workflow is useful for teams that work on large projects with multiple environments. It helps to ensure that changes are properly tested and reviewed before being deployed to production. By using separate branches for each environment, teams can avoid conflicts and maintain a stable codebase.

# Types of Environment Branches

|  Types                   |        Description                                                                                                 |
| ------------             | ---------------------------------------------------------------------------------------------------------          |
| Development Branch       |  This is where all new features and bug fixes are developed and tested                                             |  
| Testing Branch           |  This environment is dedicated to comprehensive testing to identify and fix bugs before moving to the next stage   |
| Staging Branch           | This environment closely mirrors the production environment and serves as a final testing ground before deployment |
| Production Branch        | The production branch contains the stable and tested code that is ready for deployment to the live environment     |


# Env Branch Flow
The environment branch workflow involves the following steps:
* Create a new feature branch from the development branch.
* Make changes and commit them to the feature branch.
* Open a pull request to merge the feature branch into the development branch.
* Once the changes have been reviewed and tested, merge the feature branch into the staging branch.
* Test the changes in the staging environment.
* If the changes are successful, merge the staging branch into the production branch.
* Deploy the changes to the live site.

<img width="750" length="500"  src="![image](https://github.com/avengers-p7/Documentation/assets/156056709/c2e4c381-5149-4b68-bcbf-a99cbae35a14)
">

***
 
# Advantages

| Advantage          | Description                                                                                                     |
| ------------------ | --------------------------------------------------------------------------------------------------------------- |
| Isolation          | By using separate branches for each environment, teams can avoid conflicts and maintain a stable codebase.      |
| Testing            | Changes can be thoroughly tested in the staging environment before being deployed to production.                  |
| Review             | Pull requests allow for code reviews, which can help to catch bugs and improve code quality.                     |
| Auditing           | Environment branches provide a clear record of changes, which can be useful for auditing and debugging.           |


# Disadvantages

| Disadvantage | Description                                                                                                   |
| ------------ | ------------------------------------------------------------------------------------------------------------- |
| Complexity   | The environment branch workflow can be complex, particularly for large teams simultaneously working on multiple features. |
| Overhead     | Creating and merging branches can introduce additional overhead to the development process.                   |
| Delay        | There may be a delay between making changes and deploying them to the production environment.                   |

# Conclusion 
The environment branch workflow is a useful tool for teams that work on large projects with multiple environments. By using separate branches for each environment, teams can maintain a stable codebase, thoroughly test changes, and ensure that code is reviewed before being deployed to production. However, the workflow can be complex and add overhead to the development process.


# Contact Information

|  Name                     |        	Email Address           |
| ------------              | --------------------------------|
| Vikram Bisht              |  Vikram.Bisht@opstree.com       |  

# Resources and References

|  Source                                                             |        Description                                                           |
| ------------                                                        | --------------------------------                                             |
| https://nvie.com/posts/a-successful-git-branching-model/            |  Refer to this tutorial for more information on the Feature Branch Workflow  |  
	
