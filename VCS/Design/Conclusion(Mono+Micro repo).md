i999909# Mono Repo

| Author | Created on  | Version    | Last Updated by | Last Updated on |
| -------- | ------- | -------------- | --------------| ---------------- |
| **[Harshit Singh](https://github.com/Panu-S-Harshit-Ninja-07)**  | 15-01-2024  | 1.0   | Harshit Singh | 19-01-2024 |

## Table  of Contents
Detailed documentation which includes Purpose, Introduction of each, Comparison table of Mono and Micro, Conclusion and Contact Information, References 

1. [Purpose](#Purpose)
2. [Introduction](#introduction)
3. [Comparison](#Comparison)
4. [Conclusion](#Conclusion)
5. [Contact Information](#contact-information)
6. [Refrences](#references)

## Purpose
## Introduction 
### Mono Repo
  A monorepo stores all your application and microservice code in a single source code repository like Git. A mono repo with unified and automated build and deploy pipelines can mitigate many development issues. (https://github.com/avengers-p7/Documentation/blob/main/VCS/Design/MonoRepo.md)
  
  Using a mono repo, it’s easier to standardize code and tooling across the teams. The single view of the whole code available in a mono repo increases the discoverability of status and changes. This results in smoother release management and easier refactoring.
### Micro Repo
Microrepos, or "microservices repositories," involve maintaining separate repositories for each microservice or component of a project. In the case of a backend and frontend project, there would be a dedicated repository for the backend and another for the frontend.(https://github.com/avengers-p7/Documentation/wiki/Micro%E2%80%90repos)

### Folder Structure
![image](https://github.com/avengers-p7/Documentation/assets/156056444/d91b3961-665b-48b3-8ad6-76bf9d193d2a)

## Comparison

![image](https://github.com/avengers-p7/Documentation/assets/156056570/ba8a766f-32b8-4666-bab8-be46119bc41d)
![image](https://github.com/avengers-p7/Documentation/assets/156056570/8e01306f-d544-4cc1-839d-a3f2164705f0)
✅ (Benefit) = Represents something obtainable without much effort.

⚠️ (Attention) = Represents something not easily obtainable.

❌ (Challenge) = Represents something difficult to obtain.  

## Choosing the Right Approach:
When deciding between a monorepo and microrepo strategy for a project with separate backend and frontend components, several factors should be considered.

1. Project Size and Complexity:
Monorepos are generally more suitable for large projects with complex interdependencies. If the backend and frontend are tightly coupled and share many common dependencies, a monorepo can simplify development and maintenance. Microrepos are often preferred for smaller projects or those with loosely coupled components, as they allow for more granular control and flexibility.

2. Team Structure and Autonomy:
If backend and frontend teams work independently and prefer autonomy in their codebases, microrepos can provide more flexibility and ownership. Monorepos are beneficial for fostering collaboration and sharing code among teams working on different components.

3. Deployment and Scalability Needs:
If the project follows a microservices' architecture, where components need independent deployment and scalability, microrepos align more closely with this approach. Monorepos may be preferred when a unified release and deployment process across all components is required.

## Conclusion +

In conclusion, a monorepo offers advantages like improved visibility, code sharing, and standardized practices for managing microservices. However, challenges include slower development cycles and potential complexities. To optimize monorepo usage, consider best practices such as selective builds, effective dependency management, and trunk-based development. The decision to adopt a monorepo should be based on a careful evaluation of specific needs and a balanced consideration of its benefits and challenges. Successful implementation requires a thoughtful approach and collaboration within the development team.



## Contact Information

|     Name         | Email  |
| -----------------| ------------------------------------ |
| Harshit Singh    | harshit.singh.snaatak@mygurukulam.co |
| Samir Kesare     | samir.kesare.snaatak@mygurukulam.co |        

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
|Comparison | https://www.thoughtworks.com/en-de/insights/blog/agile-engineering-practices/monorepo-vs-multirepo |
