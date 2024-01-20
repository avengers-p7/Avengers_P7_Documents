# Git Hooks 
| Author                 | Created On | Last Updated | Document Version | Last Updated By |
| ---------------------- | ---------- | ------------ | ---------------- | --------------- |
| Vishal Kumar Kesarwani | 16-01-2024 | 16-01-2024   | v1               |  Vishal         |

***
# Table of Contents

+ [Introduction](#Introduction)
+ [Purpose of hook](#Purpose_of_hook)
+ [Why in our project](#Why_in_our_project)
+ [Types of CommitHooks](#Types_of_CommitHooks)
+ [Conclusion](#Conclusion)
+ [Contact Information](#Contact_Information)
+ [References](#References)  
***
## Introduction

<img width="300" length="100" alt="Hooks" src="https://github.com/avengers-p7/Documentation/assets/156056413/93848227-e8d2-4166-83b4-39eea46e8871">

The documentation aims to empower developers with the knowledge and tools needed to maintain a secure and compliant codebase, ultimately contributing to the overall success and integrity of software projects.Commit hooks in Git are scripts that run automatically before or after specific Git events, such as committing changes. They allow developers to enforce and automate certain tasks, ensuring code quality, adherence to standards, and consistency throughout the development process.

***

## Purpose of hook

| **Purpose** | **Description** |
| ----------- | --------------- |
| **Code Quality Assurance** | Enforce coding standards, run linting, or perform static code analysis before allowing commits. |
| **Preventing Sensitive Data** | Check for and prevent the inclusion of sensitive information like passwords or API keys in commits. |
| **Automating Tests** | Run automated tests to ensure that new changes do not introduce issues. |
| **Enforcing Commit Message Guidelines** | Ensure that commit messages follow a predefined format or include relevant information. |

***

## Why using CommitHooks in our project

Using commit hooks in your project offers several advantages that contribute to the overall efficiency, quality, and consistency of the development process. Here are some key reasons for incorporating commit hooks into your project:

| **Feature** | **Description** |
| ----------- | --------------- |
| **Code Quality Assurance** | Commit hooks enable automated checks for coding standards, syntax errors, and other code quality metrics. This ensures that the committed code meets predefined standards, enhancing overall code quality.
| **Enforcement of Best Practices** | Commit hooks can enforce best practices such as proper commit message formatting, ensuring that contributors provide meaningful and standardized descriptions for each commit. |
| **Consistency Across Contributors** | Commit hooks establish a consistent development environment for all contributors by enforcing the same set of rules and checks. This consistency is especially valuable in collaborative projects with multiple developers. |
| **Streamlined Development Workflow** | Commit hooks automate repetitive tasks, allowing developers to focus on coding rather than manual checks. This streamlines the development workflow and reduces the likelihood of human error. |
| **Integration with CI/CD Pipelines** | Commit hooks complement continuous integration/continuous deployment (CI/CD) pipelines by performing preliminary checks before changes are integrated into the shared repository. This integration ensures a smoother overall development pipeline. |
| **Improved Collaboration** | By enforcing consistent commit message standards, commit hooks enhance collaboration among team members. Clear and well-documented commit messages improve code review processes and make it easier to understand the history of changes. |

***

## Types of CommitHooks

 There are two types of hooks present in Git
 
**1.Client-Side hooks**

**2.Server-Side hooks**

<img width="760" length="300" alt="Hooks" src="https://github.com/avengers-p7/Documentation/assets/156057205/f4dc2b35-3d60-492b-9f1d-0b42a3165116">


| **Client-Side Hook** | **Server-Side Hook** |
| -------------------- | -------------------- |
| **pre-commit** The pre-commit hook runs on the git commit event. This can be used for Static analysis, Linting, Spell-checks, and Code style checks. It takes zero arguments and exiting with a non-zero status aborts the commit operation. | **pre-receive** This hook reacts to git push and updates the references in its repository. It takes no arguments but for each ref to be updated it receives standard input in this format. |
| **prepare-commit-msg** The prepare-commit-msg hook is run before the commit message editor is fired up but after the default message is created. It is useful for editing the default message before the commit author sees it. | **update**  Before updating the ref on the remote repository, the update hook is invoked. Its exit status determines the success or failure of the ref update. |
| **commit-msg** This is useful to validate a commit. Developers can provide rules to validate the commit state or the commit message using this hook. Like it is helpful for spell-checks of commit messages. | **post-receive** It executes on the remote repository once all the refs have been updated. It takes no arguments but gets the same information as the pre-receive hook does on its standard input. |
| **post-commit** This hook runs after the commit operation successfully completed. This hook can be useful to provide notifications and it doesn’t take any parameters. |                                                                                                            |
| **post-checkout** The post-checkout hook runs after the git checkout operation. It can be used to set up a working directory, auto-generating documentation, etc. It works similar to the post-commit hook. | |
| **pre-rebase** The pre-rebase hook runs before the rebase operation. A script can be used to validate the rebase matches the workflow or not. If not then a non-zero exit code from the script will halt the rebase process. |  |

***

## Conclusion

Git Hooks are a powerful tool for 
automating tasks and enforcing policies in Git. By writing custom scripts that Git can execute at key points in the development process, developers can streamline their workflow and ensure code quality. With the tips and techniques outlined in this guide, you'll be able to use Git Hooks effectively in your own projects.

***

## Contact Information

| Name | Email address |
| ---- | ------------- |
| Vishal | vishal.kesarwani.snaatak@mygurukulam.co |

***

## References

| Source | Description |
| ------ | ----------- |
| https://git-scm.com/docs/githooks | Link for Documentation |
| https://www.geeksforgeeks.org/git-hooks/ | Types of CommitHooks |
| https://www.digitalocean.com/community/tutorials/how-to-use-git-hooks-to-automate-development-and-deployment-tasks | Looking at Hooks By Parameter |
