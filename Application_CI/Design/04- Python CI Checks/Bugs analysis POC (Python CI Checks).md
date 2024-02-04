# Bugs Analysis POC (Python CI Checks)

![download__1_-removebg-preview](https://github.com/avengers-p7/Documentation/assets/156056570/241aa237-0ed1-4e36-a5bf-8846f9fc4902)


| Author                 | Created On | Last Updated | Document Version | Last Updated By |
| ---------------------- | ---------- | ------------ | ---------------- | --------------- |
| **Samir Kesare** | 04-02-2024 | 04-02-2024   | v1               |  **Samir**        |
***
## Table of Contents

+ [Bandit Introduction](#Bandit-Introduction)
+ [Key Features](#Key-Features)
+ [Pre-requisite](#Pre-requisite)
+ [Installing Bandit](#Installing-Bandit)
+ [Proof of Concept (POC)](#Proof-of-Concept-(POC))
+ [Bandit Report Analysis](#Bandit-Report-Analysis)
+ [Conclusion](#Conclusion)
+ [Contact Information](#Contact-Information)
+ [References](#References)
***
## Bandit Introduction
Bandit is a tool designed to find common security issues in Python code. To do this Bandit processes each file, builds an AST from it, and runs appropriate plugins against the AST nodes. Once Bandit has finished scanning all the files it generates a report.
Bandit is a security linter for Python code that can be used to detect common security issues in your Python code. It analyzes your Python code and reports potential security issues like vulnerabilities, insecure cryptographic practices, and hardcoded secrets.
***
## Key Features

| Feature               | Description                                                                                         |
|-----------------------|-----------------------------------------------------------------------------------------------------|
| Language Compatibility| Specifically designed for Python code analysis, supporting Python 2.x and Python 3.x codebases.      |
| Static Analysis       | Conducts static analysis of Python code to identify common security issues and vulnerabilities.     |
| Plugin Architecture   | Supports a plugin architecture, allowing users to extend its functionality with custom checks.       |
| Common Vulnerabilities| Identifies common vulnerabilities such as hardcoded secrets, unsafe use of eval(), and more.        |
| Security Checks       | Performs security checks for potential security flaws like SQL injection, XSS, and command injection.|
| Integration           | Integrates well with CI/CD pipelines and development workflows, enabling automated security checks.  |
| Extensive Reporting   | Provides detailed reports, highlighting identified issues along with severity levels and locations. |
| Configurability       | Offers configurability through various options to fine-tune analysis settings and ignore specific issues. |
| Command Line Interface| Offers a command-line interface (CLI) for easy usage and integration into existing development workflows.|
| Active Development    | Actively developed and maintained by the OpenStack Security Project, ensuring updates and improvements.|
| Open Source           | Released under an open-source license (Apache 2.0), allowing community contribution and collaboration.|

***
## Pre-requisites

| Tool   | Description                          | Python3 Support | Purpose        |
|--------|--------------------------------------|-----------------|----------------|
| Bandit | A tool for bug analysis in Python   | Yes             | Python App     |

***
## Installing Bandit

To install Bandit, you can use pip, the Python package manager. Simply run the following command in your terminal:

```sh
pip install bandit
```
Once Bandit is installed, you can start using it to scan your Python code.
![image](https://github.com/avengers-p7/Documentation/assets/156056570/788d0ff6-431b-45c7-ab78-c0c0fd6b61d3)

Running Bandit on your code
To run Bandit on your Python code, navigate to the directory containing your Python code and simply run the following command:

* Using dot (.) notation it will scan all the Python files which are inside that directory:
```sh
bandit -r .
```
* If you want to scan any specific file, you can enter the path of that Python file:
```sh
bandit -r /path/to/your/code
``
This will recursively scan all files and directories under the specified path for security issues. Bandit will generate a report highlighting any potential security issues it finds.

* By default, Bandit checks for issues with severity levels of medium and higher. If you want to include low-severity issues in the report, you can use the -ll option:
```sh
bandit -r . -ll
```
This will include low-severity issues in the report.

*You can also specify additional options to customize the behavior of Bandit. For example, you can specify a severity level threshold to filter out low-severity issues:
```sh
bandit -r /path/to/your/code -s MEDIUM
```
This command will only report issues with a severity level of MEDIUM or higher.

* You can also exclude certain files or directories from the scan by using the -x option followed by the path to exclude:
```sh
bandit -r . -x some_directory/
```
This will exclude the some_directory directory from the scan.
***
### Proof of Concept
```sh
bandit -r /home/ubuntu/employee_api
```
![image](https://github.com/avengers-p7/Documentation/assets/156056570/8d0d46d4-925e-495d-8266-273ed973b75a)
![image](https://github.com/avengers-p7/Documentation/assets/156056570/7383fea1-2400-412c-abb5-771998ad22d5)
![image](https://github.com/avengers-p7/Documentation/assets/156056570/b6888a23-0e27-424f-bc5f-dfff7d1781ba)

***
## Bandit Report Analysis

### Overview

The Bandit static analysis tool helps identify security issues in Python codebases. It scans Python files for common security pitfalls and generates reports to highlight potential vulnerabilities.

### Interpreting Bandit Reports

Bandit reports typically include the following information:

- **File Paths**: The paths to the Python files analyzed.
- **Line Numbers**: The line numbers in the files where potential security issues were found.
- **Issue Severity Levels**: Bandit categorizes issues into severity levels such as Low, Medium, and High based on the potential risk they pose.
- **Issue Descriptions**: Descriptions of the security issues detected, including details about the vulnerability and its impact.

### Actionable Steps

Once Bandit generates a report, it's essential to take appropriate actions to mitigate the identified security issues:

1. **Review Reported Issues**: Carefully review the reported issues, including their severity levels and descriptions.
2. **Prioritize Fixes**: Prioritize fixing high-severity issues that pose significant security risks to the application.
3. **Refactor Code**: Address the reported issues by refactoring the codebase to follow best practices and eliminate vulnerabilities.
4. **Automate Security Checks**: Integrate Bandit into your CI/CD pipelines to automate security checks and prevent introducing new vulnerabilities in the codebase.

### Conclusion

Bandit is a valuable tool for identifying and addressing security vulnerabilities in Python applications. By regularly running Bandit and addressing the reported issues, developers can enhance the security posture of their applications and protect against potential threats.

***
## Contact Information

| Samir Kesare                    | samir.kesare.snaatak@mygurukulam.co                                                                                  
|---------------------------------|------------------------------------------------------------|

***

## References


|     Description                  | References  
| ---------------------------------| ------------------------------------------------------------------- |
|     Installing Bandit       | https://medium.com/techbeatly/how-to-use-bandit-to-scan-your-python-code-for-security-vulnerabilities-d1f696873d0f |
|     Bandit Documentation       | https://bandit.readthedocs.io/en/latest/ |  










