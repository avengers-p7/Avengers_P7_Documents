# GitOps
| Author | Created On | Last Updated | Document Version | Last Updated By |
| ------ | ---------- | ------------ | ---------------- | --------------- |
| Vishal Kumar Kesarwani, Aakash Tripathi | 19-01-2024 | 22-01-2024   | v1 | Aakash Tripathi |
***
# Table of Contents

+ [Introduction](https://github.com/avengers-p7/Documentation/blob/main/GitOps/GitOps_Overview.md#introduction)
+ [Why GitOps](https://github.com/avengers-p7/Documentation/blob/main/GitOps/GitOps_Overview.md#why-gitops)
+ [GitOps Workflows ](https://github.com/avengers-p7/Documentation/blob/main/GitOps/GitOps_Overview.md#gitops-workflows)
+ [GitOps Best Practices](https://github.com/avengers-p7/Documentation/blob/main/GitOps/GitOps_Overview.md#gitops-best-practices)
+ [Conclusion](https://github.com/avengers-p7/Documentation/blob/main/GitOps/GitOps_Overview.md#conclusion)
+ [Contact Information](https://github.com/avengers-p7/Documentation/blob/main/GitOps/GitOps_Overview.md#contact-information)
+ [References](https://github.com/avengers-p7/Documentation/blob/main/GitOps/GitOps_Overview.md#references)
***
# Introduction
GitOps is a set of practices for managing infrastructure and application configuration. It leverages Git, an open source version control system that is commonly used in software development projects. This document explores different GitOps deployment strategies. For information related to GitOps Concepts please refer **[GitOps Understanding](https://github.com/avengers-p7/Documentation/blob/main/GitOps/GitOps%20Understanding.md)**.
![Gitops-cover](https://github.com/avengers-p7/Documentation/assets/156056344/58ccc877-675d-425e-a669-4260a36533e1)

For evaluation of various GitOps tools , please refer **[GitOps Tool Evaluation](https://github.com/avengers-p7/Documentation/blob/main/GitOps/Tool_Evaluation.md)**
***
# Why GitOps 
Organizations adopting GitOps are looking to be on the cutting edge of agile development practices. GitOps provides the following benefits over existing development processes:
| **Feature** | **Description** |
| ------- | ----------- |
| **Productivity** | GitOps is a practical way to implement continuous deployment, which improves development productivity. GitOps teams can deploy every change to production instead of only pushing selected releases several times a day. This faster feedback loop can dramatically improve development velocity. |
| **Developer experience** | Modern CI/CD pipelines are complex, with a variety of tools that not all developers are familiar with. With the advent of Kubernetes, environments have gotten much more complex. However, all developers are familiar with Git source control. So a GitOps model enables much faster ramp up and a smoother experience, based on concepts all developers are familiar with. |
| **Reliability** | Git forks and reverts allow teams to perform easy, reproducible rollbacks if a problem is found in an environment. The Git repository also provides a single source of truth that allows recovery from a major problem to a stable state within minutes. |
| **Compliance and security** | GitOps makes it easier to meet compliance requirements, because it automatically creates an audit log of all Kubernetes cluster changes. This makes it possible to easily investigate issues, and prove to auditors that security measures are in place. In addition, GitOps provides strong security guarantees, and the ability to sign all changes to prove authorship and origin.
| **Consistency** | GitOps makes Kubernetes consistent with development occurring in other environments. It provides one model for change management across traditional and cloud-native environments. |
***
# GitOps Workflows 
GitOps is based on pull requests. When a pull request is initialized, users can see an overview of changes in each repository-based branch. Users can then add a summary of proposed changes, view proposed changes, add tags, and mention other contributors.

After developers create a pull request, they can add a commit in the topic branch. This allows all contributors to see the actual proposed changes. Once everyone approves the changes, they can be merged with the pull request.

## **Which configuration changes can be included in a pull request?**

A GitOps pull request can include configuration changes such as:

+ Changes to application configuration
+ Changes to container images
+ Changes to Kubernetes cluster configuration
+ Fixes to errors in an environment
+ Defining new infrastructure via declarative configuration
+ Updating an environment to new requirements

## **Troubleshooting**

After a pull request is approved and the changes are deployed, if there are any problems, troubleshooting is simple. With GitOps, any problem in an environment can be tracked to specific pull requests, and then troubleshooting can focus on the changes introduced in those pull requests.

## **Integration with other systems**

GitOps can also use other tools for Git push, development, and continuous integration:

+ GitOps can work with any CI and Git server.
+ GitOps can work with CI/CD tools built for a Kubernetes environment, such as Ocean CD and Jenkins X.
+ GitOps can use any Git repository, such as GitHub, Bitbucket, Azure Pipelines, or AWS CodeDeploy.

![0_wEWyW3HxOuvX-SaS](https://github.com/avengers-p7/Documentation/assets/156056344/29242369-20c6-4c3b-97b6-5b272fa20ed5)

***

# GitOps Best Practices
Here are a few best practices you can use to improve your GitOps implementation.

| **Best Practice** | **Description** |
| -------- | ----------- |
| **Plan branching strategies** | Remember that the branching strategy you use in your source control repository has a direct effect on your environments. You must carefully plan source control branches according to the taxonomy of environments you need to set up. |
| **Avoid mixed environments** | GitOps is “all or nothing”. For it to be effective, all parts of an environment must be controlled by infrastructure as code (IaC) tools and all the configuration must be checked into the repository. Running environments where some components are managed via GitOps, and other components manually or via other automated techniques, will have unpredictable results. |
| **Leverage the merge request discussion** | When merge requests are submitted, there is a great opportunity for developers to discuss the implication of changes. Establish an effective merge request procedure, with appropriate automation patterns, and established protocols of communication, specifying what developers should ask during a pull request and what types of exchanges are appropriate for earlier planning stages. |
| **Respond when something breaks upstream** | As soon as something breaks in an upstream environment deployed by GitOps, this indicates something was wrong with the configuration used to build that environment. Set up monitoring and triggers to obtain these signals from upstream environments. When something breaks, this should be treated as an Andon cord that stops work on the GitOps configuration until the problem is resolved. |
| **Policy as Code** | GitOps can and should be complemented by automated policies that align with organizational policies. Open Policy Agent (OPA) is one framework you can use to achieve this. Policy automation can be especially important to ensure deployed environments are aligned with security and compliance requirements.
| **Idempotency** |No matter what you started with or how many times you ran a declarative configuration, the result should always be the same. Ensure you work with template engines and deployment systems that guarantee idempotency. |

***

# Conclusion 
In summary, GitOps deployment represents a modern paradigm for continuous delivery and infrastructure management. By centralizing configurations in Git repositories, it promotes transparency and collaboration while enabling version-controlled updates for both application code and infrastructure. The pull-based deployment model and automated processes enhance efficiency, ensuring that the actual system state aligns with the desired state declared in Git. Best practices include embracing Infrastructure as Code (IaC), adhering to declarative configurations, employing robust version control, and implementing role-based access control for security. Automation, observability, and testing further contribute to a reliable and agile workflow. GitOps emerges as a resilient methodology, fostering agility, minimizing errors, and facilitating swift adaptation to evolving development and operational requirements in the dynamic landscape of DevOps.
***
# Contact Information:
| Name | Email address |
| ---- | ------------- |
| Vishal | vishal.kesarwani.snaatak@mygurukulam.co |
| Aakash | aakash.tripathi.snaatak@mygurukulam.co |
***
# References:
| Source | Description |
| ------ | ----------- |
| https://www.techtarget.com/searchitoperations/definition/GitOps  | Gitops Features |
| https://www.site24x7.com/learn/what-is-gitops.html | Gitops Features |
| https://dev.to/arafetki/gitops-infra-as-code-done-right-2ojg | Gitops Workflow |
| https://www.weave.works/technologies/gitops/  | Gitops Principles |
***
