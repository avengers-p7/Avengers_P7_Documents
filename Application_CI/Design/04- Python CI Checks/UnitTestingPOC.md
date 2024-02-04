# Python Unit Testing POC
| Author | Created On | Last Updated | Document Version | Last Updated By |
| ------ | ---------- | ------------ | ---------------- | --------------- |
| Shantanu | 02-02-2024 | 4-02-2024   |         v1     |     Shantanu    |
***

# Table of Content

# Introduction

[Unit testing](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/04-%20Python%20CI%20Checks/UnitTesting.md) is a crucial aspect of software development that involves testing individual units or components of code to ensure their proper functioning. It aims to validate that each unit, such as a function or method, works as intended and produces the expected output. So we are going to use pytest framework to do the unit test

Here we already have the unit test cases written inside the repo by the developer to check the respective Python code.

The test cases are included for the following modules and directories present inside the repo i.e route, client, model & utils

The unit test cases are written in pytest framework 

**Repo link:-** [OT-MICROSERVICES/attendance-api](https://github.com/OT-MICROSERVICES/attendance-api)
***

# POC

**Install pytest**

Ensure you have pytest installed in your Python environment. If you haven't already installed pytest, you can do so using pip:
```shell
pip install pytest
```
![Screenshot 2024-02-04 at 2 01 39 PM](https://github.com/avengers-p7/Documentation/assets/156056364/1524c430-7b5d-4603-8c2b-80714d0e0605)

**Write Your Test Functions**

Test functions should start with test_ to be discovered by pytest. For example, create a file named test_example.py:
![Screenshot 2024-02-04 at 2 19 10 PM](https://github.com/avengers-p7/Documentation/assets/156056364/dad90c51-d89e-46fc-b717-12007ca089ca)


**Run Your Tests**

For executing the test case we run the command 
```shell
python3 -m pytest
```

![Screenshot 2024-02-04 at 2 22 09 PM](https://github.com/avengers-p7/Documentation/assets/156056364/74a05b14-6e38-4ffe-9ba5-9e86b7734327)
![Screenshot 2024-02-04 at 2 22 50 PM](https://github.com/avengers-p7/Documentation/assets/156056364/a9e1362b-ea59-4db4-a141-7e563b456212)

It also shows the warning summary and sort summary info where the test cases are facing issues.
![Screenshot 2024-02-04 at 2 23 31 PM](https://github.com/avengers-p7/Documentation/assets/156056364/80f10077-4989-4965-a9cf-9647774a709b)

**Generating the report**

For generating a report, we can use this command
```shell
pytest --html=report.html
```

Additionally, there are other plugins available for generating different types of reports, such as JUnit XML reports (pytest-junitxml), JSON reports (pytest-json), and more. You can choose a plugin based on the type of report you need and install it similarly to pytest-html.


![Screenshot 2024-02-04 at 2 30 20 PM](https://github.com/avengers-p7/Documentation/assets/156056364/ed096f32-9d86-4442-9045-537ed2e767d2)
![Screenshot 2024-02-04 at 2 30 54 PM](https://github.com/avengers-p7/Documentation/assets/156056364/685da89d-9ed9-488b-9055-6d6b0bd2535b)
![Screenshot 2024-02-04 at 2 31 29 PM](https://github.com/avengers-p7/Documentation/assets/156056364/4ca00bf5-97c8-472a-a920-3c7cde06dbff)

# Conclusion
After performing unit tests in Python code through pytest framework, we are getting a detailed report regarding that each unit, such as a function or method, works as intended and produces the expected output.
***
# Contact Information
| Name | Email Address |
| ---- | ------------- |
| Shantanu  | shantanu.chauhan.snaatak@mygurukulam.co |
***
# References
| Source | Description  | 
| -------- | ------- |
| https://www.browserstack.com/guide/unit-testing-python | Python UT |
