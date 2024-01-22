# Micro-repo
***
| Author | Created on  | Version    | Last Updated by | Last Updated on |
| -------- | ------- | -------------- | --------------| ---------------- |
| Samir Kesare  | 17-01-2024  | 1.0   | Samir Kesare | 22-01-2024 |

# Table  of Contents

1. [Introduction](#Introduction)
2. [Folder Structure](#Folder-Structure)
3. [Advantages of Micro-repo](#Advantages-of-Micro-repo)
4. [Challenges with  Micro-repo](#Challenges-with-Micro-repo)
5. [Choosing the Right Approach](#Choosing-the-Right-Approach)
6. [Famous Companies which use Micro Repositories ](#Famous-Companies-which-use-Micro-Repositories)
7. [Contact Information](#contact-information)
8. [Refrences](#references) 

# Introduction 

Microrepos, or "microservices repositories," involve maintaining separate repositories for each microservice or component of a project. In the case of a backend and frontend project, there would be a dedicated repository for the backend and another for the frontend.

***

# Advantages of Micro-repo

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

# Challenges with  Micro-repo
While microrepos offer several benefits, they also have some drawbacks. Let's take a look at some of the disadvantages of this approach.

|         Disadvantage         | Description |
| ---------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Increased Complexity** | Increased learning curve: Microrepos can be more complex to set up and maintain, requiring additional tooling and configuration.Increased overhead: Managing multiple repositories can be more time-consuming and resource-intensive, increasing overhead.|
| **Reduced Collaboration** | Increased coordination: With each component residing in a separate repository, coordination between teams becomes more challenging.Reduced code reuse: Microrepos can lead to code duplication, as teams may be less likely to share code between repositories.|

***

# Choosing the Right Approach:
When deciding between a monorepo and microrepo strategy for a project with separate backend and frontend components, several factors should be considered.

|         Factors        | Description |
| ---------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Project Size and Complexity** |Monorepos are generally more suitable for large projects with complex interdependencies. If the backend and frontend are tightly coupled and share many common dependencies, a monorepo can simplify development and maintenance.Microrepos are often preferred for smaller projects or those with loosely coupled components, as they allow for more granular control and flexibility.|
| **Team Structure and Autonomy** | If backend and frontend teams work independently and prefer autonomy in their codebases, microrepos can provide more flexibility and ownership.Monorepos are beneficial for fostering collaboration and sharing code among teams working on different components.|
| **Deployment and Scalability Needs** | If the project follows a microservices' architecture, where components need independent deployment and scalability, microrepos align more closely with this approach.Monorepos may be preferred when a unified release and deployment process across all components is required.|

# Famous Companies which use Micro Repositories.

Micro Repository is used by companies like Slack, Github, Gitlab, SoundCloud etc.

![image](https://github.com/avengers-p7/Documentation/assets/156056570/99fd60cd-a62d-4a5a-886f-3433300ad928)

***
# Contact Information

|     Name         | Email  |
| -----------------| ------------------------------------ |
| Samir Kesare     | samir.kesare.snaatak@mygurukulam.co  | 


***

# References

|     Description                  | References  
| ---------------------------------| ------------------------------------------------------------------- |
|     Documentation Template       |  https://github.com/avengers-p7/Documentation/wiki/Micro%E2%80%90repos |
|     Mono Repo                    | https://dev.to/mrizwanashiq/monorepo-vs-microrepo-m58#advantages-of-microrepo |
|                                  | https://apoorv-tomar.medium.com/a-better-understanding-of-micro-rep-vs-mono-repo-a9f31f1e20fe#:~:text=Easy%20Code%20Sharing.,and%20efficient%20CI%2FCD%20pipelines. |


***
