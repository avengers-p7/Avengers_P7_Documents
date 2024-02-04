
# License Scanning : Proof Of Concept - FOSSA


***
## Table Of Contents 
+ [Introduction](#introduction)
+ [FOSSA](#fossa)
+ [FOSSA Setup](#fossa-setup)
+ [License Scanning via FOSSA](#license-scanning-via-FOSSA)
+ [Conclusion](#conclusion)
+ [Contact Information](#contact-information)
+ [References](#references)
***
## Introduction 
License scanning refers to the process of automatically analyzing and identifying software licenses associated with code or components within a software project. This practice is crucial for organizations to ensure compliance with open-source licenses, proprietary licenses, and other legal requirements.
***
## FOSSA
![9543448](https://github.com/avengers-p7/Documentation/assets/156056344/4b206b0a-bbba-4db6-977c-d4b05fb267d9)

FOSSA is a comprehensive software license compliance and dependency analysis platform designed to assist organizations in managing open-source components within their software projects. The acronym "FOSSA" stands for "Free and Open Source Software Analyzer."

## FOSSA Setup
Before we can use FOSSA, we will need to set it up locally. There are several ways to use  FOSSA like Quick Import, SBOM Import & locally integrating CLI. 
We will use the CLI as it allows us to use our personal or build machine for accurate, secure & performant results.

### Installation Steps 

**Step 1:** 
Go to the [FOSSA Website](https://fossa.com/) and select *Start For Free*
![Screenshot 2024-02-03 153557](https://github.com/avengers-p7/Documentation/assets/156056344/2245ae9c-2afb-4a8d-8a44-77d8e13abd46)



**Step 2:** Sign Up  
Provide a valid email and setup a password to get started with FOSSA
![Screenshot 2024-02-03 154001](https://github.com/avengers-p7/Documentation/assets/156056344/bdf5086a-7440-49a6-8960-c3c7acc177b2)

**Step 3:** Select CLI Option
![Screenshot 2024-02-03 152532](https://github.com/avengers-p7/Documentation/assets/156056344/300ed5f3-92e5-4aad-af9c-6e05fe918305)

**Step 4:** Run command on your machine.

```shell
curl -H 'Cache-Control: no-cache' https://raw.githubusercontent.com/fossas/fossa-cli/master/install-latest.sh | bash
```
![Screenshot 2024-02-03 152719](https://github.com/avengers-p7/Documentation/assets/156056344/d300031e-f1f9-419f-abc2-fc5815911c31)

**Step 5:** Set your API key

```shell
export FOSSA_API_KEY=<Your-API-Key>
```
![Screenshot 2024-02-03 152739](https://github.com/avengers-p7/Documentation/assets/156056344/4d31c4b6-949f-4042-810d-c091f9e16429)

FOSSA is now ready for use 

***
## License Scanning via FOSSA 

Navigate into your code directory and run the following command.
```shell
fossa analyze
```
![Screenshot 2024-02-01 163108](https://github.com/avengers-p7/Documentation/assets/156056344/af10dd6a-d739-4257-baed-b5d8dd274956)

*Another example with warnings*
![Screenshot 2024-02-01 163150](https://github.com/avengers-p7/Documentation/assets/156056344/6a0f6506-d641-4e61-81d7-ee50e3f62c22)


## Conclusion
As organizations increasingly recognize the importance of managing open-source components effectively, FOSSA emerges as a valuable tool in safeguarding intellectual property, mitigating legal risks, and promoting secure and compliant software development practices. Its adoption signifies a commitment to transparency, efficiency, and the long-term sustainability of software projects in an ever-evolving landscape of open-source contributions.

## Contact Information

| Name                 | Contact Information                                                                                     
|---------------------------------|------------------------------------------------------------|
| Aakash Tripathi                 |  aakash.tripathi.snaatak@mygurukulam.co
***
## References

|     Description                  | References  
| ---------------------------------| ------------------------------------------------------------------- |
| FOSSA Setup  | https://blog.opstree.com/2023/04/04/fossa-audit-grade-open-source-dependency-protection/#more-13285 |
| FOSSA Docs | (https://docs.fossa.com/docs/introduction)https://docs.fossa.com/docs/introduction | 


