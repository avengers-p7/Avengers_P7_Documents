# SonarQube : Authentication 
***
|   Authors        |  Created on   |  Version   | Last updated by | Last edited on |
| -----------------| --------------| -----------|---------------- | -------------- |
| Aakash Tripathi | 30 Jan 2024   |     v1     | Aakash Tripathi | 30 Jan 2024    |
***
## Table Of Contents 
+ [Introduction](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/07-%20Sonarqube/Authentication%20&%20Authorization.md#introduction)
+ [Authentication]()
+ [Authentication Mechanism]()
+ [Technical Details]()
+ [Conclusion]
+ [Contact Information]()
+ [References]()


## Introduction
SonarQube comes with a number of global security features:
+ On-board authentication and authorization mechanisms.
+ The ability to force users to authenticate before they can see any part of a SonarQube instance.
+ The ability to delegate to authentication
This document explores authentication mechanisms in SonarQube
***

## Authentication 
By default, SonarQube forces user authentication. We can  disable forced user authentication, and allow anonymous users to browse projects and run analyses in our instance. To do this, log in as a **system administrator**, go to **Administration** > **Configuration** > **General Settings** > **Security**, and disable the **Force user authentication property**.

> [!WARNING]
> *Disabling the **Force user authentication** can expose your SonarQube instance to security risks. It is strongly recommended to force user authentication on production instances or carefully configuring the security (user permissions, project visibility, etc.) on our instance.*

### API endpoints authentication
If the **Force user authentication** property is set to *false*, the following API endpoints are accessible without authentication (click API endpoints below to expand the list):

<details close>
  <summary>API Endpoints</summary>
<br>api/components/search</br>
<br>api/issues/tags</br>
<br>api/languages/list</br>
<br>api/metrics/domains</br>
<br>api/metrics/search</br>
<br>api/metrics/types</br>
<br>api/plugins/installed</br>
<br>api/project_tags/search</br>
<br>api/qualitygates/list</br>
<br>api/qualitygates/search</br>
<br>api/qualitygates/show</br>
<br>api/qualityprofiles/backup</br>
<br>api/qualityprofiles/changelog</br>
<br>api/qualityprofiles/export</br>
<br>api/qualityprofiles/exporters</br>
<br>api/qualityprofiles/importers</br>
<br>api/qualityprofiles/inheritance</br>
<br>api/qualityprofiles/projects</br>
<br>api/qualityprofiles/search</br>
<br>api/rules/repositories</br>
<br>api/rules/search</br>
<br>api/rules/show</br>
<br>api/rules/tags</br>
<br>api/server/version</br>
<br>api/settings/login_message</br>
<br>api/sources/scm (for public repositories)</br>
<br>api/sources/show (for public repositories)</br>
<br>api/system/dbmigrationstatus</br>
<br>api/system/migrate_db</br>
<br>api/system/ping</br>
<br>api/system/status</br>
<br>api/system/upgrades</br>
<br>api/users/search</br>
<br>api/webservices/list</br>
<br>api/webservices/response_example</br>
</details>

> [!NOTE]
> It is prudent to keep **Force user authentication** enabled if you have your SonarQube instance publicly accessible.

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

# Contact Information

| Name                 | Contact Information                                                                                     
|---------------------------------|------------------------------------------------------------|
| Aakash Tripathi                 |  aakash.tripathi.snaatak@mygurukulam.co
***
# References

|     Description                  | References  
| ---------------------------------| ------------------------------------------------------------------- |
| SonarQube Security | https://docs.sonarsource.com/sonarqube/latest/instance-administration/security/ |
| SonarQube Authentication & Provisioning  | https://docs.sonarsource.com/sonarqube/latest/instance-administration/authentication/overview/ | 

