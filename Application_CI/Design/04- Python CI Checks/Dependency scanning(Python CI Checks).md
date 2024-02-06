# Dependency Scanning ( Python CI Checks ) (POC)
| Author                 | Created On | Last Updated | Document Version | Last Updated By |
| ---------------------- | ---------- | ------------ | ---------------- | --------------- |
| Vishal Kumar Kesarwani | 30-01-2024 | 06-02-2024   | v1               |  Vishal         |
***

## Table of Contents 
+ [Introduction](#Introduction)
+ [Dependency scanning](#Dependency-scanning)
+ [OWASP](#OWASP-Dependency-Check )
+ [Flow Diagram](#Flow-Diagram)
+ [Proof of Concept](#Pre-requisite)
+ [Dependency Scanning (POC) in Other Languages](#Dependency-Scanning-(POC)-in-Other-Languages)
+ [Conclusion](#Conclusion)
+ [Contact Information](#contact-information)
+ [References](#references)

***
## Introduction
Dependency scanning is vital in contemporary software development for securing and stabilizing your projects. This involves recognizing and handling the external libraries and frameworks your project relies on. By checking for known vulnerabilities in these dependencies, you can preemptively tackle security threats and maintain the strength and security of your applications. This guide will walk you through a Proof of Concept (PoC) for implementing and utilizing OWASP Dependency-Check to conduct thorough dependency scanning in your Go projects.
***
## Dependency scanning

* Dependency scanning is a process used in software development to identify and analyze the external dependencies or third-party components that a project relies on. These dependencies can include libraries, frameworks, modules, packages, or other code modules that are utilized to build and run the software. 

* The scanning process is typically automated and integrated into the development workflow, often as part of continuous integration or continuous delivery (CI/CD) pipelines. It serves as a crucial post-build process examines the project's dependencies to identify any known vulnerabilities, outdated versions, or security issues. 

* For more detail click [**here**](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/03-%20Java%20CI%20checks/Dependency%20Scanning/%20README.md)      
***
## OWASP Dependency-Check    
<img width="360" length="300" alt="OWASP" src="https://github.com/avengers-p7/Documentation/assets/156056413/4b0dadd1-816c-49d1-8436-b8d68ebe1c4c">  

OWASP is an open-source tool widely utilized for identifying known vulnerabilities in project dependencies. This tool automatically analyzes dependencies and checks them against a comprehensive database of security vulnerabilities, including the National Vulnerability Database (NVD). It supports various programming languages and build tools, making it a versatile choice for enhancing the security of software projects.
***
## Flow Diagram

![Screenshot from 2024-02-07 01-08-01](https://github.com/avengers-p7/Documentation/assets/156056413/6f0502b3-70c9-4ae6-b6e1-3bed8f7fecae)

***
## Proof of Concept
### Pre-requisite
| **Pre-requisite** | **Version** |
| ------------------ | -------- |
| Java | 17 |
| OWASP Dependency-check | 9.0.9 |
***
**OWASP Dependency-check Installation**
* Click this  [**Link**](https://owasp.org/www-project-dependency-check/) to download the zip file of OWASP .

 <img width="900" length="100" alt="python" src="https://github.com/avengers-p7/Documentation/assets/156056413/ee5ace88-343b-41bd-adec-d69d14fc42d7">

**After downloading the zip file into local system, send it to the remote server.**
  ```shell
  scp -i "key.pem" dependency-check-9.0.9-release.zip ubuntu@35.78.171.107:/home/ubuntu
  ```
> [!NOTE]
> * **key.pem** - Use your "private key".
> * **dependency-check-9.0.9-release.zip** - give the path where the zip file is downloaded.
> * **ubuntu@35.78.171.107:/home/ubuntu** - ip of the remote server and the path where you want to send the Zip file.
   
  <img width="900" length="100" alt="python" src="https://github.com/avengers-p7/Documentation/assets/156056413/fc1fc54f-f4cd-4550-8364-960c4ff2494f">
 
**First make a directory, then Within that directory clone the below repository**
  ```shell
  mkdir python
  cd python
  git clone https://github.com/OT-MICROSERVICES/attendance-api.git
  ```
  
  <img width="900" length="100" alt="python" src="https://github.com/avengers-p7/Documentation/assets/156056413/5bdf726a-6a11-4232-a1c4-12a85afd7ff1">

**Java Installation**
  ```shell
  sudo apt update
  sudo apt install openjdk-17-jdk
  ```
 <img width="900" length="100" alt="python" src="https://github.com/avengers-p7/Documentation/assets/156056413/e67c94c0-d241-4a3f-85a3-40453c9aea9c">

**Unzip the above zip file, now you will see `dependemcy-check` directory, enter into the directory  and check the dependency and generate html file.**
  ```shell
  cd /home/ubuntu/
  unzip dependency-check-9.0.9-release.zip
  cd dependemcy-check/bin/
  ./dependency-check.sh --scan /home/ubuntu/python/attendance-api --out dep-check.html
  ```

  <img width="900" length="100" alt="python" src="https://github.com/avengers-p7/Documentation/assets/156056413/d63d413e-5435-44fb-84e0-355a5e24ac8c">
  <img width="900" length="100" alt="python" src="https://github.com/avengers-p7/Documentation/assets/156056413/948b429f-9d04-4b6d-b6a4-81cd33adb822">

**HTML Report**
  <img width="900" length="100" alt="python" src="https://github.com/avengers-p7/Documentation/assets/156056413/8226250b-15b1-44ae-91d6-491284109b15">
***

## Dependency Scanning (POC) in Other Languages
* For Java , refer to this link : [**Java**](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/03-%20Java%20CI%20checks/Dependency%20Scanning%20POC/README.md)
* For Go , refer to this link : [**Go**](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/05-%20GoLang%20CI%20Checks/Dependency%20scanning%20POC%20(GoLang%20CI%20Checks).md)
  
***

## Conclusion
Implementing dependency scanning with OWASP for Python CI checks strengthens our security posture by proactively identifying and mitigating vulnerabilities in project dependencies. By integrating OWASP tools into our CI pipeline, we enhance our ability to deliver secure and reliable software to our users.
***
## Contact Information

| Name | Email address |
| ---- | ------------- |
| Vishal | vishal.kesarwani.snaatak@mygurukulam.co |

***

## References

| Source | Description |
| ------ | ----------- |
| [Link](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/03-%20Java%20CI%20checks/Dependency%20Scanning/%20README.md) | Introduction of Dependency scanning |
| [Link](https://medium.com/@sudheer.barakers/integrate-owasp-dependency-check-in-jenkins-pipeline-748d8aefc2b7) | OWASP |
| [Link](https://owasp.org/www-project-dependency-check/) | For Installation |
 
