# Pull Requests  

|   Authors        |  Created on   |  Version   | Last updated by | Last edited on |
| -----------------| --------------| -----------|---------------- | -------------- |
| Vidhi Yadav      | 19 Jan 2024   |     v1     | Vidhi Yadav     | 19 Jan 2024    |

***
# Table of Contents 
+ [Introduction](#introduction)
+ [Flow Diagram](#pull-requests-flow)
+ [Pull Request Creation](#creating-a-pull-request)
+ [Pull Request Checklist](#pull-request-checklist)
+ [Guidelines](#rules-and-guidelines)
+ [Reviewing Pull Requests](#review-process)
+ [Closing Pull Requests](#closing-pull-requests)
+ [Conclusion](#conclusion)
+ [Contact Information](#contact-information)
+ [References](#references)





***
# Introduction 
A pull request is a proposal to merge a set of changes from one branch into another. This mechanism is fundamental in collaborative software development workflows, allowing team members to thoroughly review and discuss the proposed alterations before incorporating them into the main codebase. 

The pull request acts as a communication hub where developers can engage in discussions, ask questions, and collaborate to ensure that the proposed changes align with the project's objectives and coding standards.
The primary purpose of this process is to maintain code quality, prevent errors, and promote a more informed decision-making process.

*** 
# Pull Requests flow 
![image](https://github.com/avengers-p7/Documentation/assets/156056349/3fc47489-9a3e-481a-b674-75acacbcaa1d)

***
# Creating a Pull Request
### **Step 1: Fork the Repository** 
Forking creates a personal copy of the repository on your GitHub account. It allows you to make changes without affecting the original project. Click the `Fork` button on the top right of the repository page to create your own fork.

<img width="1273" alt="Screenshot 2024-01-19 at 5 47 31 PM" src="https://github.com/avengers-p7/Documentation/assets/156056349/3bd20e2d-31bc-4518-b7ba-204af9f72fb6">

***
### **Step 2: Clone the Forked Repository**
Use the git clone command with the URL of your forked repository to download a local copy. This copy is where you'll make and test your changes.

<img width="1078" alt="Screenshot 2024-01-19 at 5 53 22 PM" src="https://github.com/avengers-p7/Documentation/assets/156056349/d1c521ff-04a8-460e-8c48-f85668733bd5">

***
### **Step 3: Create a Branch**
Branches isolate changes from the main codebase. Use `git checkout -b branch-name` to create and switch to a new branch. Naming your branch appropriately helps others understand the purpose of your changes.

<img width="776" alt="Screenshot 2024-01-19 at 6 57 25 PM" src="https://github.com/avengers-p7/Documentation/assets/156056349/9e8402d8-a880-4f65-a030-67afa35ad9f4">

***
### **Step 4: Make Changes**
Make necessary code or documentation modifications in your local branch. Ensure your changes align with the purpose of your contribution, whether it's fixing a bug, adding a documentation or any new feature.

<img width="1135" alt="Screenshot 2024-01-19 at 7 04 41 PM" src="https://github.com/avengers-p7/Documentation/assets/156056349/423618dd-b53a-411e-a890-d1369f7f0bff">


***
### **Step 5: Commit Changes**
Commits save changes with a message describing what was done. Use `git commit -m "your message"` to commit changes. Clear and concise commit messages help collaborators understand your intentions.

<img width="1039" alt="Screenshot 2024-01-19 at 7 10 19 PM" src="https://github.com/avengers-p7/Documentation/assets/156056349/b5b46607-731a-45d2-904d-17f888b9c0ce">


***
### **Step 6: Push Changes**
Pushing uploads your local branch and commits to your forked repository on GitHub. Execute `git push origin branch-name` to push changes. This makes your modifications accessible for creating a pull request.

<img width="786" alt="Screenshot 2024-01-19 at 7 14 47 PM" src="https://github.com/avengers-p7/Documentation/assets/156056349/8fb46275-92c3-4280-aadd-90ae4d4c3735">

***
### **Step 7: Create Pull Request**
A pull request proposes changes to the original repository. Navigate to the original repository, click `New Pull Request`, select your branch, and follow the prompts. Write a clear title and description to help reviewers understand the purpose of your contribution.

<img width="1259" alt="Screenshot 2024-01-19 at 7 26 27 PM" src="https://github.com/avengers-p7/Documentation/assets/156056349/3f3d8aa3-d212-41c6-9638-bab825e1a72e">




<img width="1001" alt="Screenshot 2024-01-19 at 7 28 35 PM" src="https://github.com/avengers-p7/Documentation/assets/156056349/3e78b859-0bf8-4d7b-84e3-31f99c8eb944">

> Note: While forking is common in organizational workflows, it's not mandatory for feature branches. Instead, create a branch within the existing repository. Submit a pull request from your branch, and if approved, changes can seamlessly integrate into the main branch without the need for a separate fork, streamlining collaboration.

***
# Pull Request Checklist

- [x] Tag the issue #[issue_number] (e.g., #42) to automatically close it upon merging.
- [x] Tag the issue author @[author] (e.g., @issue_author) for visibility.
- [x] Describe your change in detail to provide comprehensive context.
- [x] Explain your testing approach to ensure the reliability of your change.

***

# Rules and Guidelines

+ Use the provided checklist in the pull request template for verbosity and completeness.
+ Thoroughly test your changes to ensure they work as intended. Provide test cases where applicable to maintain code reliability.
+ Update or create documentation to reflect your changes. This ensures that others can easily understand and use your contributions.
+ Engage in the review process actively. Address and incorporate feedback from reviewers, fostering collaboration and maintaining code quality.

***
# Review Process

+ Reviewers analyze the code for adherence to coding standards, logic errors, and potential issues. Provide constructive feedback to improve code quality.
+ Engage in discussions during the review process. Collaborate with contributors to enhance the quality of the code and address concerns.
+ Only authorized maintainers can merge pull requests. Ensure that all review comments are addressed before merging to maintain code integrity.
+ Emphasize the caution associated with force pushing commits to a pull request. Highlight the potential risks of altering repository history and the impact on collaborators.

***
# Closing Pull Requests
After successful review and approval, the pull request is merged. Contributors should delete their feature branches after merging to keep the repository clean.

<img width="998" alt="Screenshot 2024-01-19 at 7 51 44 PM" src="https://github.com/avengers-p7/Documentation/assets/156056349/8f7d17b0-bf71-4019-8a3f-76dcec5b388d">

***
# Conclusion
In conclusion, the outlined guidelines not only streamline the collaborative development process but also contribute to the overall health of the project. By adhering to these established steps and rules, contributors actively contribute to a culture of transparency, thorough review, and continuous improvement. This collaborative approach not only ensures the integration of high-quality contributions but also promotes a positive and effective working environment within the development community.

***
# Contact Information

|Vidhi Yadav                     | vidhi.yadhav.snaatak@mygurukulam.co                                                                                      
|---------------------------------|------------------------------------------------------------|

***
# References

|     Description                  | References  
| ---------------------------------| ------------------------------------------------------------------- |
|     PR Checklist                | https://opensource.creativecommons.org/contributing-code/pr-guidelines/
|     Force pushing caution     | https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests        
|     PR Understanding                   | https://www.youtube.com/watch?v=For9VtrQx58


