# Environment branch workflow

|   Author     |  Created on   |  Version   | Last updated by | Last edited on |
| ------------ | --------------| -----------|---------------- | -------------- |
| Vikram BISHT | 16 Jan 2024   |     v1     | Vikram Bisht    | Vikram Bisht   |

---
# Introduction
### Environment Branch Workflow in VCS
In version control systems, branching is a powerful feature that allows developers to work on new features or bug fixes without affecting the main codebase. This document describes an environment branch workflow in Git, which is a popular version control system. This workflow is based on creating separate branches for different environments, such as development, staging, and production.

# Why we need Environment Branch
The environment branch workflow is useful for teams that work on large projects with multiple environments. It helps to ensure that changes are properly tested and reviewed before being deployed to production. By using separate branches for each environment, teams can avoid conflicts and maintain a stable codebase.

# Types of Environment Branches


|   Development Branch     |  This is where all new features and bug fixes are developed and tested                                             |  
| ------------             | ---------------------------------------------------------------------------------------------------------          |
| Testing Branch           |  This environment is dedicated to comprehensive testing to identify and fix bugs before moving to the next stage   |
| Staging Branch           | This environment closely mirrors the production environment and serves as a final testing ground before deployment |
| Production Branch        | The production branch contains the stable and tested code that is ready for deployment to the live environment     |

# Env Branch Flow
The environment branch workflow involves the following steps:
1. Create a new feature branch from the development branch.
2. Make changes and commit them to the feature branch.
2. Open a pull request to merge the feature branch into the development branch.
3. Once the changes have been reviewed and tested, merge the feature branch into the staging branch.
4. Test the changes in the staging environment.
5. If the changes are successful, merge the staging branch into the production branch.
6. Deploy the changes to the live site.

# Advantages 
The environment branch workflow has several advantages, including:
1. Isolation: By using separate branches for each environment, teams can avoid conflicts and maintain a stable codebase.
2. Testing: Changes can be thoroughly tested in the staging environment before being deployed to production.
3. Review: Pull requests allow for code reviews, which can help to catch bugs and improve code quality.
4. Auditing: Environment branches provide a clear record of changes, which can be useful for auditing and debugging.

# Disadvantages
The environment branch workflow also has some disadvantages, including:
1. Complexity: The workflow can be complex, especially for large teams working on multiple features simultaneously.
2. Overhead: Creating and merging branches can add overhead to the development process.
3. Delay: There can be a delay between making changes and deploying them to production.

# Conclusion: 
The environment branch workflow is a useful tool for teams that work on large projects with multiple environments. By using separate branches for each environment, teams can maintain a stable codebase, thoroughly test changes, and ensure that code is reviewed before being deployed to production. However, the workflow can be complex and add overhead to the development process.
