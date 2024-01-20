# Mono Repo

| Author | Created on  | Version    | Last Updated by | Last Updated on |
| -------- | ------- | -------------- | --------------| ---------------- |
| **[Harshit Singh](https://github.com/Panu-S-Harshit-Ninja-07)**  | 15-01-2024  | 1.0   | Harshit Singh | 19-01-2024 |

*** 

## Table  of Contents

1. [Introduction](#introduction)
2. [Features](#features)
3. [Advantages of Mono Repo](#Advantages-of-Mono-Repo)
4. [Challenges/Disadvantages](#challengesdisadvantages)
5. [Best Practices](#Best-Practices)
6. [Who Uses](#who-uses)
7. [Conclusion](#Conclusion)
8. [Contact Information](#contact-information)
9. [Refrences](#references) 
***
## Introduction 

  A repo (short for repository) is a storage for all the changes and files from a project, enabling developers to “version control” the project’s assets throughout its development stage.

  A monorepo stores all your application and microservice code in a single source code repository like Git. A mono repo with unified and automated build and deploy pipelines can mitigate many development issues. 
  
  Using a mono repo, it’s easier to standardize code and tooling across the teams. The single view of the whole code available in a mono repo increases the discoverability of status and changes. This results in smoother release management and easier refactoring.

### Monorepo-style development is a software development approach where:

- You develop multiple projects in the same repository.
- The projects can depend on each other, so they can share code.
- When you make a change, you do not rebuild or retest every project in the monorepo. Instead, you only rebuild and retest the projects that can be affected by your change.

***
## Features 

The monorepo approach has several advantages:
|         Feature         | Description |
| ---------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Easy visibility** | If you are working on a microservice that calls other microservices, you can look at the code, understand how it works, and find out if bugs are from your code or another team’s microservice.|
| **Code sharing** | Teams duplicating code for microservices create additional engineering overhead. If common models, shared libraries, and helper code are all stored in a single repository, teams can share them among many microservices. |
| **Improved collaboration** | A monorepo removes barriers and silos between teams, making it easier to design and maintain sets of microservices that work well together.
| **Standardization** | With monorepos, it is easier to standardize code and tooling across the teams. You can create policies that keep your main branch uncluttered, limit access to specific branches, enforce naming   guidelines, include code reviewers, and enforce best practices. Branch policies keep in-progress work isolated from completed work.
| **Discoverability** | A monorepo offers a single view of the whole code. You can review the status of the whole repository, screen all branches, and keep track of modifications much more easily in monorepos than in polyrepos.
| **Release management** | A monorepo retains all the information about how to deploy the whole system. An automated build and deploy pipeline doesn’t hide deployment knowledge within each team the way it does in a polyrepo.
| **Easier refactoring** | Direct access to all microservices makes it easier to refactor the code in a monorepo. Also, you can change the code structure. Moving the source code between folders and subfolders is much easier than moving the source code between multiple repositories.
***

![Mono Repo](https://github.com/avengers-p7/Documentation/assets/156056444/93fab22f-263e-4390-8e12-2e1e1885d918)

# Advantages of Mono Repo

| Key Principle             | Description |
|---------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Code Sharing and Reuse** | In a monorepo, code can be shared across multiple projects, making it easier to reuse code without the need for duplicate code or complex dependency management. |
| **Simplified Dependency Management** | With a monorepo, all projects use the same version of dependencies, eliminating “dependency hell.” |
| **Ease of Collaboration**    | Monorepos make it easier for developers to work together, as all the code is available in a single location. |
| **Atomic Commits and Cross-Project Changes** | Changes across multiple projects can be committed atomically, maintaining consistency and making rollback easier if necessary.
***
## Challenges/Disadvantages 

When using a mono repo for all our code we might face a few challenges, some of them are:-
|         Problem       | Description |
| ---------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Slower Development Cycles** | Breaking changes in a library can cause dependent libraries' tests to fail, requiring fixes before merging changes. Dependencies on other teams may lead to development stalls. Project progression may be hindered by the slowest team's pace, causing frustration among faster teams.
| **Requires Download of Entire Codebase** | A monorepo containing all company code can be large, requiring contributors to download the entire repository. Inefficient disk space usage and slower interactions with the vast codebase, affect everyday actions like git status or code searches.
| **Unmodified Libraries May Be Newly Versioned** | Tagging the monorepo results in all code being assigned the new tag, potentially triggering new releases for unchanged libraries. Libraries may be versioned unnecessarily, leading to confusion and challenges in managing version consistency.
| **Forking Is More Difficult** | In open-source projects, contributors find it less straightforward to fork and contribute in a monorepo compared to multiple repositories. Navigating the correct project within the monorepo and understanding the broader impact on other projects can be barriers for contributors.
***
## Best Practices 
To optimize our mono repo we can use the following practices:-

|         Practice       | Description |
| ---------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Use selective builds** | "Selective builds" refer to the process of building only the parts of the codebase that have been changed or are affected by a change, rather than building the entire monorepo. |
| **Manage Dependencies** |  Ensuring the dependencies are managed properly will ensure that builds perform optimally, function correctly, and reduce friction for developers working on the project. |
| **Managing access and merge approvals** | Managing access control with a monorepo is essential, due to the unique challenges and requirements presented by housing multiple projects or components in a single repository.
| **Use Git features to enhance repo performance** | As the size of your repository grows, the amount of bandwidth and system resources required to effectively utilize the project will increase, and the time it takes to clone can become substantial, especially when employing modern CI/CD strategies such as parallelism. In this case, we can use features like Shallow Clone and Sparse Checkout. 
| **Use Trunk-based development** | ‘Trunk-based development’ (TBD) is a strategy where all developers work in a single branch, often called the 'trunk' or 'main' branch, and use short-lived feature branches (or no branches at all). It reduces divergence, minimizes merge conflicts, and aligns with CI/CD practices.
***
## Who Uses

Several big tech companies favour the monorepo approach, while others have decided to use the multi-repo method. `Google, Facebook, Twitter, and Uber` have all publicly vouched for the monorepo approach. 

`Google` chose the monolithic source management strategy in 1999 when the existing Google codebase was migrated from CVS to Perforce. Early Google engineers maintained that a single repository was strictly better than splitting up the codebase, though at the time they did not anticipate the future scale of the codebase and all the supporting tooling that would be built to make the scaling feasible.

Over the years, as the investment required to continue scaling the centralized repository grew, Google leadership occasionally considered whether it would make sense to move from the monolithic model. Despite the effort required, Google repeatedly chose to stick with the central repository due to its advantages.

The monolithic model of source code management is not for everyone. `It is best suited to organizations like Google, with an open and collaborative culture`. It would not work well for organizations where large parts of the codebase are private or hidden between groups.
***
## Conclusion 

In conclusion, a monorepo offers advantages like improved visibility, code sharing, and standardized practices for managing microservices. However, challenges include slower development cycles and potential complexities. To optimize monorepo usage, consider best practices such as selective builds, effective dependency management, and trunk-based development. The decision to adopt a monorepo should be based on a careful evaluation of specific needs and a balanced consideration of its benefits and challenges. Successful implementation requires a thoughtful approach and collaboration within the development team.
***


## Contact Information

|     Name         | Email  |
| -----------------| ------------------------------------ |
| Harshit Singh    | harshit.singh.snaatak@mygurukulam.co |                                                                                      
***
## References

|     Description                  | References  
| ---------------------------------| ------------------------------------------------------------------- |
|     Documentation Template       | https://github.com/OT-MICROSERVICES/documentation-template/wiki/Application-Template |
|     Mono Repo                    | https://www.perforce.com/blog/vcs/what-monorepo#what-01 |
|                                  | https://www.toptal.com/front-end/guide-to-monorepos#:~:text=Instead%20of%20managing%20multiple%20repositories,website%20and%20its%20iOS%20app.
|                                  | https://circleci.com/blog/monorepo-dev-practices/ |
| Mono Repo Best Practices | https://buildkite.com/blog/monorepo-ci-best-practices |
| Use Case | https://kinsta.com/blog/monorepo-vs-multi-repo/
|          | https://cacm.acm.org/magazines/2016/7/204032-why-google-stores-billions-of-lines-of-code-in-a-single-repository/fulltext
***
