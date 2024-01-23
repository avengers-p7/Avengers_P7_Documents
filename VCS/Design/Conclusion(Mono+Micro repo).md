# Mono Repo vs Micro Repo

| Author | Created on  | Version    | Last Updated by | Last Updated on |
| -------- | ------- | -------------- | --------------| ---------------- |
| **[Harshit Singh](https://github.com/Panu-S-Harshit-Ninja-07)**  | 15-01-2024  | 1.0   | Harshit Singh | 22-01-2024 |
| **Samir Kesare**  | 15-01-2024  | 1.0   |  |  |
***

## Table  of Contents

1. [Introduction](#introduction)
2. [Comparison](#Comparison)
3. [Conclusion](#Conclusion)
4. [Contact Information](#contact-information)
5. [Refrences](#references)
***

## Introduction 
In this document, we explore the choice between Mono Repo and Micro Repo for version control by defining and comparing them. We have also stated the points through which we should choose the right approach according to our requirement/ use case. 
### Mono Repo
  A monorepo stores all your application and microservice code in a single source code repository like Git. A mono repo with unified and automated build and deploy pipelines can mitigate many development issues. [reference documentation](https://github.com/avengers-p7/Documentation/blob/main/VCS/Design/MonoRepo.md)
  
  Using a mono repo, it’s easier to standardize code and tooling across the teams. The single view of the whole code available in a mono repo increases the discoverability of status and changes. This results in smoother release management and easier refactoring.
### Micro Repo
Microrepos, or "microservices repositories," involve maintaining separate repositories for each microservice or component of a project. In the case of a backend and frontend project, there would be a dedicated repository for the backend and another for the frontend.[reference documentation](https://github.com/avengers-p7/Documentation/wiki/Micro%E2%80%90repos)

### Folder Structure
![image](https://github.com/avengers-p7/Documentation/assets/156056444/ac2a02a1-e4bf-48a3-91d3-76d02e05c299)
***
## Comparison

### Technical aspect
|           Concept           | Mono Repo | Micro Repo |
| --------------------------  | :-------: | :--------: |
| Clean Code                  |    ✅     |    ❌      | 
| Refator Code                |    ✅     |    ❌      |
| Security                    |    ❌     |    ✅      |
| Scalibilty                  |    ❌     |    ✅      |
| Tests(Unit, Int, e2e)       |    ✅     |     ⚠️      |
| Module Versioning           |     ⚠️     |    ✅      |
| Clear Owernship             |    ✅     |    ✅      |
| Intergration(CI/CD)         |     ⚠️     |    ✅      |
| Dependency Administration   |    ✅     |     ⚠️      |
| Migrating to another type of repository managenment    |    ❌     |    ✅      |4

✅ (Benefit) = Represents something obtainable without much effort.

⚠️ (Attention) = Represents something not easily obtainable.

❌ (Challenge) = Represents something difficult to obtain.  
### Cultural aspect
|                     Concept                      | Mono Repo | Micro Repo |
| ------------------------------------------------ | :-------: | :--------: |
| Onboarding                                       |    ✅     |    ❌      | 
| Independance for maintenance                     |    ✅     |    ❌      |
| Good engineering practice                        |    ❌     |    ✅      |
| Prioritization of needs(features, bugs, etc)     |    ❌     |    ✅      |
| Isolation and good  communication between teams  |    ✅     |     ⚠️      |

***

## Choosing the Right Approach:
When deciding between a monorepo and microrepo strategy for a project with separate backend and frontend components, several factors should be considered.

|         Factors        | Description |
| ---------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Project Size and Complexity** |Monorepos are generally more suitable for large projects with complex interdependencies. If the backend and frontend are tightly coupled and share many common dependencies, a monorepo can simplify development and maintenance.Microrepos are often preferred for smaller projects or those with loosely coupled components, as they allow for more granular control and flexibility.|
| **Team Structure and Autonomy** | If backend and frontend teams work independently and prefer autonomy in their codebases, microrepos can provide more flexibility and ownership.Monorepos are beneficial for fostering collaboration and sharing code among teams working on different components.|
| **Deployment and Scalability Needs** | If the project follows a microservices' architecture, where components need independent deployment and scalability, microrepos align more closely with this approach.Monorepos may be preferred when a unified release and deployment process across all components is required.|
***
## Conclusion

Choosing a microrepo strategy for separate components offers flexibility and autonomy, aligning well with our requirements. This approach allows independent development and deployment, fostering scalability and streamlined processes. 
Microrepos offer specific advantages in certain scenarios. Let's take a look at some of the benefits of this approach

|         Feature         | Description |
| ---------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Security** | It is one of the main benefits of using a multi-repo. This is because, unlike mono-repos, in this strategy it’s possible to grant specific and necessary permissions according to the specific scope of a project.|
| **Scalability** | With a multi-repo, scalability should be much more feasible and manageable from the beginning. This is because projects are abstracted earlier.|
| **Versioning** | It is also almost instantaneous when you use a multi-repo — when you have separate environments in multiple different repositories, little coordination is required.|
| **Assign Ownership** | With a multi-repo it is much easier to assign ownership since, for example, each repository can satisfy a specific business domain. |
| **Independent Approach** | The independence and performance provided by multi-repos makes it much easier for organizations to distribute their resources and evaluate results.|
| **Migration** |  Migrating multi-repos to alternative ways of managing a codebase is much easier to do, compared to mono-repos |
| **CI/CD with Micro-repo** | It’s much easier to do CI/CD with a multi-repo. This is because there is a basic separation, which makes it easier to facilitate resources between teams. |
***

## Contact Information

|     Name         | Email  |
| -----------------| ------------------------------------ |
| Harshit Singh    | harshit.singh.snaatak@mygurukulam.co |
| Samir Kesare     | samir.kesare.snaatak@mygurukulam.co |        
***

## References

|     Description                  | References  
| ---------------------------------| ------------------------------------------------------------------- |
|     Documentation Template       | https://github.com/OT-MICROSERVICES/documentation-template/wiki/Application-Template |
|     Mono Repo  vs  Micro Repo    | https://www.thoughtworks.com/en-de/insights/blog/agile-engineering-practices/monorepo-vs-multirepo |

