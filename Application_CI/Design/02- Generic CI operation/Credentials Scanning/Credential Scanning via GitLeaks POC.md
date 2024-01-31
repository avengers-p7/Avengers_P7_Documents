
# Credential Scanning : Proof Of Concept - GitLeaks


***
## Table Of Contents 
+ [Introduction](#introduction)
+ [GitLeaks]()
+ [GitLeaks Installation]()
+ [Credential Scanning via GitLeaks]()
+ [GitLeaks: Other Use Cases]()
+ [Conclusion]()
+ [Contact Information]()
+ [References]()
***
## Introduction 
Credential scanning is essential for maintaining the security of software development and IT environments. In the fast-paced world of technology, developers often work collaboratively on code repositories, and sensitive information such as passwords, API keys, and access tokens may unintentionally be included in the codebase. Credential scanning tools, like Gitleaks, play a crucial role in proactively identifying and mitigating security risks by systematically searching repositories for these potential vulnerabilities. 
***
## GitLeaks
![download](https://github.com/avengers-p7/Documentation/assets/156056344/5e5c49c3-a946-4836-8353-b6ee6f8ddc40)

Gitleaks is an open-source tool designed to search repositories for sensitive information like passwords, API keys, and other credentials that may have been accidentally committed.Gitleaks is specifically designed to scan Git repositories for sensitive information that might be exposed inadvertently. It helps organizations and developers identify and rectify security issues before they become a threat.

## GitLeaks Installation
Before we can use Gitleaks, we will need to install it. There are several ways to install GitLeaks like Homebrew, Docker & Go. 
The GitLeaks binary can be downloaded from the [release](https://github.com/gitleaks/gitleaks/releases) page for the GitLeaks repository.

![Screenshot 2024-02-01 013748](https://github.com/avengers-p7/Documentation/assets/156056344/0d6225d7-47b6-4891-b063-0e58fcd6727a)

### Installation Steps 

**Step 1:** Copy link to the tar based on the OS and architecture 

![Screenshot 2024-02-01 013730](https://github.com/avengers-p7/Documentation/assets/156056344/682c41fa-b5ad-4d03-9c17-268647affb0b)

**Step 2:** Download the tarball 
```shell
wget <link-we-copied>
```
![Screenshot 2024-02-01 011624](https://github.com/avengers-p7/Documentation/assets/156056344/efaf0ec1-22b9-4d58-9db7-ed01be458f06)

**Step 3:** Extract the tarball
```shell
tar xvzf gitleaks_8.18.1_linux_x64.tar.gz
```
![Screenshot 2024-02-01 011446](https://github.com/avengers-p7/Documentation/assets/156056344/4d754ff3-5d9a-4f93-b458-02bf46e3cafb)

**Step 4:** Copy gitleaks file to `/usr/local/bin`
```shell
sudo cp gitleaks /usr/local/bin/
gitleaks version
```
![Screenshot 2024-02-01 011527](https://github.com/avengers-p7/Documentation/assets/156056344/830c711d-d685-473b-82ad-dff00bc53978)

***
## Credential Scanning via GitLeaks 
The most common scenario is when we want to detect any secrets committed to our git source code repository. For this, we can:

**Step 1:** Go to the source code repository you want to detect secrets from.

```shell
cd <repo-we-want-to-scan>
```

**Step 2:** Run the following command to find the details of secrets committed in your git repository

```shell
gitleaks detect -v
```
![Screenshot 2024-02-01 012043](https://github.com/avengers-p7/Documentation/assets/156056344/08aa1fab-089c-4b62-915d-228b78b631a9)

*Another example with smaple secrets*

![Screenshot 2024-02-01 013025](https://github.com/avengers-p7/Documentation/assets/156056344/84811b1a-98ca-4953-9835-858b4a18159d)

If you have found some secrets in your source code repository and you want to erase them.

## Conclusion
In conclusion, Gitleaks stands as a pivotal tool in the realm of cybersecurity, providing a robust solution for identifying and mitigating potential security risks within Git repositories. Its capacity to systematically scan codebases for sensitive information, such as passwords and API keys, underscores its significance in preemptively addressing vulnerabilities. Gitleaks not only contributes to the maintenance of secure development practices but also aligns with the proactive ethos necessary to navigate the dynamic landscape of digital security. By integrating Gitleaks into workflows, organizations can fortify their defenses against inadvertent credential leaks, ensuring a resilient and secure foundation for their software development endeavors.

## Contact Information

| Name                 | Contact Information                                                                                     
|---------------------------------|------------------------------------------------------------|
| Aakash Tripathi                 |  aakash.tripathi.snaatak@mygurukulam.co
***
## References

|     Description                  | References  
| ---------------------------------| ------------------------------------------------------------------- |
| Credential Scanning | https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/02-%20Generic%20CI%20operation/Credentials%20Scanning/README.md |
| GitLeaks Understanding | https://akashchandwani.medium.com/what-is-gitleaks-and-how-to-use-it-a05f2fb5b034 | 

