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

| **Focus on Main Branch**     | **Description**                                      | 
|--------------------------|--------------------------------------------| 
| GitLab Flow Approach     | Directly works with the "main" branch for simplicity. Keeps the version control streamlined.            |


| **Feature Branches**         | **Description**                                           |
|--------------------------|--------------------------------------------| 
| Purpose                  | Created for new features or fixes. Enables isolated work without affecting the main code. Branches off directly from the "main" branch.    |


| **Issue Tracking**           | **Description**                                            |
|--------------------------|--------------------------------------------| 
| Integration              | Link each feature branch to an issue in the issue tracker. Provides context for code changes and enhances team communication.|


| **Review and Merge**         | **Description**                                          |
|--------------------------|--------------------------------------------| 
| Process                  | Create a merge request when a feature branch is ready. Triggers a code review process for quality assurance. Catches potential problems before merging into the main branch.|


| **Pre-production Environments** | **Description**                                        |
|--------------------------|--------------------------------------------| 
| Implementation           | Supports separate branches for staging and production environments. Allows thorough testing before releasing changes to users.|


# Best practices in GitLab flow
- Use feature branches if you are working on something new, so that contributors can easily start the code review process before merging.
- If developers are working on a feature branch and adding new commits, they should run tests right away. If the tests take more than 5 minutes, run them in parallel.
- Perform code reviews in the draft merge request because developers can identify issues as soon as possible. Also, tag that draft request as WIP or work in progress.
- Developers can have a separate branch for production, and then they can run a script that triggers the deployment process.
- Developers should check out the main branch and create a new feature branch. After making the necessary changes, they can merge it into the main branch. Before merging the request, they should conduct a 360 review in the draft request.

# Advantage of GitLab flow

| Key Principle             | Description                                                                                                                                                                                                                          |
|---------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Simplicity and Transparency| Easy to learn and implement, especially for Git beginners. The workflow is well-defined and relies on a limited number of key branches, fostering transparency through issue-linking and clear change visibility.               |
| Efficiency                | Promotes small, focused feature branches that merge frequently, minimizing merge conflicts and streamlining development iteration.                                                                                                  |
| Integration with GitLab    | Built-in integration with GitLab features like merge requests, CI/CD pipelines, and issue tracking, optimizing collaboration and automation.                                                                                           |
| Flexibility               | Adaptable to specific team needs and project complexity. Additional branches or workflows can be incorporated to fit your requirements.                                                                                               |
| Emphasis on Testing       | Merge requests and CI/CD pipelines encourage continuous testing and code quality checks throughout the development cycle.                                                                                                           |
# Disadvantage of GitLab flow

| Key Concern                | Description                                                                                                                                                                                                                                |
|----------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Potential Merge Complexity | Can become cumbersome for larger teams with frequent merges, increasing the risk of merge conflicts and requiring more attention to conflict resolution.                                                                                   |
| Feature Branch Longevity   | Feature branches often live longer than other workflows, potentially leading to outdated code or divergence from main if not actively managed.                                                                                           |
| Release Management (Optional)| Requires additional overhead if using separate production branches for controlled releases, adding another layer of complexity.                                                                                                              |
| Learning Curve             | While simpler than GitFlow, GitLab Flow still has a learning curve, especially for teams new to Git branching strategies.                                                                                                                  |
| Dependency on CI/CD        | Optimal execution relies heavily on robust CI/CD pipelines for automated testing and deployment, which might not be available for all teams.                                                                                               |

# Conclusion 

GitLab Flow helps software teams work together smoothly by organizing code changes into mini-projects ("feature branches"). This keeps things clear, avoids messy merges, and lets everyone contribute without stepping on each other's toes.
Good fit for: Teams who prioritize clean workflows, clear communication, and high-quality code. Consider your team's size, experience, and project needs before adopting it.

# Contact Information

| Name            | Email Address                        |
|-----------------|--------------------------------------|
| Khushi Malhotra | khushi.malhotra.snaatak@mygurukulam.co |

# Resources and References

| Resource                                 | Content                                               |
|------------------------------------------|-------------------------------------------------------|
| [GitLab Flow Documentation](https://about.gitlab.com/topics/version-control/what-is-gitlab-flow/) | GitLab official document to understand all concepts   |
