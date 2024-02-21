# Documentation of Jenkins Plugin Installation 


![image](https://github.com/avengers-p7/Documentation/assets/156644891/50a769a7-2076-4ed7-8d56-3bf6ce448388)


| Author                                                           | Created on  | Version    | Last Updated by | Last Updated on |
| ---------------------------------------------------------------- | ----------- | ---------- | --------------- | --------------- |
| Nidhi Bhardwaj                                                    | 20-02-2024  | 1.0        | Nidhi Bhardwaj   | 20-02-2024      |




***
# Table of contents 

1. [Introduction](#Introduction)
2. [What is a Jenkins plugin](#What-is-a-jenkins-plugin)
3. [Pre-requisites](#Pre-requisites)
4. [Steps to install Plugin](#Steps-to-install-plugin)
5. [Conclusion](#Conclusion)
6. [Resource and Reference](#Resource-and-Reference)
7. [Contact Info](#Contact-Information)




***
# Introduction 
Jenkins for continuous integration/continuous deployment (CI/CD) processes, installing plugins is a fundamental step in tailoring the server to meet specific project requirements. Jenkins plugins serve as modular extensions that enhance its core functionalities, providing capabilities ranging from source code management to deployment and monitoring. The installation of plugins is seamlessly integrated into the Jenkins ecosystem, facilitated by the Plugin Manager interface, which allows users to browse, install, update, and manage plugins effortlessly. With a vast repository of open-source plugins maintained by the community, users can easily extend Jenkins to integrate with various tools and services, customize workflows, and automate repetitive tasks. 


***

# What is a Jenkins plugin


A Jenkins plugin is an essential component that extends the functionality of the Jenkins automation server, allowing users to customize and enhance its capabilities according to their specific requirements. These plugins are modular software packages that integrate seamlessly with Jenkins, providing additional features, integrations, and tools to support various aspects of the software development lifecycle. Jenkins plugins cover a wide range of functionalities, including source code management, build triggers, testing frameworks, deployment automation, monitoring, and reporting. 


***


# Pre-requisites

|Tool|Description|
|----|------------|
|Jenkins|This is required to install plugins|


***


### Here is the list of some plugins we have installed on our Jenkins as a part of our requirements:

1. Blue Ocean

2. SonarQube Scanner for Jenkins

3. OWASP Dependency-Check Plugin

4. Aws Credential

5. Slack Notification

**Note: This is not the complete list, we will continue adding plugins as required**


***


# Steps to install Plugin


**Jenkins provides two methods for installing plugins on the controller**

**1. Using the "Plugin Manager" in the web UI**

 **2. Using the Jenkins CLI install-plugin command**


Each approach will result in the plugin being loaded by Jenkins but may require different access levels and trade-offs.

The two approaches require that the Jenkins controller be able to download meta-data from an Update Center, whether the primary Update Center operated by the Jenkins project [1], or a custom Update Center.

The plugins are packaged as self-contained .hpi files, which have all the necessary code, images, and other resources that the plugin needs to operate successfully.



# Blue Ocean



The simplest and most common way of installing plugins is through the **Manage Jenkins > Plugins view**, available to administrators of a Jenkins environment.

Under the Available tab, plugins available for download from the configured Update Center can be searched and considered: 





![Screenshot from 2024-02-09 22-00-41](https://github.com/avengers-p7/Documentation/assets/156644891/039dece4-386e-42d8-b7ce-43a793abae0d)








![image](https://github.com/avengers-p7/Documentation/assets/156644891/3256cce6-00c6-4024-8eb0-c7fb7f695302)










![image](https://github.com/avengers-p7/Documentation/assets/156644891/7ed46f7b-5787-46a0-8986-7a784f76eea4)



 





# Sonarqube 


SonarQube is an open-source platform developed for continuous inspection of code quality to perform automatic reviews with static analysis of code to detect bugs, code smells, and security vulnerabilities. Plugins extend the functionality of SonarQube to support additional languages, frameworks, and integrations.


**Navigate to plugins**

Now follow path Dashboard > Manage Jenkins > Plugins




![image](https://github.com/avengers-p7/Documentation/assets/156644891/2339b401-a0b5-434c-8a02-311f0702a3f0)







![image](https://github.com/avengers-p7/Documentation/assets/156644891/ad994575-fc47-4d5f-a74c-a33526a3c65e)








![image](https://github.com/avengers-p7/Documentation/assets/156644891/7f3fa7ae-02b3-4afc-9d77-5d1403dd32bc)





# OWASP Dependency-Check Plugin


OWASP Dependency-Check Plugin in Jenkins is a powerful tool designed to enhance the security of your software projects by identifying and managing vulnerabilities in project dependencies. OWASP, or the Open Web Application Security Project, is a nonprofit organization dedicated to improving software security. The Dependency-Check Plugin integrates with Jenkins, a popular automation server, to automate security checks on project dependencies as part of the continuous integration (CI) and continuous delivery (CD) pipeline.





![image](https://github.com/avengers-p7/Documentation/assets/156644891/b9512480-e6d6-4c86-9e5d-5979f8f9cb1f)









![image](https://github.com/avengers-p7/Documentation/assets/156644891/ca0c441a-7db6-4390-9a6f-2d9b48121d03)






# AWS Credentials Plugin


AWS credentials are essential pieces of information that grant access to Amazon Web Services (AWS) resources and services. These credentials typically consist of an Access Key ID and a Secret Access Key, which are used to authenticate and authorize API requests made to AWS. Access Key IDs serve as the username, while Secret Access Keys function as the password, providing a secure means of accessing AWS resources programmatically or through the AWS Management Console.





 ![image](https://github.com/avengers-p7/Documentation/assets/156644891/49587f56-066c-403f-9123-a23ef4edfd45)

 




# Slack Notification




Slack notifications serve as a crucial communication mechanism within teams, providing real-time updates and alerts on various events and activities. Integrating Slack with other tools and services, such as continuous integration/continuous deployment (CI/CD) pipelines or monitoring systems, enables teams to receive timely notifications directly within their Slack channels, streamlining collaboration and enhancing visibility into project workflows. These notifications can range from build status updates, deployment notifications, and error alerts, to task assignments, facilitating rapid response and coordination among team members. By configuring Slack notifications, teams can centralize communication, ensure everyone stays informed, and foster a culture of transparency and collaboration



![image](https://github.com/avengers-p7/Documentation/assets/156644891/581eb302-6717-4967-82de-e7eed102f565)









![image](https://github.com/avengers-p7/Documentation/assets/156644891/09d8bc75-9136-438f-b9b3-3b8724f1ec8a)



> [!Note]
> **This is not the complete list, we will continue adding plugins as required.**

***
# Conclusion



In short, we talked about the basics of Jenkins plugins, and how they help Jenkins do more stuff. We covered the simple steps to install and set them up, showing you how to use the plugin manager to handle everything.


***
# Resource and Reference



| **Links** | **Description** |
| --------- | --------------- |
| https://plugins.jenkins.io/ | Main Documentation |



***
# Contact Information


|Name|Email|
|-----|-----|
|Nidhi|nidhi.bhardwaj.snaatak@mygurukulam.co|





