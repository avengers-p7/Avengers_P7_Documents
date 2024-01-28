# Environment branch workflow

|   Author     |  Created on   |  Version   | Last updated by | Last edited on |
| ------------ | --------------| -----------|---------------- |--------------- |
| Vikram BISHT | 26 Jan 2024   |     v1     | Vikram Bisht    | 26 Jan 2024    |

---
# Table of Contents 
+ [Introduction](#introduction)
+ [What is Python CI Checks](#What-is-Python-CI-Checks)
+ [Why Python CI Checks](#Why Python-CI-Checks)
+ [Creating a feature branch](#Creating-a-feature-branch)
+ [Advantages](#Advantages)
+ [Disdvantages](#Disdvantages)
+ [Conclusion](#conclusion)
+ [Contact Information](#contact-information)
+ [References](#References)
***


# Introduction
Continuous Integration (CI) is a development practice that involves regularly merging code changes and automatically building and testing the application to catch integration issues early. In the context of Python development, CI checks typically involve running automated tests, linters, and code formatters to ensure code quality and consistency. One important aspect of CI checks is code compilation, which involves checking if the code can be successfully compiled into executable form.

# What is Python CI Checks?

Python CI checks involve setting up automated processes to compile, test, and verify Python code changes. These checks are typically performed whenever code is pushed to a version control repository, ensuring that the software remains stable and error-free throughout its development lifecycle.

# Why Python CI Checks?

Code compilation is an essential step in Python CI checks because it ensures that the code can be built and executed successfully. By catching errors and issues early in the development process, developers can save time and effort by fixing issues before they become more significant problems. Additionally, code compilation can help ensure that the code meets certain quality and reliability standards, making it easier to maintain and scale over time.

# Different Tools for Python CI Checks

|  Tool                   |        Description                                                                                                 |
| ------------             | ---------------------------------------------------------------------------------------------------------          |
| Jenkins                  |  An open-source automation server that supports continuous integration and continuous delivery pipelines.                                            |  
| Travis CI	               |  This environment is dedicated to comprehensive testing to identify and fix bugs before moving to the next stage   |
| CircleCI                 | Another cloud-based CI/CD platform that automates the build, test, and deployment processes.                       |
| GitHub Actions           | This environment closely mirrors the production environment and serves as a final testing ground before deployment |
| Production Branch        | The production branch contains the stable and tested code that is ready for deployment to the live environment     |

































# Creating a feature branch

* Create a new feature branch from the development branch.
* Make changes and commit them to the feature branch.
* Open a pull request to merge the feature branch into the development branch.
* Once the changes have been reviewed and tested, merge the feature branch into the staging branch.
* Test the changes in the staging environment.
* If the changes are successful, merge the staging branch into the production branch.
* Deploy the changes to the live site.

![image](https://github.com/avengers-p7/Documentation/assets/79625874/c8584f6b-f7cc-47c9-b006-0c83cd49cee9)


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
| Delay        | There may be a delay between making changes and deploying them to the production environment.                   |

# Conclusion 
The environment branch workflow is a useful tool for teams that work on large projects with multiple environments. By using separate branches for each environment, teams can maintain a stable codebase, thoroughly test changes, and ensure that code is reviewed before being deployed to production. However, the workflow can be complex and add overhead to the development process.


# Contact Information

|  Name                     |        	Email Address           |
| ------------              | --------------------------------|
| Vikram Bisht              |  Vikram.Bisht@opstree.com       |  

# References

|  Source                                                             |        Description                                                           |
| ------------                                                        | --------------------------------                                             |
| https://nvie.com/posts/a-successful-git-branching-model/            |  Refer to this tutorial for more information on the Feature Branch Workflow  |  
| https://github.com/avengers-p7/Documentation/blob/main/VCS/Design/FeatureBranch.md | Feature branch Doc                                            |	
