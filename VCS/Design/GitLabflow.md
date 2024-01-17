| Author           | Created on  | Last Updated | Document Version |
|------------------|-------------|--------------|-------------------|
| Khushi Malhotra | 16-01-2024  | 17-01-2024   |        v1          |

# Introduction
In today's fast-paced software development world, teams need a way to work together smoothly and efficiently, especially when it comes to branching and merging code. GitLab Flow is a simple but powerful branching strategy that helps teams stay organized and deliver features quickly.

# Why
| Key Aspect      | Description                                                                                                                                                               |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Simplicity      | GitLab flow is relatively simple to learn and implement, even for teams new to Git. It uses only a few core branches (master, develop, feature branches, and release branches) and well-defined workflows for branching, merging, and deployment. |
| Transparency    | GitLab flow emphasizes transparency by linking code changes to issues in the issue tracker. This helps team members understand the context of changes and track the progress of work.                                 |
| Efficiency      | GitLab flow promotes efficient development by encouraging small, focused feature branches that can be merged frequently. This reduces the risk of merge conflicts and makes it easier to identify and fix bugs.                |
| Integration     | GitLab flow is designed to work seamlessly with GitLab's features, such as merge requests, continuous integration/continuous delivery (CI/CD), and issue tracking. This integration can help to automate tasks and streamline the development process. |
| Flexibility     | While GitLab flow provides a basic framework, it is also flexible enough to be adapted to meet the specific needs of your team. You can add additional branches or workflows as needed to accommodate your project's complexity.         |

# GitLab flow Working

### Focus on the main branch: 
Instead of having a separate "develop" branch, GitLab Flow works directly with the "main" branch. This keeps things simple and streamlined.

### Feature branches for new work: 
When you're working on a new feature or fix, create a dedicated branch off of the main branch. This allows you to work in isolation without affecting the main code.

### Issue tracking for clarity: 
Link each feature branch to an issue in your issue tracker. This provides context for the code changes and helps with communication within the team.


### Review and merge: 
Once a feature branch is ready, create a merge request to bring it back into the main branch. This triggers a code review process to ensure quality and catch any potential problems.

### Pre-production environments: 
GitLab Flow supports having separate branches for staging and production environments. This allows you to test changes thoroughly before releasing them to users.
