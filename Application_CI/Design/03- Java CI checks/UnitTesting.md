# Unit Testing in Software Development

| **Author** | **Created On** | **Last Updated** | **Document Version** |
| ---------- | -------------- | ---------------- | -------------------- |
| **Parasharam Desai** | 23-01-2024 | 23-01-2024 | V1 |

***


# Table of Contents

1. [Introduction](#introduction)
2. [What is Unit Testing?](#what-is-unit-testing)
3. [Why is Unit Testing Important?](#why-is-unit-testing-important)
4. [Unit Testing Advantages](#unit-testing-advantages)
5. [Unit Testing Disadvantages](#unit-testing-disadvantages)
6. [Different Tools for Unit Testing](#different-tools-for-unit-testing)
7. [Proof of Concept (POC) for Java Base Application](#proof-of-concept-poc-for-java-base-application)
8. [Best Practices for Unit Testing](#best-practices-for-unit-testing)
9. [Recommendation/Conclusion](#recommendation-conclusion)
10. [Contact Information](#contact-information)
11. [Resources and References](#resources-and-references)

***
# Introduction

Welcome to the documentation on Unit and Unit Testing in Software Development. This guide aims to provide a comprehensive understanding of the concepts surrounding unit testing within a software application.

***

# What is Unit Testing?

In unit testing, a **'unit'** refers to the smallest testable part of a software program, such as a function or method. A **module,** which is nothing but a single unit of software, can also be considered a 'unit.' The goal of unit testing is to test each unit, including modules, in isolation to ensure they work as intended before integrating them into the larger system.

<img width="560" length="300" alt="ut" src="https://github.com/Parasharam-DevOps/Avenger-P7/assets/132131379/cdfe8356-c6ea-407f-800a-01063a1d21b4">

**Unit testing** is a type of software testing where individual units or components of a software application are tested to ensure they meet their design and behavior requirements. These units can be functions, methods, or classes, and they are tested in isolation, without any dependencies on external components.

<img width="560" length="300" alt="ut" src="https://github.com/avengers-p7/Documentation/assets/156056413/b20adeca-16bc-4b75-bf24-0a8fc6d20d3b">

***
## Types of Unit Testing

| Manual Unit Testing                                                                                               | Automated Unit Testing                                                                                                  |
|-------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------|
| Manual testing involves human testers creating test cases, testing software without automation tools, and providing final reports.                                               | Automated testing utilizes tools for testing, making it faster and more efficient compared to manual testing.            |
| Testers manually execute test cases and observe software behavior, potentially allowing for human errors.         | Automation tools execute test cases automatically, reducing the chance of human errors and providing consistent results. |
| Manual testing is slower due to human involvement and can be time-consuming.                                      | Automated testing is faster since it's performed with automation tools, saving time and resources.                        |
| It's suitable for scenarios where human judgment and intuition are required, such as exploratory testing.         | Best suited for repetitive tasks, regression testing, and scenarios where rapid testing is needed, ensuring reliability. |


***

# Why is Unit Testing important?

Unit testing offers several benefits, including:

| **Benefits**                         | **Description**                                                                                          |
|--------------------------------------|----------------------------------------------------------------------------------------------------------|
| **Early bug detection**              | Testing individual units helps identify issues early in the development cycle, reducing overall bug fixing costs.                                                     |
| **Improved code quality**            | Unit tests ensure that each unit functions as expected, leading to a more robust and reliable codebase.                                                             |
| **Faster development**               | Unit tests provide a safety net for developers, allowing them to refactor and improve the codebase with confidence.                                                   |
| **Better collaboration**             | Unit tests help developers understand the expected behavior of individual units, making it easier for teams to collaborate and maintain the codebase. |

***
# Different Tools for Unit Testing

There are various unit testing frameworks available for different programming languages. Some popular ones include:

| **Tool Name** | **Purpose** | **Programming Language** | **Testing Types Supported** | **Ease of Learning** | **Integration with IDEs** | **Parallel Execution** | **Data-Driven Testing** | **Reports and Documentation** | **Community Support** | **Pros** | **Cons** | **Ideal Scenarios** |
|---------------|-------------|---------------------------|-----------------------------|-----------------------|---------------------------|------------------------|-------------------------|-----------------------------|------------------------|----------|----------|---------------------|
| JUnit         | Unit testing | Java | Unit testing, regression testing | Easy | Well-supported in popular IDEs like IntelliJ, Eclipse | Limited support in JUnit 4, better in JUnit 5 | Limited support | Provides basic reporting; additional tools may be needed for detailed reports | Large community | Standard in Java development | Limited support for parallel execution | Unit testing and regression testing |
| TestNG        | Versatile testing | Java | Unit testing, functional testing, end-to-end testing, integration testing | Moderate to easy | Excellent integration with popular IDEs like Eclipse, IntelliJ | Yes | Yes | Extensive reporting features, including HTML reports and custom listeners | Active community | Versatile, supports various testing types | Learning curve for beginners, can be verbose | Versatile testing needs including unit, functional, and integration testing |
| Mockito       | Mocking for unit testing | Java | Unit testing | Moderate | Integrates with popular IDEs for Java development | No direct support; can be achieved using other tools or frameworks | Limited support for parameterized tests | Limited; primarily focused on verification errors | Active community | Powerful mocking capabilities, simple syntax | Limited testing scope, not a complete testing framework | Unit testing with a focus on behavior verification |

***

# Unit Testing Advantages

There are many advantages to unit testing, including the following:

| Point                                                  | Explanation                                                       |
|--------------------------------------------------------|-------------------------------------------------------------------|
| **Early problem identification**                           | Identifying issues early reduces the likelihood of compound errors. |
| **Cost-effectiveness of early fixing**                     | Addressing problems in the early stages of development is usually less expensive than fixing them later. |
| **Simplified debugging process**                           | Early detection of issues simplifies the debugging process.        |
| **Agile codebase modifications**                           | Developers can swiftly make changes to the codebase as needed.     |
| **Code reuse and migration**                               | Enables developers to reuse code and migrate it to new projects.    |

***

# Unit Testing Disadvantages

While unit testing is integral to any software development and testing strategy, there are some aspects to be aware of. Disadvantages to unit testing include the following:

| Point                                                         | Explanation                                            |
|---------------------------------------------------------------|--------------------------------------------------------|
| **Tests may not uncover every bug**                                | Despite thorough testing, it's possible for some bugs to remain undetected.                    |
| **Limited scope of unit tests**                                    | Unit tests focus on specific sets of data and functionality, not integration aspects.           |
| **Increased test code complexity**                                 | Writing tests may require more lines of code compared to the actual code being tested.          |
| **Learning curve for implementing unit testing**                   | Developers might need to acquire new skills, such as using specific automated testing tools.    |

***

# Proof of Concept (POC) for Java Base Application

For a detailed proof of concept (POC) related to Java unit testing, please refer to [Unit Testing POC](./Application_CI/Design/03-%20Java%20CI%20checks/Unit-Testing-Poc.md).

---

# Python Unit Testing

For Python unit testing, refer to [Python Unit Testing POC](./Python_Unit_Testing_POC.md).

---

# Golang Unit Testing

For Golang unit testing, refer to [Golang Unit Testing POC](./Golang_Unit_Testing_POC.md).

***

# Best Practices for Unit Testing

| Point                                                         | Explanation                                                                                   |
|---------------------------------------------------------------|-----------------------------------------------------------------------------------------------|
| **Write tests before implementing functionality (TDD)**           | Following Test-Driven Development (TDD) methodology involves writing tests prior to coding.   |
| **Keep tests simple and isolated**                                 | Tests should focus on a single unit and be kept simple for better readability and debugging.   |
| **Write tests that are easy to understand and maintain**          | Ensure test cases are written in a clear and understandable manner to facilitate maintenance.  |
| **Ensure tests are independent and stateless**                    | Tests should not rely on external state to maintain consistency and independence.             |
| **Use test doubles for isolating units from dependencies**        | Employ mocks, stubs, and fakes to isolate units under test from external dependencies.        |
| **Aim for high test coverage without sacrificing quality**        | Strive for comprehensive test coverage while ensuring tests are meaningful and effective.     |
| **Continuously maintain and update tests as codebase evolves**    | Regularly update and refactor tests to align with changes in the codebase and requirements.    |

***

# Recommendation/Conclusion

In conclusion, JUnit is the recommended choice for Java unit testing due to its:

**Standardization:** Widely accepted in Java development.
**Integration:** Seamless integration with popular IDEs.
**Ease of Learning:** Simple syntax for quick adoption.
**Community Support:** Large and active community for ongoing assistance.
**Parallel Execution:** Improved support for optimizing test suite performance.
**Compatibility:** Works well with Maven and Gradle for versatile project setups.
By choosing JUnit, teams can ensure efficient, reliable unit testing, leading to higher code quality and faster development cycles.

***

# Contact Information

|    Name                                   | Email Address                    |
|-------------------------------------------|----------------------------------|
| **[Parasharam Desai](https://github.com/Parasharam-Desai)** | parasharam.desai.snaatak@mygurukulam.co |

***

# Resources and References

|       **Description**                                   |           **References**                    |
|---------------------------------------------------------|-----------------------------------------------|
| what is unit                                             | [What Exactly Is a Unit in Unit Testing?](https://www.blinkingcaret.com/2016/04/27/what-exactly-is-a-unit-in-unit-testing/) |
| what is unit testing                                     | [YouTube Video: What is Unit Testing?](https://www.youtube.com/watch?v=So0gxfFGmLs) |
| Advantage & disadvantage                                | [Definition of Unit Testing](https://www.techtarget.com/searchsoftwarequality/definition/unit-testing) |
| Unit Testing Best Practices                              | [Unit Testing Best Practices](https://www.softwaretestinghelp.com/unit-testing-best-practices/) |
| Top 10 Java Unit Testing Frameworks for 2023             | [Explore Top 10 Unit Testing Frameworks](https://www.scalosoft.com/blog/top-10-java-unit-testing-frameworks-for-2023/) |

