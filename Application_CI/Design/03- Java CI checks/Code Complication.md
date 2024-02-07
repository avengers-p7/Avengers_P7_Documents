# Documentation of Code Compilation of Java 

|Author  | Created on |version | last updated on|
|--------|------------|---------|----------------|
|Nidhi Bhardwaj | 23-01-2024  | V1 | 23-01-2024 |

***
# Table of Content

1.  [Introduction](#introduction)
2.  [What is Java CI Code Compilation ](#What-is-java-CI-Code-Compilation)
3.  [Java Tools](#java-tools)
4.  [Tool Comparison](#comparison)
5.  [Best Practices](#best-practices)
6.  [Proof of concepts (POC)](#proof-of-concepts-(POC))
7.  [conclusion](#conclusion)
8.  [Contact Information](#contact-information)
9.  [References](#references)

***

# Introduction 

Java CI code compilation in the context of checking in code. Continuous Integration (CI) is a development practice that emphasizes frequent integration of code changes and automated testing. 

**Definition**: Continuous Integration is a development practice where developers frequently integrate their code changes into a shared repository. Each integration triggers automated processes such as builds, tests, and validations.

**Objective**: To detect and address integration issues early in development, ensuring a consistent and reliable codebase.

***

# What is Java CI Code Compilation

**Java CI (Continuous Integration)**:

CI refers to the practice of the development process of continuously integrating code changes from multiple contributors into a shared repository. CI systems automate the process of building, testing, and validating code changes. Common CI tools for Java include Jenkins, Travis CI, GitLab CI, and others.

**Code Compilation**

Code compilation is converting human-readable source code into machine-readable code or bytecode that can be executed by a computer. In Java, this typically involves using a compiler (e.g., javac) to convert .java source files into .class files

***

# Different Tools for Java compilation

In the Java ecosystem, there are several tools commonly used for compiling Java code. Here are some of the prominent ones

**1.Java Compiler (Javac)**: The standard Java Compiler provided with the Java Development Kit (JDK). It is a command-line tool for compiling Java source code files (.java) into bytecode (.class) files.

**Example** 

![image](https://github.com/avengers-p7/Documentation/assets/156644891/4933dad8-393e-4ce2-b1c9-2c1cb4b33a8c)

**2. Apache Maven**: A popular build automation and project management tool that can be used for compiling, testing, and packaging Java projects. Maven uses a declarative XML file (pom.xml) to manage project configurations.

**Example** 

![image](https://github.com/avengers-p7/Documentation/assets/156644891/e7accbf5-8639-4a4e-bade-878209823306)

**3. Gradle**: Another build automation tool for Java that uses a Groovy-based DSL (Domain-Specific Language) or Kotlin for project configuration. It's designed to be flexible and supports incremental builds.

**Example**

![image](https://github.com/avengers-p7/Documentation/assets/156644891/8050e5c2-2fd8-48f3-8ead-ce76e26cb619)

**4. Ant**: A build tool similar to Maven but using XML-based configuration. It is an older tool that is still used in some projects.

**Example**

![image](https://github.com/avengers-p7/Documentation/assets/156644891/09f1e5d2-c169-4ac5-b09b-896669275960)

**Eclipse Compiler for Java** (ECJ): The Eclipse Foundation provides a Java compiler that is embedded in the Eclipse IDE. It can also be used as a standalone compiler.

**Example**

![image](https://github.com/avengers-p7/Documentation/assets/156644891/38423f34-56ae-4279-8b1d-68a7cb52ec33)


**6. IntelliJ IDEA Compiler**: If you're using IntelliJ IDEA as your integrated development environment, it has its own built-in compiler for Java.

Compiling is typically triggered automatically when you build or run your project within the IDE.

***

# Comparison

Here's a comparison table of some key features and characteristics of the mentioned Java CI/Build tools:

| Feature | javac | Apache Maven | Gradle | Apache Ant|
|----------|-------|--------------|--------|-----------|
| Build File Format | java files | pom.xml (XML) | build.gradle (Groovy or Kotlin DSL) | build.xml (XML) |
| Dependency Management | Manual (Classpath) | Yes (Central Repository) | Yes (Central Repository) | Yes (Central Repository) | Manual (Libraries) |
| Plugins and Extensions | Limited | Abundant | Extensible | Abundant |
| Convention over Configuration | NO | yes| yes| NO |
| Build Lifecycle Phases |	Compile	| clean, compile, test, package, install, deploy, etc. |	build, clean, test, assemble, etc | 	compile, clean, test, jar, etc |
| Build Profiles | No |	Yes |	Yes	| Yes |
| Community Support | 	N/A |	Active | Active	 | Moderate |

***
# Advantages

| Advantage | javac	| Apache Maven |	Gradle	| Apache Ant |
|------------|------|--------------|-----------|------------|
| Ease of Use	| Simple and lightweight | Easy configuration with conventions |	Concise syntax with Groovy or Kotlin DSL	 | Flexible, but XML configuration can be verbose |
|Dependency Management	| Manual	| Centralized dependency management (Central Repository)	| Powerful dependency management	| Manual, requires managing libraries manually | 
| Build Lifecycle	| Basic compile functionality |	Clearly defined lifecycle phases	| Highly customizable build lifecycle	 | Customizable build lifecycle |
|Convention over Configuration	| No |	Yes, follows conventions (standard project structure)	| Yes, supports convention-based development	| No |
|Plugins and Extensions	|  Limited |	Rich ecosystem of plugins | 	Extensive plugin system	| Various plugins available |
| Incremental Builds	| No	| Yes, supports incremental builds |	Yes, incremental builds for improved performance	| No |
| Integrations with IDEs	| Integrated	| Integration available (e.g., Eclipse, IntelliJ IDEA)	| Integration available (e.g., IntelliJ IDEA)	| Integration available (e.g., Eclipse)|
| Community Support | 	N/A	 |Active community support	| Active community support |	Moderate community support |

***

# Best Practices 

Continuous Integration (CI) specifically for Java code compilation, there are several best practices that can help streamline the process and ensure code quality. Here are some recommendations:

|Name | Description  |
|------|----- |
|Use a Build Tool  | Employ a robust build tool such as Maven or Gradle for managing dependencies and compiling Java code.Define project configurations and dependencies in a build file (pom.xml for Maven, build.gradle for Gradle) |
| Build Isolation| Ensure that each CI build is isolated to prevent interference from other builds. Avoid shared resources to prevent conflicts and ensure reproducibility.|
| Automate Compilation |Automate the compilation process to catch syntax errors and ensure code consistency. Include compilation as a step in your CI pipeline.|
|Dependency Management|Clearly specify and manage dependencies in your build tool configuration.Regularly update dependencies to the latest versions to benefit from bug fixes and improvements.|
|JDK Version Compatibility |Specify the target JDK version in your build configuration to ensure compatibility. Consider testing code with different JDK versions, especially if your application needs to support multiple versions.|
|Parallel Compilation |Leverage the parallel compilation feature of your build tool to speed up the build process. Configure the number of threads for compilation based on your build server's capabilities |
|Incremental Builds |Use incremental builds to only compile the files that have changed since the last build. This can significantly reduce build times, especially for larger projects. |
|Static Code Analysis |Integrate static code analysis tools (e.g., FindBugs, Checkstyle, PMD) into your build process. Enforce coding standards and identify potential issues early in development.|
|Code Quality Metrics |Integrate tools like SonarQube to measure and monitor code quality metrics. Set up quality gates to enforce code quality standards.|
|Automated Testing | Include unit tests in your build process to verify the correctness of your code. Integrate automated tests to run after successful compilation |
|Continuous Inspection |Regularly inspect the build artifacts and ensure they conform to coding standards.Consider using tools like JDepend to analyze package dependencies.|
|Artifact Management |Publish build artifacts to a repository manager (e.g., Nexus, Artifactory) for versioning and reuse. Cache dependencies to speed up subsequent builds.|
|Documentation |Include documentation in your project to explain the build process, dependencies, and any specific compilation considerations. Keep documentation up-to-date to help new contributors understand the build setup.|
| Versioning and Tagging | Tag releases with version numbers to ensure traceability. Use versioning consistently across your project and in build configurations.|
| Error Handling and Logging | Implement robust error handling in your build script to catch and report errors. Ensure that the build logs provide sufficient information for debugging |


***

# Proof of concepts (POC)


here's a simple proof of concept for a Maven-based Java CI pipeline using Jenkins

# Step 1: clone github project

```shell
git  clone https://github.com/opstree/spring3hibernate/tree/master
```

**pom.xml**

![image](https://github.com/avengers-p7/Documentation/assets/156056444/9de05880-ce7d-4ab8-a1b8-974adbacfdee)

> [!NOTE]
> Change maven compiler version from 1.6 to 7 

![image](https://github.com/avengers-p7/Documentation/assets/156056444/8a9710fb-856d-472b-b513-a80f756227dd)



# Step 3: Run mvn compile

```shell
mvn compile
```
![image](https://github.com/avengers-p7/Documentation/assets/156056444/e4ee38c5-fcdb-472e-8a1f-17b25aae4adc)

![image](https://github.com/avengers-p7/Documentation/assets/156056444/546a6af3-0836-42c2-aed4-e22feec845ec)

![image](https://github.com/avengers-p7/Documentation/assets/156056444/2358944e-d4c0-4a41-a493-3d3bf9ddf4d8)







# Conclusion

In conclusion, the code compilation process in Java involves translating source code into bytecode, which can be executed by the Java Virtual Machine (JVM). During compilation, the Java compiler (javac) checks the syntax and semantics of the code, identifying any errors or inconsistencies. If the code compiles successfully, it produces bytecode files (.class) containing instructions for the JVM. This bytecode is platform-independent, allowing Java programs to run on any device with a compatible JVM installed. Additionally, the compilation process may involve optimizing the generated bytecode for performance. Overall, code compilation is a crucial step in the software development lifecycle, ensuring that Java programs are translated into executable format efficiently and accurately.

***

# Contact Information 

|Name | Email ID |
|------|---------|
|Nidhi Bhardwaj | nidhi.bhardwaj.snaatak@mygurukulam.co |

***

# References 

|Link | Description |
|-----|--------------|
| https://www.toptal.com/java/java-continuous-integration-setup-tutorial | Documentation |












