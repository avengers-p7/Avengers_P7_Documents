| Author           | Created on  | Last Updated | Document Version |
|------------------|-------------|--------------|-------------------|
| Khushi Malhotra | 16-01-2024  | 16-01-2024   |        v1          |

-------------------------------------------------------------------------------------------------------------------------------------------------------------------

# Introduction
Gitflow is an alternative Git branching model that involves the use of feature branches and multiple primary branches. It was first published and made popular by Vincent Driessen at nvie. 
Gitflow can be used for projects that have a scheduled release cycle and for the DevOps best practice of continuous delivery.

-------------------------------------------------------------------------------------------------------------------------------------------------------------------

# Purpose
Gitflow is a branching model for Git that aims to streamline the release management process and enhance collaboration within development teams. It achieves this by defining a clear structure and set of rules for how different branches should be used and interacted with.

-------------------------------------------------------------------------------------------------------------------------------------------------------------------

# Key Benefits
| Key Benefit                       | Description                                                                                                     |
|-----------------------------------|-----------------------------------------------------------------------------------------------------------------|
| **Organized Release Management**     | Separates development from release preparation, ensuring a stable main branch.                                  |
|                                       | Facilitates parallel development of features and hotfixes without disrupting the main codebase.               |
| **Improved Collaboration**            | Provides a consistent framework for developers to work within, reducing confusion and conflicts.               |
|                                   | Encourages code reviews and testing before merging into main branches.                                          |
| **Clear History and Traceability**    | Maintains a well-defined history of changes, making it easier to track feature development, hotfixes, and releases. |
|                                   | Simplifies rollbacks if necessary.                                                                              |

-------------------------------------------------------------------------------------------------------------------------------------------------------------------

# How it works
![image](https://github.com/avengers-p7/Documentation/assets/156056460/636dbd44-dd54-42c7-89b1-b5bcb68ff517)

## Here's a breakdown of the diagram:

### Main Branch:
The main branch represents the stable, production-ready version of the code. It should only be updated with releases.
- Represents the production-ready code.
- Directly reflects what is deployed in production.
### Develop Branch: 
The develop branch is where ongoing development takes place. New features are implemented and tested on the develop branch before being merged into the main branch.
- Integration branch for ongoing development work.
- Feature branches are merged into the develop branch.
### Feature Branches:
Developers create feature branches from the develop branch to work on individual features. Once a feature is complete and tested, it is merged back into the develop branch.
- Created for the development of specific features or enhancements.
- Branched off from the develop branch.
- Merged back into the develop branch upon completion.
### Release Branch: 
When a new release is ready to be shipped, a release branch is created from the develop branch. The release branch is used to stage and test the release before deploying it to production. Once the release is deployed, the release branch is merged back into both the main and develop branches.
- Created when preparing for a new release.
- Bug fixes and last-minute features are added here.
- Merged into both master and develop branches.
### Hotfix Branch: 
If a critical bug is discovered in production, a hotfix branch is created from the main branch. The hotfix branch is used to fix the bug and deploy the fix to production quickly. Once the hotfix is deployed, the hotfix branch is merged back into both the main and develop branches.
- Created to address critical issues in the production code.
- Branched off from the master branch.
- Merged into both master and develop branches.

## Here are some additional details about the Git flow workflow

| **Pull Requests** | **Versioning** | **Deployment** |
|-------------------|-----------------|-----------------|
| Developers should create pull requests to merge their changes from feature branches into the develop branch. This allows for code review and testing before the changes are merged. | Releases are typically tagged with a version number. This makes it easy to track which changes are included in each release. | The specific way that releases and hotfixes are deployed to production will vary depending on the project. |

-------------------------------------------------------------------------------------------------------------------------------------------------------------------

# Advantages and Disadvantages
| **Advantages of Gitflow**                                       | **Disadvantages of Gitflow**                                |
|------------------------------------------------------------------|-----------------------------------------------------------|
| Clear and organized branching structure: Makes the development process more transparent and easier to understand for the team. | Can be complex for small teams: The multiple branches and workflow can be cumbersome for small teams with simple projects. |
| Promotes stable releases: Isolates feature development and hotfixes from the main branch, minimizing the risk of introducing instability. | Potential for bottlenecks: Code reviews and merges can create bottlenecks if not managed effectively. |
| Enables parallel development: Different features can be worked on simultaneously without disrupting the main codebase. | Less suited for rapid release cycles: Frequent releases may cause merge conflicts and slow down the process. |
| Provides clear versioning: Releases are tagged with version numbers, simplifying release management and tracking. | Overhead for release tasks: Release branches require additional work for packaging and deployment. |
| Encourages code reviews and testing: Pull requests ensure code quality before merging to the main branch. | Not ideal for continuous integration: The focus on separate branches can clash with a continuous integration approach. |

-------------------------------------------------------------------------------------------------------------------------------------------------------------------


# Conclusion
Gitflow, while powerful, isn't a one-size-fits-all solution. Its structured approach shines in large projects with defined release cycles, but its complexity can burden smaller teams or those needing frequent releases. Consider alternative workflows for agility and simplicity, prioritizing Gitflow only if control, organization, and predictable launches are top priorities.

-------------------------------------------------------------------------------------------------------------------------------------------------------------------

# Contact Information
| Name            | Email Address                        |
|-----------------|--------------------------------------|
| Khushi Malhotra | khushi.malhotra.snaatak@mygurukulam.co |

-------------------------------------------------------------------------------------------------------------------------------------------------------------------
# Resources and References

| Resource                                  | Content                                                      |
|-------------------------------------------|--------------------------------------------------------------|
| [Git Flow Documentation](https://medium.com/@matt_weingarten/version-control-done-right-with-gitflow-8623eb051ea2) | Introduction, Gitflow                                       |
| [Atlassian Git Flow Tutorial](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow) | Diagram, How it works, Types of branches                    |
| [Advantage & Disadvantage](https://medium.com/@ferrohardian/git-flow-pros-and-cons-85b398a64848) | Advantage and disadvantage of git flow                      |

-------------------------------------------------------------------------------------------------------------------------------------------------------------------
