
# VCS Notifications Concept 

|   Authors        |  Created on   |  Version   | Last updated by | Last edited on |
| -----------------| --------------| -----------|---------------- | -------------- |
| Aakash Tripathi | 18 Jan 2024   |     v1     | Aakash Tripathi | 19 Jan 2024    |
***
## Table Of Contents 
1. Introduction
2. Why Notifications
3. Types of Notifications
4. Events for VCS Notifications
5. Conclusion
6. Contact Information
7. Refrences
***
## Introduction
A Version Control System (VCS) plays a crucial role in software development by managing changes to source code, documents, and other project assets. A VCS notification system is a mechanism that informs users or stakeholders about changes, updates, or events related to a version-controlled project. A notification system enhances collaboration, communication, and awareness among team members. 
***
## Why VCS Notifications
A Version Control System (VCS) notification system is crucial in a collaborative development environment for several reasons:

| Features                        | Description                                                                                                                   |
|---------------------------------|-------------------------------------------------------------------------------------------------------------------------------|.
| Collaboration and Communication | Stakeholders need to be aware of changes made by their peers to avoid conflicts and ensure that everyone is on the same page. |
| Timely Resolution of Issues     | Alerts team members about new issues or updates on existing ones. This ensures that critical issues are addressed promptly.   |
| Continuous Integration and Deployment (CI/CD) | Integrates with CI/CD systems to provide notifications on build successes, failures, and other pipeline events. | 
| Security Alerts | Notifies developers about security vulnerabilities in the codebase or dependencies and alerts on access/changes to the codebase.              |.
| User Mentions and Discussions| Allows for targeted communication through user mentions in commit messages, pull requests, or issues. 
| Customizable Notifications |Enables users to customize their notification preferences based on their role, responsibilities, and the areas of the project they are interested in. This helps avoid information overload. |
***
## Types of Notifications 
The frontend application have dependencies on other REST API of **[OT-Microservices](https://github.com/OT-MICROSERVICES)**. To run the application successfully, we need these things configured:

## Events for VCS Notifications 

## Conclusion
**Javascript heap out of memory error**
During the build phase one might encounter javascript heap out of memory error.
![Screenshot from 2024-01-16 00-25-27](https://github.com/avengers-p7/Documentation/assets/156056413/d5202499-699c-496e-a874-7b7662e26c7b)
This can be resolved using `export NODE_OPTIONS="--max-old-space-size=512"`    
**NOTE:** Ideally the size should not be more than half the size of memory(RAM) .

***
# Contact Information

| Name                 | Contact Information                                                                                     
|---------------------------------|------------------------------------------------------------|
| Aakash Tripathi                 |  aakash.tripathi.snaatak@mygurukulam.co
***
# References

|     Description                  | References  
| ---------------------------------| ------------------------------------------------------------------- |
| Frontend API | https://github.com/OT-MICROSERVICES/frontend |
| Javascript heap out of memory error |https://geekflare.com/fix-javascript-heap-out-of-memory-error/ | 
| Default index file for public folder | https://github.com/react-cosmos/create-react-app-example/blob/master/public/index.html |
