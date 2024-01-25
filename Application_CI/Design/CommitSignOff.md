# Commit Sign-Off

![image](https://github.com/avengers-p7/Documentation/assets/156056460/6d952a76-4498-416b-8a4e-9f07eec2612c)
***
# What is Commit Sign-Off
A commit sign-off is a line added to the end of a commit message in a version control system, like Git, to indicate that the contributor:

- Takes responsibility for the changes introduced in the commit. This means they confirm that they authored the code, have the necessary permissions to contribute it, and it adheres to the project's guidelines and coding style.
- Agrees to the project's licensing terms. By signing off, the contributor confirms that they have the right to license the code under the project's chosen license.
***
# Why 
The purpose of a Signed-off-by trailer in Git is:-
- Improved accountability: Sign-offs make it clear who is responsible for each change in the codebase, which can be helpful for debugging and tracking down issues.
- Encourages code ownership: By requiring sign-offs, projects can encourage contributors to take ownership of their code and ensure that it meets the project's standards.
***
# Ways you can perform Commit Sign-off
| Option                       | Description                                                                                                                                                          |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Manually adding sign-off** | This is the simplest method and doesn't require any additional tools. Just follow these steps:<br>When composing your commit message in any Git client (including the command line or GitHub web interface), add the sign-off line at the end.  |
| **Using automation**         | Several tools and techniques can automate the sign-off process, saving you time and effort. Here are some options:<br>- **Git configuration:** You can configure Git globally or per repository to automatically add the sign-off line to every commit.  |
***
# Advantages

| **Advantages of Commit Sign-off**                                   | 
|---------------------------------------------------------------------|
| **1. Accountability:**                                              | 
|     Commit sign-off clearly identifies who is responsible for the changes introduced in a particular commit. This improves traceability and facilitates debugging or reverting changes if needed. | 
| **2. Code ownership:**                                              | 
|     Sign-off can imply ownership and acceptance of the code within a project. This helps maintain code quality and ensures that changes adhere to project standards. | 
| **3. Review process:**                                              | 
|     Sign-off often signifies that the code has undergone proper review and approval before being merged into the main branch. This strengthens the code quality and reduces the risk of regressions. | 
| **4. Contributor recognition:**                                    | 
|     Publicly acknowledging contributions through sign-off can boost developer morale and encourage participation.                | 
***
# Disadvantages

| **Disadvantages of Commit Sign-off**                               | 
|---------------------------------------------------------------------|
| **1. Overhead:**                                                    | 
|     Implementing and enforcing a sign-off process can add complexity and overhead to the development workflow, especially for small projects or frequent contributors. |
| **2. Attribution disputes:**                                        | 
|     In some cases, disputes may arise regarding the actual responsibility for changes when multiple developers are involved in a single commit. |
| **3. Fear of contribution:**                                         | 
|     Strict sign-off requirements might discourage junior developers or new contributors from submitting their work due to fear of making mistakes or not meeting expectations. |
| **4. False sense of security:**                                     | 
|     Relying solely on sign-off as a quality measure can be misleading. Thorough code review and testing remain crucial for ensuring code quality. |
***
# Proof of Concept 
***
## 1. Enforce Commit Sign-offs through Web Interface

**Step-1** Access the repository:
- Navigate to the GitHub repository in your web browser.

![image](https://github.com/avengers-p7/Documentation/assets/156056460/0a9ea5eb-1be1-433c-a92e-14edb7b53016)
***
**Step-2** Make your changes:
- Click on the file(s) you want to edit.
- Make the necessary changes directly in the web editor.

![image](https://github.com/avengers-p7/Documentation/assets/156056460/2d35a8a5-2719-4e20-8ed8-e764ea37258a)
***
**Step-3** Commit your changes:
- Locate the "Commit changes" section.
- Manually add sign-off.
- Type a clear and concise commit message summarizing your changes.
- Add the following line at the end of the message:
```shell
Signed-off-by: Your Name <your_email_address>
```
- Replace with your actual name and email address.
- Click the "Commit changes" button to create the commit with the sign-off.

![image](https://github.com/avengers-p7/Documentation/assets/156056460/ab294094-d8fb-4df4-b10e-a2ecf829542f)
***
Now the Commit also displays the Committer details.

![image](https://github.com/avengers-p7/Documentation/assets/156056460/3c81b43f-96d5-4423-8f54-6cf72b03bd2e)
***
In the Slack Notification and Email notification the Committer details are displayed.
![image](https://github.com/avengers-p7/Documentation/assets/156056460/a9f45a5a-c330-4017-874b-6b1f7a7b6a5f)
![image](https://github.com/avengers-p7/Documentation/assets/156056460/9670c773-15e8-4d1a-8fa3-907510560dc5)
***

## 2. Enforce Commit Sign-offs through CLI
***
**Step-1** Clone the repository:
- Open your terminal or command prompt.
- Navigate to the desired directory using the cd command.
- Run ```git clone <repository_url>``` to clone the repository to your local machine. Replace "<repository_url>" with the actual HTTPS or SSH URL of the repository.

![image](https://github.com/avengers-p7/Documentation/assets/156056460/9b37caf6-f36f-4773-b49f-44bce1bd7606)
***
**Step-2**Make changes to the code:
- Use your preferred text editor or IDE to edit the files in the cloned repository.
- Make the necessary changes to the code.

![image](https://github.com/avengers-p7/Documentation/assets/156056460/60cc2c2c-2a83-45e1-a568-b0f55f2005dc)
***
**Step-3** Stage your changes:
- Run ```git add <modified_files>``` to stage the specific files you've changed, or git add . to stage all modified files.

![image](https://github.com/avengers-p7/Documentation/assets/156056460/b2d1260e-7180-4505-acb3-93406695d860)
***
**Step-4** Commit with sign-off:
- Using the -s or --signoff flag
```shell 
git commit --signoff -m "Fix issue with <details of the issue>. Updated <specific files affected>.
Signed-off-by: Your Name <your_email_address>"
```

![image](https://github.com/avengers-p7/Documentation/assets/156056460/8cf56189-5fbd-4861-a2c3-f50cd17f7956)
***
**Step-5** Push your changes:
- Run ``` git push``` to push your committed changes, including the sign-off, to the remote repository on GitHub.

![image](https://github.com/avengers-p7/Documentation/assets/156056460/05075dab-0399-4bd1-8f5c-1a931dc936eb)
***
**Step-6** Verify sign-off: 
- Run ``` git show ```to view the complete commit message and confirm the Signed-off-by line is present.

![image](https://github.com/avengers-p7/Documentation/assets/156056460/2adb69c3-5021-457f-b385-460be59d56cf)
***
