# SonarQube : Authorization
***
|   Authors        |  Created on   |  Version   | Last updated by | Last edited on |
| -----------------| --------------| -----------|---------------- | -------------- |
| Aakash Tripathi | 30 Jan 2024   |     v1     | Aakash Tripathi | 31 Jan 2024    |
***
## Table Of Contents 
+ [Introduction](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/07-%20Sonarqube/Authentication%20&%20Authorization.md#introduction)
+ [Authorization](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/07-%20Sonarqube/Authentication.md#authentication)
+ [Authentication Mechanism](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/07-%20Sonarqube/Authentication.md#authentication-mechanisms)
+ [Technical Details](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/07-%20Sonarqube/Authentication.md#technical-details)
+ [Conclusion](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/07-%20Sonarqube/Authentication.md#conclusion)
+ [Contact Information](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/07-%20Sonarqube/Authentication.md#contact-information)
+ [References](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/07-%20Sonarqube/Authentication.md#references)

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

## Authentication Mechanisms
Authentication can be managed through a number of mechanisms:
+ Via the SonarQube built-in users/groups database.
+ Via several delegated authentication method

### Supported authentication methods
We can use one of the following authentication methods to allow the same authentication between SonarQube and our authentication system:

| **Authentication Method** | **Description** |
| ------------------------- | --------------- |
|[ **HTTP header** ](https://docs.sonarsource.com/sonarqube/latest/instance-administration/authentication/http-header/)| We can delegate user authentication to third-party systems (proxies/servers) using HTTP header authentication. |
| [ **LDAP** ](https://docs.sonarsource.com/sonarqube/latest/instance-administration/authentication/ldap/) | We can configure SonarQube authentication and authorization to an LDAP server (including the LDAP service of Active Directory) by configuring the correct values in *<sonarqubeHome>/conf/sonar.properties* |
| [ **SAML** ](https://docs.sonarsource.com/sonarqube/latest/instance-administration/authentication/saml/overview/) | We can delegate authentication to a SAML 2.0 identity provider using SAML authentication. SonarQube uses the Service Provider (SP) initiated SAML. Available with [Azure AD](https://docs.sonarsource.com/sonarqube/latest/instance-administration/authentication/saml/how-to-set-up-azure-ad/),[Keycloak](https://docs.sonarsource.com/sonarqube/latest/instance-administration/authentication/saml/how-to-set-up-keycloak/),[Okta](https://docs.sonarsource.com/sonarqube/latest/instance-administration/authentication/saml/how-to-set-up-okta/) |
| [ **GitHub** ](https://docs.sonarsource.com/sonarqube/latest/instance-administration/authentication/github/) | To allow users to log in with GitHub credentials, we'll need to connect SonarQube to a GitHub App. This will also allow us to configure user, group, and permission provisioning. |
| [ **Bitbucket Cloud** ](https://docs.sonarsource.com/sonarqube/latest/instance-administration/authentication/bitbucket-cloud/) | To allow users to log in with Bitbucket Cloud credentials, we need to use an OAuth consumer and set the authentication settings in SonarQube. |
| [ **GitLab** ](https://docs.sonarsource.com/sonarqube/latest/instance-administration/authentication/gitlab/)| We can delegate authentication to GitLab using a dedicated GitLab OAuth application. |
***
## Technical Details 
When we create a user in SonarQube's own database, it is considered local and will only be authenticated against SonarQube's own user/group database rather than against any external tool (LDAP, Active Directory, Crowd, etc.). By default, `admin` is a local account.

Similarly, all non-local accounts will be authenticated only against the external tool.

An Administrator can manage tokens on a user's behalf via **Administration** > **Security** > **Users**. From here, click in the user's Tokens column to see the user's existing tokens, and either revoke existing tokens or generate new ones. An *Administrator* can only create user tokens on behalf of another user. Once established, a token is the only credential needed to run an analysis. Tokens should be passed as the value of the `sonar.token` property.
***

## Conclusion
SonarQube comes with its own user database, as well as the ability to delegate authentication via protocols and providers. Each method offers:
+ User identity management
+ Authentication
+ User and group provisioning 
+ Group synchronization (optional for JIT provisioning)

These measures enhance security by controlling access to code analysis tools, ensuring a secure and accountable environment for developers.

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


