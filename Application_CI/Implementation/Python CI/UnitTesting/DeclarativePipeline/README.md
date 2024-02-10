# Python Declarative Pipeline Unit Testing POC
| Author | Created On | Last Updated | Document Version | Last Updated By |
| ------ | ---------- | ------------ | ---------------- | --------------- |
| Shantanu | 07-02-2024 | 10-02-2024   |         v1     |     Shantanu    |
***

# Table of Content

# Introduction
Testing individual units or components of a software program is a vital part of the software development process, ensuring that each part performs as intended. In this context, we utilize the pytest framework to create [unit tests,](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/04-%20Python%20CI%20Checks/UnitTesting.md) validating the functionality of specific components. This practice contributes to verifying the overall correctness and reliability of a software application. For detailed understanding on Jenkins Pipeline click [here](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Implementation/GenericDoc/jenkinsPipeline.md).
***

# Prerequisites

|  Tool  | Description  |
| ------ | ---------- |
| Jenkins | Jenkins will orchestrate the CI/CD pipeline and execute the dependency analysis stage. |
| Python | Python is a versatile, high-level programming language. |
| Pytest | It is a widely used testing framework for Python, streamlining the task of creating and running tests. |
***

# Pipeline Configuration

**Agent Configuration:** This specifies that the pipeline can run on any available agent (slave node).

```
agent any
```




