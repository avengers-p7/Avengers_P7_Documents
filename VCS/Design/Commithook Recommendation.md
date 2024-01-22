# Commit Hooks Recommendations and Detailed Documentation

| Author                 | Created On | Last Updated | Document Version | Last Updated By |
| ---------------------- | ---------- | ------------ | ---------------- | --------------- |
| Vishal Kumar Kesarwani | 20-01-2024 | 22-01-2024   | v1               |  Vishal         |

***
## Table of Contents
+ [Introduction](#Introduction)
+ [Why Choosing Pre-Commit Hooks ](#Why-Choosing-Pre-Commit-Hooks )
+ [Pre-Commit Hook](Pre-Commit-Hook)
+ [Why Choosing Pre-Commit Hooks ](#Why-Choosing-Pre-Commit-Hooks )
+ [Setting Up Commit Hooks](#Setting-Up-Commit-Hooks)
+ [Troubleshooting](#Troubleshooting)
+ [Conclusion](#Conclusion)
+ [Contact Information](#Contact_Information)
+ [References](#References)  
***
## Introduction of Commithook

Commit hooks are scripts that run automatically before or after specific events in the Git lifecycle. They help maintain code quality, enforce coding standards, and prevent undesirable changes from being committed. for more detail Click [here](https://github.com/avengers-p7/Documentation/blob/main/VCS/Design/CommmitHooks%20Understanding.md)

***
## Recommended Commit Hook

I recommend using pre-commit hooks to streamline and manage various hooks effectively.

***

## Pre-Commit Hook

A pre-commit hook is a script or program that runs before a Git commit is finalized. It allows developers to enforce certain checks, validations, or formatting requirements on their code before it gets committed to the version control system.

## Why Use Pre-commit Hooks:

| **Feature** | **Description** |
|------------ | --------------- |
| **Code Quality Assurance**| Pre-commit hooks enable checks for code quality, formatting, and linting to be enforced before finalizing a commit, ensuring a high standard of code.|
| **Consistency** | They ensure a consistent coding style across the project by automatically enforcing coding standards. |
| **Early Issue Detection** | Identifying and addressing issues early in the development process, prior to code review, helps prevent the introduction of errors into the codebase. |
| **Time Savings** | Automated checks save developers time that might be spent manually fixing issues during code review or after commits, improving overall development efficiency. |

***

## Comparison of Git Hooks

| **Feature** | **Pre-commit Hook** | **Commit Hook** | **Post-commit Hook** |
| ----------- | ------------------- | ---------------- | ------------------- |
| **Timing**              | Runs before committing      | Runs during committing      | Runs after committing       |
| **Purpose**             | Preemptively checks         | Validates during commit     | Actions after commit        |
| **Scope of Checks**     | Code formatting, linting    | Commit message format       | Push-related operations     |
| **Interactivity**       | Allows code modification    | Can block commit            | No code modification        |
| **Execution Dependency**| Local environment           | Local environment           | Local or remote setup       |

***

## Setting Up Commit Hooks  

To set up commit hooks, follow these general steps:

* Navigate to the root directory of your Git repository.
* Create a new directory named .git/hooks if it doesn't exist.
  
 ![Screenshot from 2024-01-22 22-30-14](https://github.com/avengers-p7/Documentation/assets/156056413/0f5baf96-1072-4f05-b06d-86054e7a9c01)

* Make sure the scripts are executable (chmod +x script-name).

***

## Troubleshooting
If hooks are not working as expected, check the following:

* Ensure scripts are executable (chmod +x script-name).
* Verify that the hooks are in the correct .git/hooks directory.

***

## Conclusion
 
Pre-commit hooks offer a proactive approach to code quality by allowing developers to catch and address issues before they become part of the version control history. While other hooks serve specific purposes during or after the commit process, pre-commit hooks focus on preventive measures, making them a valuable tool for maintaining a clean and consistent codebase.

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
