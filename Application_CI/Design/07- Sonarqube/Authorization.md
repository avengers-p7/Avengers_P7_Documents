# SonarQube : Authorization
***
|   Authors        |  Created on   |  Version   | Last updated by | Last edited on |
| -----------------| --------------| -----------|---------------- | -------------- |
| Aakash Tripathi | 30 Jan 2024   |     v1     | Aakash Tripathi | 31 Jan 2024    |
***
## Table Of Contents 
+ [Introduction](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/07-%20Sonarqube/Authorization.md#introduction)
+ [Authorization](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/07-%20Sonarqube/Authorization.md#authorization)
+ [User](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/07-%20Sonarqube/Authorization.md#user)
+ [Group](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/07-%20Sonarqube/Authorization.md#group)
+ [Global Permissions](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/07-%20Sonarqube/Authorization.md#global-permissions)
+ [Project Permissions](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/07-%20Sonarqube/Authorization.md#project-permissions)
+ [Permission templates for default permissions]()
+ [Creators Permission](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/07-%20Sonarqube/Authorization.md#creators-permissions)
+ [Reset project permissions to a template](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/07-%20Sonarqube/Authorization.md#reset-project-permissions-to-a-template)
+ [Conclusion](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/07-%20Sonarqube/Authorization.md#conclusion)
+ [Contact Information](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/07-%20Sonarqube/Authorization.md#contact-information)
+ [References](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/07-%20Sonarqube/Authorization.md#references)



## Introduction
SonarQube comes with a number of global security features:
+ On-board authentication and authorization mechanisms.
+ The ability to force users to authenticate before they can see any part of a SonarQube instance.
+ The ability to delegate to authentication
This document explores authorization mechanisms in SonarQube
***

## Authorization
The way authorization is implemented in SonarQube is pretty standard. It is possible to create as many users and groups of users as needed. The users can then be attached (or not) to (multiple) groups. Groups and/or users are then given (multiple) permissions. The permissions grant access to projects, services, and functionalities.

To administer groups and users, choose **Administration** > **Security**, and use the sub-menu items.
***
## User
Multiple integrations that allow the delegation of authentication are available (see the [Plugin version matrix](https://docs.sonarsource.com/sonarqube/latest/instance-administration/plugin-version-matrix/)), but we can manually create and edit users at **Settings** > **Security** > **Users**. For manually-created users, login and password can be set at creation. Manually-created users can edit their passwords.

During both user creation and editing, we can set an account's screen name and email address. User login and email address will be implicitly recognized as SCM accounts if applicable, but we can set additional SCM accounts explicitly.

***

## Group

A group is a set of users.
To administer groups, go to **Administration** > **Security** > **Groups**

To edit the membership of a group, click the icon next to the membership total.

Two groups have a special meaning:
+ **Anyone** is a group that exists in the system, but that cannot be managed. Every user belongs to this group, including anonymous users.
+ **sonar-users** is the default group to which users are automatically added.

***

## Global permissions
To set global permissions, log in as a *System administrator* and go to **Administration** > **Security** > **Global Permissions.**

| **Permissions** | **Description** |
| ----------------- | ----------------|
| Administer System | All administration functions for the instance: global configuration. |
| Administer Quality Profiles | Any action on quality profiles, including delegating permissions to specific Quality Profiles. |
| Administer Quality Gates | Any action on quality gates, including delegating permissions to specific quality gates. |
| Execute Analysis | Access to all settings required to perform analysis and the ability to push analysis results to the SonarQube server. This includes private project settings but excludes secured settings like passwords. |
| Create Projects | Initialize the structure of a new project before its first analysis. This permission is also required when doing the very first analysis of a project that has not already been created via the GUI.|
| Create Applications | Create a new Application. |
| Create Portfolios | Create a new Portfolio. |

Users with any explicit create permission will see a `+` item in the top menu giving access to these functions. If these permissions are removed from global administrators, they will lose quick access to them via the `+` menu, but retain access to creation via the `Administration` menu.

> [!NOTE]
> Creating an item does not automatically grant rights to administer it. For that, see [Creators permission](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/07-%20Sonarqube/Authorization.md#creators-permissions) below.

***

## Project permissions
Project permissions are available from the project-level Administration menu: **Project Settings** > **Permissions**.
Project visibility may be toggled between `public` and `private`. Making a project `private` hides its source code and measures from the **Anyone** group. 
By default, any newly created project will be `public`. It means every SonarQube user, authenticated or not, will be able to:
| Browse | Access a project, browse its measures and issues, and perform some issue edits (confirm, assign, comment). |
|------- | ---------------------------------------------------------------------------------------------------------- |
| **See Source Code** | **View the project's source code.** |

If you want to be sure only a limited list of groups and users can see the project, you need to mark it Private. Once a project is private you will be able to define which groups and users can Browse the project or See Source Code.

If you want all newly created projects to be `private`, you can change the default visibility in **Administration** > **Projects** > **Management.**

For both public and private projects, four different permissions can be set:

| **Permissions** | **Description** |
| ----------------- | ----------------|
| Administer Issues | Resolve issues as being Won't Fix or False Positive (users also need **Browse** permission).
| Administer Security Hotspots |Change the status of a Security Hotspot.
| Administer | Access project settings and perform administration tasks (users also need **Browse** permission).By default, a user with this Administer permission can manage both configuration and permissions for the current project. To only allow project administrators to update the project configuration, go to **Administration** > **Configuration** > **General Settings** > **Security** and disable the Enable permission management for project administrators property.
| Execute Analysis | Access to all settings required to perform analysis and the ability to push analysis results to the SonarQube server. This includes private project settings but excludes secured settings like passwords. |

Private projects have two additional permissions:

| **Permissions** | **Description** |
| ----------------- | ----------------|
| Browse |Access a project; browse its measures, issues, and Security Hotspots; perform some issue edits (confirm/resolve/reopen, assignment, comment); comment on or change the user assigned to a Security Hotspot. |
|See Source Code | View the project's source code. |

> [!IMPORTANT]
> Note that permissions are not cumulative. For instance, if you want to be able to administer the project, you also have to be granted the Browse permission to be able to access the project (which is the default for public projects).You can either manually grant permissions for each project to some users and groups or apply permission templates to projects.

***

## Permission templates for default permissions
SonarQube ships with a *default permissions template*, which automatically grants specific permissions to certain groups when a project, portfolio, or application is created. It is possible to edit this template and to create additional templates. A separate template can be set for each type of resource. Further, for projects, you can have a template apply only to a subset of new projects using a project key regular expression (the template's Project Key Pattern). By default, every new project with a key that matches the supplied pattern will have the template's permissions applied.

Templates are empty immediately after creation. Clicking on the template name will take you to its permission editing interface.

Templates are administered through **Administration** > **Security** > **Permission Templates**.

***

## Creators permissions
**Creators** is a special group that appears only in the permission template editing interface. Any permissions assigned to this group will at the time of project/portfolio/application creation be granted to the single user account used to create the project. This allows SonarQube administrators to let users autonomously create and administer their own projects.

While templates can be applied after project creation, applying a template that includes Creators permissions to an existing project/portfolio/application will not grant the relevant permissions to the project's original creator because that association is not stored.

***

## Reset project permissions to a template
To apply permission templates to projects go to **Administration** > **Projects** > **Management**. You can either apply a template to a specific project using the project-specific **Actions** > **Apply Permission Template** option or use the **Bulk Apply Permission Template** to apply a template to all selected projects.

> [!IMPORTANT]
> Note that there is no relation between a project and a permission template, meaning that:
> + The permissions of a project can be modified after a permission template has been applied to this project.
> + None of the project permissions are changed when a permission template is modified.

***

## Conclusion

***

## Contact Information

| Name                 | Contact Information                                                                                     
|---------------------------------|------------------------------------------------------------|
| Aakash Tripathi                 |  aakash.tripathi.snaatak@mygurukulam.co
***
## References

|     Description                  | References  
| ---------------------------------| ------------------------------------------------------------------- |
| SonarQube Security | https://docs.sonarsource.com/sonarqube/latest/instance-administration/security/ |
| SonarQube Authentication & Provisioning  | https://docs.sonarsource.com/sonarqube/latest/instance-administration/authentication/overview/ | 


