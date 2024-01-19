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

- **Easy visibility**

  If you are working on a microservice that calls other microservices, you can look at the code, understand how it works, and find out if bugs are from your code or another team’s           
  microservice.
  
- **Code sharing**

  Teams duplicating code for microservices create additional engineering overhead. If common models, shared libraries, and helper code are all stored in a single repository, teams can share them   among many microservices.

- **Improved collaboration**

  A monorepo removes barriers and silos between teams, making it easier to design and maintain sets of microservices that work well together.

- **Standardization**

  With monorepos, it is easier to standardize code and tooling across the teams. You can create policies that keep your main branch uncluttered, limit access to specific branches, enforce naming   guidelines, include code reviewers, and enforce best practices. Branch policies keep in-progress work isolated from completed work.

- **Discoverability**

  A monorepo offers a single view of the whole code. You can review status for the whole repository, screen all branches, and keep track of modifications much more easily in monorepos than in      polyrepos.

- **Release management**

  A monorepo retains all the information about how to deploy the whole system. An automated build and deploy pipeline doesn’t hide deployment knowledge within each team the way it does in a   
  polyrepo.
- **Easier refactoring**

  Direct access to all microservices makes it easier to refactor the code in a monorepo. Also, you can change the code structure. Moving the source code between folders and subfolders is much      easier than moving the source code between multiple repositories.

## Challenges/Disadvantages 
## Best Practices 
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
