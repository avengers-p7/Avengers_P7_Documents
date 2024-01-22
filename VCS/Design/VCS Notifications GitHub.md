

# GitHub Notifications

|   Authors        |  Created on   |  Version   | Last updated by | Last edited on |
| -----------------| --------------| -----------|---------------- | -------------- |
| Aakash Tripathi | 19 Jan 2024   |     v1     | Aakash Tripathi | 19 Jan 2024    |
***
## Table Of Contents 
1. [Introduction](https://github.com/avengers-p7/Documentation/blob/main/VCS/Design/VCS%20Notifications%20GitHub.md#introduction)
2. [Prerequisites](https://github.com/avengers-p7/Documentation/blob/main/VCS/Design/VCS%20Notifications%20GitHub.md#prerequisites)
3. [Setup Guide](https://github.com/avengers-p7/Documentation/blob/main/VCS/Design/VCS%20Notifications%20GitHub.md#setup-guide)
4. [Best Practices](https://github.com/avengers-p7/Documentation/blob/main/VCS/Design/VCS%20Notifications%20GitHub.md#best-practices)
5. [Conclusion](https://github.com/avengers-p7/Documentation/blob/main/VCS/Design/VCS%20Notifications%20GitHub.md#conclusion)
6. [Contact Information](https://github.com/avengers-p7/Documentation/blob/main/VCS/Design/VCS%20Notifications%20GitHub.md#contact-information)
7. [References](https://github.com/avengers-p7/Documentation/blob/main/VCS/Design/VCS%20Notifications%20GitHub.md#references)
***
## Introduction
GitHub provides notifications to users regarding activities related to their repositories, issues, pull requests, and other collaborative work on the platform. Notifications help users stay informed about changes, discussions, and events happening within repositories they are involved in. This document will explore how some of the Github notifications can be configured.
***
## Prerequisites 
To configure notifications on Github we need : 
1. A working GitHub account
2. An Organization and Teams
3. A repository
4. Make sure you have the authorization to configure notifications
***
## Setup Guide
   We will configure notifications for :
   | **Notification** | **Description** |
   | ---------------- | --------------- |
   | [Code Review](https://github.com/avengers-p7/Documentation/blob/main/VCS/Design/VCS%20Notifications%20GitHub.md#configuring-github-notifications-for-code-review) | Notifications to reviewer team to review code |
   | [Team Mentions]( https://github.com/avengers-p7/Documentation/blob/main/VCS/Design/VCS%20Notifications%20GitHub.md#configuring-github-notifications-for-code-review)| Notifications to team members when mentioned |
   | [Repository Events](https://github.com/avengers-p7/Documentation/blob/main/VCS/Design/VCS%20Notifications%20GitHub.md#configuring-github-notifications-for-repository-push-events) | Notifications to owner/group on repository push events |
   
### **Configuring GitHub notifications for Code Review**
1. Login to your GitHub Account and select "Your organizations"
   ![Screenshot 2024-01-21 230919](https://github.com/avengers-p7/Documentation/assets/156056344/fb58920d-381c-4110-9169-e4be4802164a)

2. From the list of all you organizations , select the one you want to configure notifications for
   ![Screenshot 2024-01-21 231627](https://github.com/avengers-p7/Documentation/assets/156056344/31aede03-5b7e-427e-b31d-fec108c8e326)

3. Go to the 'Teams' tab and pick the team you wan to configure the notifications for
   ![Screenshot 2024-01-21 232016](https://github.com/avengers-p7/Documentation/assets/156056344/d6f65814-68fa-4609-a81f-f88dcdaabd1b)

   ![Screenshot 2024-01-21 232232](https://github.com/avengers-p7/Documentation/assets/156056344/e011010b-72e5-426e-a539-8de8716798b6)

4. Select the "Settings" tab
   ![Screenshot 2024-01-21 232647](https://github.com/avengers-p7/Documentation/assets/156056344/7c56678c-9fb7-4a71-8867-7da5a483cd49)

5. Select "Code Review" form the left-side pan
   ![Screenshot 2024-01-21 233227](https://github.com/avengers-p7/Documentation/assets/156056344/61028c4a-71bd-450d-9bf9-4bcf5365873c)

6. Pick and configure the code review settings based on your requirement and click 'Save Changes'
   ![Screenshot 2024-01-21 233602](https://github.com/avengers-p7/Documentation/assets/156056344/df1577cf-99a2-4133-8835-1e628cab8b7b)

### **Configuring GitHub notifications for Teams**
1. In the "Settings Tab" from above we can enable/disable notifications for your team. Pick 'Enabled' click 'Save Changes'
   ![Screenshot 2024-01-21 234106](https://github.com/avengers-p7/Documentation/assets/156056344/568e4019-8275-4e85-bf12-e791dc88f5ba)

### **Configuring GitHub notifications for Repository Push Events**
1. On the main page of your organization, select "Repositories"
   ![Screenshot 2024-01-21 234631](https://github.com/avengers-p7/Documentation/assets/156056344/f5676bff-7a32-4b8d-9053-b50f94d16c02)

2. Pick the  repository you want to configure notifications for
   ![Screenshot 2024-01-21 234706](https://github.com/avengers-p7/Documentation/assets/156056344/b366cd37-7ed1-4a7b-9148-9df9d8bfdc28)

3. Select "Settings"
   ![Screenshot 2024-01-21 235309](https://github.com/avengers-p7/Documentation/assets/156056344/39b26071-fd90-4d28-93e7-687e42c20fa9)

4. Scroll down to the "Integrations" section and select "Email Notifications"
    ![Screenshot 2024-01-21 235518](https://github.com/avengers-p7/Documentation/assets/156056344/dbcb5135-1532-4801-bb5c-4c7bdf61de2f)

5. In the "Address" field, type up to two email addresses, separated by whitespace, where you'd like notifications to be sent. If you'd like to send emails to more than two accounts, set one of the email addresses to a group email address.
   ![Screenshot 2024-01-21 235731](https://github.com/avengers-p7/Documentation/assets/156056344/814c77ec-c35a-40bc-b537-ac20f9f921e6)

   Check "Active" and click "Setup Notifications"

**Note:** *Individual users can configure their notifications from the 'Notifications' tab in the 'Settings' section 
          ![Screenshot 2024-01-22 001153](https://github.com/avengers-p7/Documentation/assets/156056344/c9937eaa-bb51-4aae-9341-d60d55d838bd)

***
## Best Practices 
Effectively managing GitHub notifications is crucial for staying informed without being overwhelmed. Here are some best practices to help you handle GitHub notifications efficiently:
| **Best Practice** | **Description** |
| ----------------- | --------------- |
| **Customize Notification Settings** | In your GitHub account settings,adjust notification preferences based on the types of activities you want to be notified about. |
| **Use "Watching," "Starring," and "Ignoring"** | GitHub allows you to "Watch," "Star," or "Ignore" repositories. Watching a repository means you'll receive notifications for all activity, starring means you'll receive notifications only for updates, and ignoring means you won't receive any notifications. |
| **Prioritize Repositories** | If you're part of multiple repositories, prioritize them based on importance. You can mark repositories as "Pinned" to have them appear at the top of your GitHub dashboard, making it easier to focus on essential projects. |
| **Unsubscribe from Unnecessary Threads** | If you find yourself receiving notifications for threads or issues that are not relevant, unsubscribe from them. Open the thread and click on the "Unsubscribe" button to stop receiving updates. |
| **Use Filters and Labels** | Leverage GitHub's filtering options to sort and categorize your notifications. You can filter by repository, type, or reason. Additionally, use labels to categorize and tag specific notifications for easier identification. |
| **Utilize Mention Only When Necessary** | Limit the use of mentions to situations where you genuinely need someone's attention. Excessive mentions can clutter notification feeds and lead to important updates being overlooked. |

By adopting these best practices, you can streamline your GitHub notification experience, ensuring that you stay informed about relevant activities without feeling overwhelmed by unnecessary updates.
***
## Conclusion
GitHub notifications play a pivotal role in fostering effective collaboration within development teams. By providing timely updates on issues, pull requests, and repository activities, they ensure that team members stay informed, enabling seamless coordination and quick responses. Managing notifications thoughtfully not only enhances communication but also contributes to a more organized and efficient software development workflow on GitHub.

***
## Contact Information

| Name                 | Contact Information                                                                                     
|---------------------------------|------------------------------------------------------------|
| Aakash Tripathi                 |  aakash.tripathi.snaatak@mygurukulam.co
***
## References

|     Description                  | References  
| ---------------------------------| ------------------------------------------------------------------- |
| Github Docs for Notification | https://docs.github.com/en/account-and-profile/managing-subscriptions-and-notifications-on-github/setting-up-notifications/about-notifications |
| Best Practices | https://ben.balter.com/2020/08/25/how-i-manage-github-notifications/ |
