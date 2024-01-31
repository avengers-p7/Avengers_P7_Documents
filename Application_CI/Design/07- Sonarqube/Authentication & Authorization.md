# SonarQube : Authentication 
***
|   Authors        |  Created on   |  Version   | Last updated by | Last edited on |
| -----------------| --------------| -----------|---------------- | -------------- |
| Aakash Tripathi | 30 Jan 2024   |     v1     | Aakash Tripathi | 30 Jan 2024    |
***
## Table Of Contents 
+ [Introduction]
+ [Authentication]
+ 


## Introduction
SonarQube comes with a number of global security features:
+ On-board authentication and authorization mechanisms.
+ The ability to force users to authenticate before they can see any part of a SonarQube instance.
+ The ability to delegate to authentication
This document explores authentication mechanisms in SonarQube
***

## Authentication 
By default, SonarQube forces user authentication. We can  disable forced user authentication, and allow anonymous users to browse projects and run analyses in our instance. To do this, log in as a **system administrator**, go to **Administration** > **Configuration** > **General Settings** > **Security**, and disable the **Force user authentication property**.

**NOTE:** *Disabling the **Force user authentication** can expose your SonarQube instance to security risks. It is strongly recommended tp force user authentication on production instances or carefully configuring the security (user permissions, project visibility, etc.) on our instance.*

### API endpoints authentication
If the **Force user authentication** property is set to *false*, the following API endpoints are accessible without authentication (click API endpoints below to expand the list):

<details open>
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
