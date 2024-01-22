# Commit Hooks Recommendations and Detailed Documentation

| Author                 | Created On | Last Updated | Document Version | Last Updated By |
| ---------------------- | ---------- | ------------ | ---------------- | --------------- |
| Vishal Kumar Kesarwani | 20-01-2024 | 22-01-2024   | v1               |  Vishal         |

***
## Table of Contents
+ [Introduction](#Introduction-of-Commithook)
+ [Comparison of Git Hooks](#Comparison-of-Git-Hooks)
+ [Recommended Commit Hook](#Recommended-Commit-Hook)
+ [Pre-Commit Hook](Pre-Commit-Hook)
+ [Why Use Pre-commit Hooks](#Why-Use-Pre-commit-Hooks)
+ [Setting Up Commit Hooks](#Setting-Up-Commit-Hooks)
+ [Troubleshooting](#Troubleshooting)
+ [Conclusion](#Conclusion)
+ [Contact Information](#Contact_Information)
+ [References](#References)  
***
## Introduction of Commithook

Commit hooks are scripts that run automatically before or after specific events in the Git lifecycle. They help maintain code quality, enforce coding standards, and prevent undesirable changes from being committed. for more detail Click [here](https://github.com/avengers-p7/Documentation/blob/main/VCS/Design/CommmitHooks%20Understanding.md)

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

## Recommended Commit Hook

I recommend using pre-commit hooks to streamline and manage various hooks effectively.

***

## Pre-Commit Hook

A pre-commit hook is a script or program that runs automatically before a Git commit is finalized. It is one of the various hooks provided by Git, and its purpose is to perform checks, validations, or tasks on the code before it becomes part of the version control system. The pre-commit hook allows developers to ensure code quality, consistency, and adherence to coding standards before changes are committed to the repository.

## Why Use Pre-commit Hooks

| **Feature** | **Description** |
|------------ | --------------- |
| **Code Quality Assurance**| Pre-commit hooks enable checks for code quality, formatting, and linting to be enforced before finalizing a commit, ensuring a high standard of code.|
| **Consistency** | They ensure a consistent coding style across the project by automatically enforcing coding standards. |
| **Early Issue Detection** | Identifying and addressing issues early in the development process, prior to code review, helps prevent the introduction of errors into the codebase. |
| **Time Savings** | Automated checks save developers time that might be spent manually fixing issues during code review or after commits, improving overall development efficiency. |

***

## Setting Up Commit Hooks  

To set up commit hooks, follow these general steps:

* Navigate to the root directory of your Git repository.
* Create a new directory named .git/hooks if it doesn't exist.

  <img width="550" length="200" alt="Hooks" src="https://github.com/avengers-p7/Documentation/assets/156056413/0f5baf96-1072-4f05-b06d-86054e7a9c01">
* Take a look at the `.git/hooks` directory to see some default scripts.
   
  <img width="350" length="75" alt="Hooks" src="https://github.com/avengers-p7/Documentation/assets/156056413/ef20acbd-1674-42bc-aa03-7c741d56dd1a">

* Write a simple Git hook
    
  Do you want to put in guardrails to prevent mistakes when making commits to your Git repository? A simple Git hook trick is to    prompt the user for confirmation before they commit something to a branch.
  Create a new file named `.git/hooks/pre-commit` and open it in a text editor. Add the following text, which queries Git for a     list of the files about to be committed for the current branch name and then enters a while loop until it gets a response from    the user:
  
  <img width="750" length="475" alt="Hooks" src="https://github.com/avengers-p7/Documentation/assets/156056413/2f9fe825-7d5d-476e-8c5d-89d7a71a6402">
  
  <img width="650" length="275" alt="Hooks" src="https://github.com/avengers-p7/Documentation/assets/156056413/841de1d0-0917-48e1-85cb-c0e5acc3e6a6">  
  
  Save and Exit.

* Mark the file executable.  
  `chmod +x .git/hooks/pre-commit`
  
* And then try it out by creating, adding, and committing a file.

   <img width="650" length="275" alt="Hooks" src="https://github.com/avengers-p7/Documentation/assets/156056413/9ed4d44e-b86d-4b80-a704-1783ddf38b01">  

***

## Troubleshooting
If hooks are not working as expected, check the following:  

![Screenshot from 2024-01-22 23-04-04](https://github.com/avengers-p7/Documentation/assets/156056413/8abafcfa-e2b6-457c-abb4-6c4129843718)

* Ensure scripts are executable (chmod +x script-name).  
  `chmod +x .git/hooks/pre-commit`
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
