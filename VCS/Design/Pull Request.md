# Pull Requests  

|   Authors        |  Created on   |  Version   | Last updated by | Last edited on |
| -----------------| --------------| -----------|---------------- | -------------- |
| Vidhi Yadav      | 19 Jan 2024   |     v1     | Vidhi Yadav     | 19 Jan 2024    |

***
# Table of Contents 

***
# Introduction 
A pull request (PR) is a fundamental aspect of collaborative development on GitHub. It allows contributors to propose changes to a repository and initiate a discussion around those changes before merging them into the main codebase.

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
# Rules and Guidelines

