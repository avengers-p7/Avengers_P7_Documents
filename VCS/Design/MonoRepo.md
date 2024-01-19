# Mono Repo

| Author | Created on  | Version    | Last Updated by | Last Updated on |
| -------- | ------- | -------------- | --------------| ---------------- |
| **[Harshit Singh](https://github.com/Panu-S-Harshit-Ninja-07)**  | 15-01-2024  | 1.0   | Harshit Singh | 19-01-2024 |

## Table  of Contents

1. [Introduction](https://github.com/avengers-p7/Documentation/blob/main/VCS/Design/MonoRepo.md#introduction)
2. [Features](#features)
3. [Challenges/Disadvantages](#challengesdisadvantages)
4. [Best Practices](#Best-Practices)
5. [Conclusion](#Conclusion)
6. [Contact Information](#contact-information)
7. [Refrences](#references) 

## Introduction 

  A repo (short for repository) is a storage for all the changes and files from a project, enabling developers to “version control” the project’s assets throughout its development stage.

  A monorepo stores all your application and microservice code in a single source code repository like Git. A mono repo with unified and automated build and deploy pipelines can mitigate many development issues. 
  
  Using a mono repo, it’s easier to standardize code and tooling across the teams. The single view of the whole code available in a mono repo increases the discoverability of status and changes. This results in smoother release management and easier refactoring.

### Monorepo-style development is a software development approach where:

- You develop multiple projects in the same repository.
- The projects can depend on each other, so they can share code.
- When you make a change, you do not rebuild or retest every project in the monorepo. Instead, you only rebuild and retest the projects that can be affected by your change.

  ![Mono Repo](https://github.com/avengers-p7/Documentation/assets/156056444/93fab22f-263e-4390-8e12-2e1e1885d918)

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

## Challenges/Disadvantages 

Using a single repository for all our code has several drawbacks.

- **Slower Development Cycles**

  When the code for a library contains breaking changes, which make the tests for dependent libraries fail, the code must also be fixed before merging the changes.
  If these libraries depend on other teams, who are busy working on some other task and are not able (or willing) to adapt their code to avoid the breaking changes and have the tests pass, the    development of the new feature may stall.

  What’s more, the project may well start advancing only at the speed of the slowest team in the company. This outcome could frustrate the members of the fastest teams, creating conditions for    them to want to leave the company.
  
  In addition, a library will need to run the tests for all other libraries too. The more tests to run, the more time it takes to run them, slowing down how fast we can iterate on our code.

- **Requires Download of Entire Codebase**

  When the monorepo contains all the code for a company, it can be huge, containing gigabytes of data. To contribute to any library hosted within, anybody would require a download of the whole   repository.

  Dealing with a vast codebase implies a poor use of space on our hard drives and slower interactions with it. For instance, everyday actions such as executing git status or searching in the      codebase with a regex may take many seconds or even minutes longer than they would with multiple repos.

- **Unmodified Libraries May Be Newly Versioned**

  When we tag the monorepo, all code within is assigned the new tag. If this action triggers a new release, then all libraries hosted in the repository will be newly released with the version     number from the tag, even though many of those libraries may not have had any change.

- **Forking Is More Difficult**

  Open-source projects must make it as easy as possible for contributors to become involved. With multiple repositories, contributors can head directly to the specific repository for the project they want to contribute to. With a monorepo hosting various projects, though, contributors must first navigate their way into the right project and will need to understand how their contribution may affect all other projects.

## Best Practices 

|         Practice       | Description |
| ---------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Use selective builds** | "Selective builds" refer to the process of building only the parts of the codebase that have been changed or are affected by a change, rather than building the entire monorepo. |
| **Manage Dependencies** |  Ensuring the dependencies are managed properly will ensure that builds perform optimally, function correctly, and reduce friction for developers working on the project. |
| **Managing access and merge approvals** | Managing access control with a monorepo is essential, due to the unique challenges and requirements presented by housing multiple projects or components in a single repository.
| **Use Git features to enhance repo performance** | As the size of your repository grows, the amount of bandwidth and system resources required to effectively utilize the project will increase, and the time it takes to clone can become substantial, especially when employing modern CI/CD strategies such as parallelism. In this case, we can use features like Shallow Clone and Sparse Checkout. 
| **Use Trunk-based development** | ‘Trunk-based development’ (TBD) is a strategy where all developers work in a single branch, often called the 'trunk' or 'main' branch, and use short-lived feature branches (or no branches at all). It reduces divergence, minimizes merge conflicts, and aligns with CI/CD practices.
## Conclusion 

## Contact Information

|     Name         | Email  |
| -----------------| ------------------------------------ |
| Harshit Singh    | harshit.singh.snaatak@mygurukulam.co |                                                                                      

## References

|     Description                  | References  
| ---------------------------------| ------------------------------------------------------------------- |
|     Documentation Template       | https://github.com/OT-MICROSERVICES/documentation-template/wiki/Application-Template |
|     Mono Repo                    | https://www.perforce.com/blog/vcs/what-monorepo#what-01 |
