# Static Analysis of go POC

|   Author        |  Created on   |  Version   | Last updated by  | Last edited on |
| --------------- | --------------| -----------|----------------- | -------------- |
| Khushi Malhotra |  30 Jan 2024  |  Version 1 | Khushi Malhotra  | 31 Jan 2024    |
***
# Table of Contents
- [Introduction](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/05-%20GoLang%20CI%20Checks/Static-code-analysis-poc.md#introduction)
- [Flow Diagram](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/05-%20GoLang%20CI%20Checks/Static-code-analysis-poc.md#flow-diagram)
- [Pre-requisites](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/05-%20GoLang%20CI%20Checks/Static-code-analysis-poc.md#prerequisites)
- [POC of Static Code Analysis](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/05-%20GoLang%20CI%20Checks/Static-code-analysis-poc.md#poc-of-static-code-analysis)
- [gosec Report File](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/05-%20GoLang%20CI%20Checks/Static-code-analysis-poc.md#gosec-report-file)
- [Conclusion](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/05-%20GoLang%20CI%20Checks/Static-code-analysis-poc.md#conclusion)
- [Contact Information](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/05-%20GoLang%20CI%20Checks/Static-code-analysis-poc.md#contact-information)
- [Resources and References](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/05-%20GoLang%20CI%20Checks/Static-code-analysis-poc.md#resources-and-references)
***

# Introduction
Static code analysis is a method of examining source code to identify potential defects, vulnerabilities, style lapses, or security risks without actually executing the code. It serves as a valuable tool for improving code quality, reliability, and security.

# Flow Diagram 
![image](https://github.com/avengers-p7/Documentation/assets/156056460/d9277e04-b0b9-45a5-887f-ee3d038190d9)

- Installation:
Install the necessary tools, such as Gosec for Go code.
- Running the Analysis:
Initiate the static code analysis tool, specifying the code to be analyzed.
- Storing Results:
The tool generates a report, often in a JSON file, detailing found issues.

# Prerequisites
1. Install go 
2. Install gosec


# POC of Static Code Analysis

**Step-1** Install go
``` Shell
sudo snap install go --classic
```
![WhatsApp Image 2024-01-31 at 19 50 08_4281265c](https://github.com/avengers-p7/Documentation/assets/156056460/c8b08dad-aecf-4f02-a7e7-0938b4075c0b)
***
**Step-2**  Install gosec
``` shell
sudo snap install gosec
```
![WhatsApp Image 2024-01-31 at 18 29 49_ad9184ce](https://github.com/avengers-p7/Documentation/assets/156056460/db86ed1c-60c7-46ca-a9f3-77881921dd4e)
***
**Step-3** Run Gosec
- Run gosec on your project. This will perform static code analysis and generate a report.
``` Shell
gosec ./...
```
![WhatsApp Image 2024-01-31 at 18 32 35_22af5693](https://github.com/avengers-p7/Documentation/assets/156056460/1c0ff99f-4177-444f-aed3-dd5cea9fdf02)
***
![WhatsApp Image 2024-01-31 at 18 32 48_b096c587](https://github.com/avengers-p7/Documentation/assets/156056460/192174c5-3316-4f44-a189-a1ccf9c86943)

![WhatsApp Image 2024-01-31 at 18 32 59_afa1689f](https://github.com/avengers-p7/Documentation/assets/156056460/37322234-bb24-4619-a479-c8ab876bb3fe)
***
**Step-4** Review the Report:
- After running gosec, it will generate a report highlighting any security issues it finds. The report will include information about the issues, their severity, and the affected files. Open the report in a text editor or browser.

- By default, gosec outputs the report in the console. If you want to generate a report in JSON or other formats, you can use the -fmt flag.
``` shell
gosec -fmt=json -out=gosec-report.json ./...
```
![WhatsApp Image 2024-01-31 at 18 33 43_6e7f4263](https://github.com/avengers-p7/Documentation/assets/156056460/966d3263-5618-4a6f-b2b6-be0e80cf6253)
***
# gosec Report File
[gosec-report.json](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/05-%20GoLang%20CI%20Checks/gosec-report.json)

# Conclusion
Gosec stands as a powerful tool for proactive security defense in Go development. By seamlessly integrating into your workflows and meticulously analyzing code constructs, it uncovers vulnerabilities before they can compromise application integrity.

# Contact Information
| Name            | Email Address                        |
|-----------------|--------------------------------------|
| Khushi Malhotra | khushi.malhotra.snaatak@mygurukulam.co |

# Resources and References
[What is Static Code Analysis](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/05-%20GoLang%20CI%20Checks/Static_Code_Analysis_Go_Language.md)

[Why we need Static Code Analysis](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/05-%20GoLang%20CI%20Checks/Static_Code_Analysis_Go_Language.md)

[gosec](https://opensource.com/article/20/9/gosec)
