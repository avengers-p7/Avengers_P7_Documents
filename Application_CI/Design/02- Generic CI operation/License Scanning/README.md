# License Scanning


***
## Table Of Contents 
+ [Introduction](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/Credential%20Scanning.md#introduction)
+ [Why License Scanning](#why-license-scanning-)
+ [Tool Comparison](#tool-comparison)
+ [Tool Recommendation](#tool-recommendation)
+ [Proof Of Concept : FOSSA](#proof-of-concept--fossa)
+ [Advantages](#advantages)
+ [Best Practices](#best-practices)  
+ [Conclusion](#conclusion)
+ [Contact Information](#contact-information)
+ [References](#references)

***
## Introduction 
License scanning refers to the process of automatically analyzing and identifying software licenses associated with code or components within a software project.

## Why License Scanning ?
License scanning is important for several reasons in the context of software development and usage:

| **Requirement** | **Description** |
| -------------------- | --------------- |
| **Legal Compliance** | Ensuring that the software complies with the terms and conditions of relevant licenses is essential for legal reasons. 
| **Open Source Software (OSS) Management** | Many software projects incorporate open-source components, each governed by specific licenses. License scanning helps organizations identify and manage the licenses associated with these components, ensuring compliance with open-source license requirements. |
| **Risk Mitigation** | License scanning helps identify potential legal risks associated with the use of specific licenses. It allows organizations to assess and understand the implications of incorporating certain software components into their projects. |
| **Intellectual Property Protection** | License scanning helps protect intellectual property by ensuring that the organization is using software components in a manner consistent with the terms defined by the licenses. |
| **Security and Quality Assurance** | By scanning licenses, organizations can also assess the security and quality of the software components. This includes evaluating the reputation of the open-source projects, checking for known vulnerabilities, and ensuring that the software is well-maintained. |

## License Scanning Tools 
Credential scanning tools are used to identify and prevent the exposure of sensitive information, such as usernames, passwords, API keys, and other credentials, within source code, configuration files, or other repositories. Here are some popular credential scanning tools:

| **Tool** | **Description** |
| -------- | --------------- |
| **TruffleHog** | TruffleHog is a Python-based tool that scans Git repositories for high-severity security issues, including potential exposure of credentials. |
| **GitLeaks** | GitLeaks is an open-source tool designed to search through Git repositories for secrets and sensitive information. It supports various file types and allows you to customize the rules for finding credentials. |
| **RepoPeek** | RepoPeek is a lightweight Python tool that scans repositories on GitHub, GitLab, and Bitbucket to find sensitive information, including credentials, API keys, and more. |
| **GitGuardian** | GitGuardian is a commercial tool that specializes in scanning for sensitive data, secrets, and credentials in both public and private repositories. It supports various version control systems and integrates with CI/CD pipelines. |
| **Spectre** | Spectre is an open-source secrets scanner that supports various file types and can be integrated into CI/CD pipelines. It is designed to find secrets such as passwords, API keys, and other sensitive information. |
| **Hawkeye** | Hawkeye is a security tool that scans for secrets, API keys, and other sensitive information in source code repositories. It supports multiple file formats and can be integrated into CI workflows. |
| **Detect-Secrets** | *detect-secrets* is an open-source Python tool that scans code repositories, using regex-based patterns to identify and prevent the accidental inclusion of sensitive information like passwords or API keys. It's easily integrated into CI/CD pipelines and supports customizable configuration for reduced false positives. |

***

## Tool Comparison
| Feature / Aspect      | FOSSA                                  | Black Duck                                | FOSSology                                  |
|-----------------------|----------------------------------------|-------------------------------------------|--------------------------------------------|
| **License Detection** | Comprehensive license detection across multiple languages and package managers. | Extensive license detection capabilities supporting various languages and package managers. | Focus on analyzing licenses and copyright information in source code.                   |
| **Vulnerability Scanning** | Provides vulnerability scanning for open-source dependencies. | Offers robust security scanning capabilities, identifying vulnerabilities in open-source components. | Primarily focuses on license analysis but may lack advanced security scanning features.     |
| **Integration**        | Integrates with various development and CI/CD tools, supporting multiple workflows. | Integrates with popular DevOps tools and CI/CD pipelines for seamless integration. | Integrates with various systems and supports custom integration through APIs.                  |
| **Ease of Use**        | User-friendly interface with a focus on ease of navigation and understanding. | Generally user-friendly, with a range of features accessible through a web-based interface. | May have a steeper learning curve and a more technical interface for some users.               |
| **Community Support**  | Active community support and regular updates to the platform. | Strong community support, backed by a well-established company (Synopsys). | Open-source project with community contributions, but may have less extensive support.          |
| **Scalability**        | Scalable to handle projects of various sizes and complexities. | Scalable for enterprise-level projects with extensive codebases and dependencies. | Suitable for smaller to mid-sized projects; scalability may vary based on requirements.         |
| **Customization**      | Provides customization options and flexibility in reporting and policies. | Offers customization options for policies, reporting, and integration with existing tools. | Being open source, it allows customization but may require more technical expertise.              |
| **Cost (Free Elements)** | FOSSA offers a free version with limited features, and pricing is based on project size and complexity for additional features. | Black Duck may have free trials, but it is primarily a commercial product with pricing based on project size and organization requirements. | FOSSology is open-source, and the software itself is free. Costs may be associated with support and customization services. |                           |
***
## Tool Recommendation

**FOSSA** has several features that give it an edge over other license scanning tools. Here are few key points that highlight its advantages:

| **FOSSA Feature** | **Description** |
| -------------------- | --------------- |
| Comprehensive Multi-Language Support | FOSSA is recognized for its comprehensive license detection capabilities across a wide range of programming languages and package managers. This multi-language support is crucial for organizations with diverse tech stacks, allowing them to accurately identify and manage licenses in projects with mixed language dependencies. |
| Advanced Vulnerability Scanning | FOSSA goes beyond license analysis and includes robust vulnerability scanning for open-source dependencies. This feature enhances the tool's utility by providing insights into potential security risks associated with the components used in a software project. This dual focus on licenses and security makes FOSSA a more comprehensive solution for managing open-source components. |
| User-Friendly Interface and Workflow Integration | FOSSA offers a user-friendly interface, designed to facilitate ease of navigation and understanding. This aspect can contribute to faster adoption by development teams. Additionally, FOSSA integrates seamlessly with various development and CI/CD tools, making it easier to incorporate license scanning into existing workflows without causing disruptions. |
| Continuous Monitoring |  FOSSA supports continuous monitoring, allowing organizations to stay informed about changes in licenses as their projects evolve over time. |

***

## Proof Of Concept : FOSSA

*Please refer the [FOSSA License Scanning POC](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/02-%20Generic%20CI%20operation/License%20Scanning/License%20Scanning%20via%20FOSSA%20POC.md) for FOSSA setup process and proof of concept of license scanning using FOSSA.*

***
## Advantages 

| **Advantages of Credential Scanning Tools**                   |    **Description**                                   |
|-------------------------------------------------------------|---------------------------------------|
| **Security Improvement:** |  Prevent exposure of sensitive credentials in repositories & reduce attack surface and unauthorized access | 
| **Compliance and Regulatory Compliance:** | Ensure adherence to security standards and regulations & address industry-specific and regional compliance |
| **Early Detection of Vulnerabilities:** | Integrate with CI/CD for early detection in development & reduces time to remediate and mitigate vulnerabilities |      
| **Cost Savings:** | Prevent financial and reputational costs of security incidents & minimizes remediation costs through early detection |                        
| **Maintaining Trust:** | Build customer and user trust through commitment to security as we avoid fallout from data breaches |
***

## Best Practices 
Here are some best practices for effective credential scanning:

| **Best Practice**                   |    **Description**                                   |
|-------------------------------------------------------------|---------------------------------------|
| Regular Scanning | Implement regular and automated credential scanning across all code repositories, configuration files, and other relevant assets. |
| Integration with CI/CD Pipelines | Integrate credential scanning into your continuous integration/continuous deployment (CI/CD) pipelines. |
| Pattern-Based Scanning | Use pattern-based scanning tools that can recognize common formats of credentials, such as API keys, passwords, and access tokens. Customize these patterns to match your organization's specific credential formats. |
| Exclude Trusted Files and Paths | Define exclusion rules for trusted files and paths where credentials might be legitimately stored. This prevents unnecessary alerts and false positives, focusing the scan on areas of higher risk. |
| Secure Credential Storage | Encourage the use of secure credential storage solutions, such as vaults or key management services, rather than storing sensitive information directly in code or configuration files. |
| Audit Trails | Maintain audit trails for credential scanning activities. Keep records of scan results, actions taken, and any identified vulnerabilities. This information can be valuable for compliance purposes and continuous improvement. |
| Regular Updates |Keep your credential scanning tools and patterns up to date. Regularly update the tools to benefit from the latest security enhancements and ensure compatibility with evolving development practices. |

By implementing these best practices, organizations can significantly reduce the risk of credential leaks and enhance the overall security of their software development lifecycle.

***
## Conclusion  
In conclusion, credential scanning emerges as a fundamental practice in modern cybersecurity, offering a proactive approach to identifying and mitigating potential vulnerabilities within code repositories and configurations. By systematically searching for sensitive information like passwords and API keys, this practice serves as a critical line of defense against unauthorized access and data breaches. Integrated into the development lifecycle and bolstered by automated tools, credential scanning not only safeguards the integrity of systems but also fortifies organizations against evolving threats in the digital realm. In prioritizing the protection of sensitive data, credential scanning underscores its indispensable role in fostering a resilient and secure environment for software development and IT operations.

# Contact Information

| Name                 | Contact Information                                                                                     
|---------------------------------|------------------------------------------------------------|
| Aakash Tripathi                 |  aakash.tripathi.snaatak@mygurukulam.co
***
# References

|     Description                  | References  
| ---------------------------------| ------------------------------------------------------------------- |
| Credential Scanning | https://microsoft.github.io/code-with-engineering-playbook/continuous-integration/dev-sec-ops/secret-management/credential_scanning/ |
| GitLeaks |  https://akashchandwani.medium.com/what-is-gitleaks-and-how-to-use-it-a05f2fb5b034 | 
| detect-secrets | https://microsoft.github.io/code-with-engineering-playbook/continuous-integration/dev-sec-ops/secret-management/recipes/detect-secrets/ |


