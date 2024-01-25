# CI Concepts
| Author | Created On | Last Updated | Document Version | Last Updated By |
| ------ | ---------- | ------------ | ---------------- | --------------- |
| Shantanu | 23-01-2024 | 26-01-2024   |         v1     |     Shantanu    |
***

# Table of Content
1. Introduction
2. Key Components
3. Workflow
4. Benefits
5. Best Practices
6. Conclusion

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
This phase involves several preparatory steps and checks to ensure that the codebase is in a suitable state for the build process. The pre-build phase is crucial for identifying and addressing issues early in the development cycle. Key activities in the pre-build phase include:

* **Code Compilation:** Code compilation in the pre-build phase of CI involves translating source code into machine-readable form, ensuring syntactic correctness and generating artifacts essential for subsequent testing and deployment processes. This step is crucial for early detection of errors and maintaining a consistent and executable codebase.

* **Credential Scanning:** Identifying and mitigating potential security risks by searching for sensitive information, such as passwords or API keys, within the source code and build configurations to prevent unintentional exposure. This process aims to enhance security by proactively addressing credential-related vulnerabilities before the actual build and deployment.

* **Depemdency Scanning:** Analyzing the project's dependencies and identifying any known vulnerabilities or security issues in third-party libraries or components. This process helps ensure that the software is built on a foundation of secure and up-to-date dependencies.

* **License Analysis:** Examining the project's dependencies to identify and manage software licenses associated with third-party libraries, ensuring compliance with licensing requirements and avoiding legal issues. This process aids in maintaining a clear understanding of the licenses governing the use of software components.

* **Static Analysis:** Examining the source code without executing it to detect potential issues such as code quality, security vulnerabilities, or adherence to coding standards. This proactive analysis helps identify and address problems early in the development process.

* **Code Coverage:** Code coverage in the pre-build phase of CI measures the proportion of code that automated tests exercise, providing insights into the effectiveness of test suites by identifying areas not covered. This analysis helps ensure comprehensive testing and higher confidence in the codebase's reliability.

![Screenshot 2024-01-25 at 9 20 17 PM](https://github.com/avengers-p7/Documentation/assets/156056364/c64fa417-0dc7-40bc-a5b4-69abfaf25d32)

### Post-Build
The compiled code is subjected to additional automated tests, deployment to staging and production environments, and monitoring to ensure successful integration and readiness for release. This phase focuses on validating the build's integrity and preparing it for deployment. Key activities in the post-build phase include:

* **Health Check Validation:**  It involves verifying the operational health of the deployed application by running checks to ensure key components are functioning correctly. It helps ensure that the application is in a stable state before and after deployment, reducing the risk of issues impacting end-users.

* **Sanity Test:** Sanity test  in the post-build phase of CI involves running a subset of tests that cover essential functionalities to quickly verify that major components of the software work as expected. It ensures that basic functionality is intact after changes and is often used as a quick check before more comprehensive testing or deployment.

* **Functional Test:** Functional test  in the post-build phase of CI involves executing a comprehensive set of tests that assess the application's functionalities to ensure they meet the specified requirements. It verifies that the software behaves as intended, detecting issues related to functionality, user interactions, and business logic.

* **Integration Test:** It involves testing the interactions and interfaces between different components or modules to ensure they work together seamlessly. It validates the integration points of the software, identifying and resolving issues related to the collaboration between various parts of the system.

* **Dynamic Application Security Testing:** Dynamic Application Security Testing (DAST) in the post-build phase of CI involves analyzing a running application for security vulnerabilities, such as input validation errors or misconfigurations. DAST evaluates the security of the application in its dynamic state, simulating real-world attacks and providing insights into potential security risks.

![Screenshot 2024-01-25 at 9 40 36 PM](https://github.com/avengers-p7/Documentation/assets/156056364/c9e0450e-c36e-4cc2-ba5a-a9c617c0efa7)
***

# Benefits
| **Description**            |     **Benefits**                                 |
| ---------------------------------------------------- | --------------------------------------------------- |
| **Early Detection of Issues**                       | -Identification of integration issues and bugs early in the development process.<br>- Quick resolution of problems leading to improved code quality. |
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
| **Best Practice for CI**                               | **Effect on CI**                                                   |
| ------------------------------------------------------ | ------------------------------------------------------------------- |
| **Automate Everything**                              | -Reduces manual errors<br>- Streamlines processes for efficiency   |
| **Keep Builds Fast**                                 | Enables quick feedback for developers                               |
| **Run Tests in Isolation**                           | Identifies and isolates issues efficiently                           |
| **Maintain a Single Source of Truth**               |  Ensures consistency and avoids versioning conflicts                |
| **Implement Version Control**                       | Facilitates collaboration and tracks changes effectively           |
| **Monitor and Analyze**                              | Provides insights for continuous improvement                        |
| **Parallelize Test Execution**                       | Accelerates testing by running tests concurrently                    |
| **Practice Continuous Integration, Not Just CI**    | Emphasizes frequent and small integrations for stability            |
| **Version Build Artifacts**                          | Enables traceability and rollback to specific versions if needed     |
| **Use Immutable Infrastructure**                   | Ensures consistency and reproducibility in deployment environments   |
| **Implement Pull Requests**                         | Facilitates code review and collaboration before integration        |
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
