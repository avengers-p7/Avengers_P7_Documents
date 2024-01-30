# CI Concepts
| Author | Created On | Last Updated | Document Version | Last Updated By |
| ------ | ---------- | ------------ | ---------------- | --------------- |
| Shantanu | 23-01-2024 | 26-01-2024   |         v1     |     Shantanu    |
***

# Table of Content
[1. Introduction](#introduction)

[2. Key Components](#key-components)

[3. Workflow](#workflow)

[4. Benefits](#benefits)

[5. Best Practices](#best-practices)

[6. Conclusion](#conclusion)

# Introduction
Continuous Integration is a software development practice where code changes are automatically integrated and tested frequently. Developers submit their code changes to a shared repository, triggering an automated build and test process. This ensures that the codebase is always in a functional state. Continuous Integration addresses challenges in software development by automating the integration of code changes from multiple contributors. It aims to detect and fix integration issues early in the development process, promoting collaboration and delivering more reliable software.
***

# Key Components
| Components | Description | Tools |
| ---- | ------------- | -------------|
| Version Control System | Manages code changes, tracks revisions, and facilitates collaboration among developers.| Git, SVN, Mercurial |
| Build Server | Automates the compilation and packaging of code changes, ensuring consistency in the build process.	| Jenkins, Travis CI, CircleCI |
| Automated Testing	 | Includes unit, integration, and functional tests to verify the correctness of code changes.	| JUnit, NUnit, pytest, Selenium |
| Deployment Pipeline	| Defines the automated steps involved in building, testing, and deploying code changes.	| GitLab CI/CD, Azure Pipelines, GitHub Actions |
| Notification System	| Alerts developers about build and test results, providing immediate feedback on the status of changes.	| Email notifications, Slack integration, Teams |
***

# Workflow
Workflow in context of CI refers to the series of automated steps and processes that code changes go through from development to deployment. It defines the sequence of tasks that are executed when changes are made to the version-controlled codebase. Workflow is further divides into two parts pre-build and post-build.

### Pre-Build
The pre-build phase in Continuous Integration (CI) is a crucial step designed to ensure the integrity, security, and efficiency of the software development process. By conducting various analyses and checks before the actual compilation and build of the code, the pre-build phase aims to detect and address potential issues at an early stage. Early issue detection is fundamental in minimizing the cost and effort associated with bug fixing and enhancing the overall code quality. Through processes such as static analysis, credential scanning, and dependency checking, developers can identify errors, security vulnerabilities, and compliance issues before they propagate to subsequent stages of the CI/CD pipeline. The pre-build phase is crucial for identifying and addressing issues early in the development cycle. Key activities in the pre-build phase include:

| CI Phase            | Process Description                                                                                            |
|---------------------|---------------------------------------------------------------------------------------------------------------|
| Code Compilation    | Translating source code into machine-readable form, ensuring syntactic correctness, and generating artifacts for testing and deployment. Early detection of errors and maintaining a consistent and executable codebase. |
| Credential Scanning | Identifying and mitigating security risks by searching for sensitive information (e.g., passwords, API keys) within the source code and build configurations. Proactively addressing credential-related vulnerabilities before build and deployment. |
| Dependency Scanning | Analyzing project dependencies to identify known vulnerabilities or security issues in third-party libraries/components. Ensuring a secure and up-to-date foundation for software development. |
| License Analysis    | Examining project dependencies to identify and manage software licenses. Ensuring compliance with licensing requirements and avoiding legal issues associated with third-party libraries. |
| Static Analysis      | Examining source code without execution to detect issues like code quality, security vulnerabilities, or adherence to coding standards. Proactive identification and resolution of problems in the development phase. |
| Code Coverage        | Measuring the proportion of code exercised by automated tests in the pre-build phase. Providing insights into test suite effectiveness by identifying areas not covered and ensuring comprehensive testing. |

![Screenshot 2024-01-25 at 9 20 17 PM](https://github.com/avengers-p7/Documentation/assets/156056364/c64fa417-0dc7-40bc-a5b4-69abfaf25d32)

### Build
The build phase, as a whole, aims to provide developers with timely feedback on code quality, security, and functionality, facilitating the continuous and reliable delivery of software updates. The primary objectives of the build phase in CI are as follows:

| Build Phase Activity    | Description                                                                                                      |
|-------------------------|------------------------------------------------------------------------------------------------------------------|
| Dependency Resolution   | Necessary dependencies, libraries, and external components are fetched and integrated into the build to provide the software with access to required resources during execution.       |
| Artifact Generation     | The output of the build process, known as artifacts, includes compiled binaries, libraries, configuration files, and other essential components needed to run the application. These artifacts are utilized in subsequent stages of the CI/CD pipeline. |
| Unit Testing            | Some CI systems include unit testing as part of the build process to assess the functionality of individual units or components of the code. Successful unit tests indicate that each part of the code behaves as expected.  |
| Code Quality Checks     | Static code analysis tools are used to assess code quality, checking for adherence to coding standards, identifying potential issues, and ensuring consistent code style. |


### Post-Build
The post-build phase in Continuous Integration (CI) is vital for ensuring the completeness and reliability of the software after the compilation and build process. This phase involves executing various activities, such as running automated tests, generating deployable artifacts, and performing additional validations. The primary objective is to verify that the compiled code functions as expected, meets quality standards, and is ready for deployment. Post-build processes also facilitate the identification of integration issues, ensuring that the individual components work seamlessly together. Additionally, tasks like creating documentation, packaging the application, and preparing for deployment are typically handled in the post-build phase. By thoroughly validating the build outputs, the post-build phase ensures that the software is in a deployable state, providing confidence in the reliability and functionality of the application before it moves on to the deployment stage. Key activities in the post-build phase include:

| Test Type                           | Description                                                                                                      |
|-------------------------------------|------------------------------------------------------------------------------------------------------------------|
| Health Check Validation             | Verifying the operational health of the deployed application by running checks to ensure key components function correctly. Ensures a stable state before and after deployment, reducing end-user impact. |
| Sanity Test                         | Involves running a subset of tests in the post-build phase to quickly verify essential functionalities, ensuring major components work as expected. A quick check before more comprehensive testing or deployment. |
| Functional Test                     | Comprehensive testing in the post-build phase assessing the application's functionalities to ensure they meet specified requirements. Verifies software behavior related to functionality, user interactions, and business logic. |
| Integration Test                    | Testing interactions and interfaces between different components or modules to ensure seamless collaboration. Validates integration points, identifying and resolving issues related to the system's various parts. |
| Dynamic Application Security Testing | In the post-build phase, it involves analyzing a running application for security vulnerabilities, such as input validation errors or misconfigurations. DAST evaluates security in a dynamic state, simulating real-world attacks and providing insights into potential risks. |

![Screenshot 2024-01-25 at 9 40 36 PM](https://github.com/avengers-p7/Documentation/assets/156056364/c9e0450e-c36e-4cc2-ba5a-a9c617c0efa7)
***

# Benefits
| **Description**            |     **Benefits**                                 |
| ---------------------------------------------------- | --------------------------------------------------- |
| **Early Detection of Issues**                       | - Identification of integration issues and bugs early in the development process.<br>- Quick resolution of problems leading to improved code quality. |
| **Consistent Builds**                               | - Automated processes ensure consistent code builds across different environments.<br>- Reduces errors caused by variations in developer machines or deployment settings. |
| **Rapid Feedback**                                   | - Developers receive prompt feedback on the status of their code changes.<br>- Accelerates the development cycle by addressing issues quickly. |
| **Reduced Integration Risks**                       | - Frequent, smaller integrations minimize the risk of large-scale integration problems.<br>- Easier management and resolution of conflicts. |
| **Automated Testing**                                | - Encourages the use of automated testing (unit, integration, etc.) for code validation.<br>- Ensures code changes do not introduce new bugs and maintains existing functionality. |
| **Enhanced Collaboration**                           | - CI fosters collaboration by providing a shared, continuously updated codebase.<br>- Developers work on smaller, manageable changes with confidence. |
| **Faster Release Cycles**                            | - Streamlines development and deployment pipelines, enabling faster and more frequent releases.<br>- Accelerates the delivery of new features and updates to users. |
| **Improved Code Quality**                            | - Enforces coding standards and identifies code smells through automated code analysis.<br>- Reduces the likelihood of introducing defects. |
| **Efficient Debugging**                             | - Enables the identification of specific commits that introduce problems for efficient debugging.<br>- Enhances traceability and diagnosis of issues. |
| **Increased Confidence in Releases**                | - Ensures that code changes undergo automated testing before deployment.<br>- Boosts confidence in the stability and reliability of software releases. |
| **Facilitates Continuous Deployment**               | - CI serves as a foundational practice for organizations moving towards continuous deployment.<br>- Automates the deployment process after successful testing and validation. |
***

# Best Practices
| Best Practice                     | Effect                                        | Examples of Implementation                                    |
| ---------------------------------- | --------------------------------------------- | ------------------------------------------------------------ |
| Keep Builds Fast                   | Enables quick feedback for developers         | Optimize build scripts and dependencies to minimize build times. |
| Run Tests in Isolation             | Identifies and isolates issues efficiently    | Utilize containers (e.g., Docker) to isolate tests and dependencies. |
| Implement Version Control          | Facilitates collaboration and tracks changes  | Use Git for version control and enforce branching strategies.  |
| Monitor and Analyze                | Provides insights for continuous improvement | Implement monitoring tools like Prometheus, Grafana, or New Relic. |
| Parallelize Test Execution          | Accelerates testing by running tests concurrently | Divide test suites and run tests in parallel using CI/CD platforms. |
| Version Build Artifacts            | Enables traceability and rollback if needed   | Tag releases in version control and use build numbers for artifacts. |
| Use Immutable Infrastructure        | Ensures consistency and reproducibility       | Deploy applications using container orchestration tools (e.g., Kubernetes). |
| Implement Pull Requests            | Facilitates code review and collaboration     | Use a pull request workflow, such as GitHub Pull Requests or Bitbucket. |

***

# Conclusion

Continuous Integration (CI) serves as a vital practice in software development, fostering collaboration, early issue detection, and reliable code deployment. Embracing CI principles ensures that our code evolves seamlessly, allowing teams to deliver high-quality software with efficiency and confidence. It's a key ingredient in the recipe for successful software development, emphasizing consistency and collaboration throughout the coding journey.
***

# Contact Information
| Name | Email Address |
| ---- | ------------- |
| Shantanu  | shantanu.chauhan.snaatak@mygurukulam.co |

# References
| Source | Description  | 
| -------- | ------- | 
| [https://docs.github.com/en/authentication)https://docs.github.com/en/authentication](https://katalon.com/resources-center/blog/ci-cd-tools)https://katalon.com/resources-center/blog/ci-cd-tools | Key Components |
| https://semaphoreci.com/continuous-integration#:~:text=CI%20and%20CD%20are%20often,unit%20in%20the%20delivery%20process. | Workflow |
| https://katalon.com/resources-center/blog/benefits-continuous-integration-delivery | Benefits |
| https://www.cloudbees.com/continuous-delivery/continuous-integration-best-practices | Best Practices |
