# Commit Hooks Recommendations and Detailed Documentation

| Author                 | Created On | Last Updated | Document Version | Last Updated By |
| ---------------------- | ---------- | ------------ | ---------------- | --------------- |
| Vishal Kumar Kesarwani | 20-01-2024 | 22-01-2024   | v1               |  Vishal         |

***
## Table of Contents
+ [Introduction](#Introduction)
+ [Why Choosing Pre-Commit Hooks ](#Why-Choosing-Pre-Commit-Hooks )
  + [Pre-Commit Hook](Pre-Commit-Hook)
+ [Setting Up Commit Hooks](#Setting-Up-Commit-Hooks)
+ [Troubleshooting](#Troubleshooting)
+ [Conclusion](#Conclusion)
+ [Contact Information](#Contact_Information)
+ [References](#References)  
***
## Introduction of Commithook

Commit hooks are scripts that run automatically before or after specific events in the Git lifecycle. They help maintain code quality, enforce coding standards, and prevent undesirable changes from being committed. for more detail Click [here](https://github.com/avengers-p7/Documentation/blob/main/VCS/Design/CommmitHooks%20Understanding.md)

***

## Why Choosing Pre-Commit Hooks 


### 1. Pre-Commit Hook
**Purpose:** Runs before a commit is created. It's ideal for checking syntax, running quick tests, and ensuring the commit won't break the build.

**Implementation:** Create a script (e.g., pre-commit) that performs necessary checks. Examples include running linting tools, checking for debug statements, or validating coding standards.
 

***
## Setting Up Commit Hooks  

To set up commit hooks, follow these general steps:

* Navigate to the root directory of your Git repository.
* Create a new directory named .git/hooks if it doesn't exist.
* Inside the .git/hooks directory, create or copy the hook scripts.
* Make sure the scripts are executable (chmod +x script-name).

***

## Troubleshooting
If hooks are not working as expected, check the following:

* Ensure scripts are executable (chmod +x script-name).
* Verify that the hooks are in the correct .git/hooks directory.

***

## Conclusion

Pre-commit Git hooks can be used to automate tasks and ensure that code meets a certain level of quality and consistency. By using pre-commit hooks, developers can catch potential issues before they are committed to the repository, saving time and improving productivity. 

***

## Contact Information

| Name | Email address |
| ---- | ------------- |
| Vishal | vishal.kesarwani.snaatak@mygurukulam.co |

***

## References

| Source | Description |
| ------ | ----------- |
| https://www.redhat.com/sysadmin/git-hooks | Git hook Example |
