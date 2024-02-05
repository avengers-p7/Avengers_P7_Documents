# Documentation of Code Compliation

|Author  | Created on |version | last updated on|
|--------|------------|---------|----------------|
|Nidhi Bhardwaj | 23-01-2024  | V1 | 23-01-2024 |

***
# Table of Content

1.  Introduction
2.  What
3.  Different Tools of java compilation
4.  Comparison
5.  Best Practices
6.  Proof of concepts (POC)
7.  conclusion
8.  Contact Information
9.  References

***

# Introduction 

Java CI code compilation in the context of checking in code. Continuous Integration (CI) is a development practice that emphasizes frequent integration of code changes and automated testing. 

**Definition**: Continuous Integration is a development practice where developers frequently integrate their code changes into a shared repository. Each integration triggers automated processes such as builds, tests, and validations.

**Objective**: To detect and address integration issues early in the development process, ensuring a consistent and reliable codebase.

***

# What is java ci code compilation

***Java CI (Continuous Integration)**:

CI refers to the practice of continuously integrating code changes from multiple contributors into a shared repository. CI systems automate the process of building, testing, and validating code changes. Common CI tools for Java include Jenkins, Travis CI, GitLab CI, and others.

***Code Compilation**

Code compilation is the process of converting human-readable source code into machine-readable code or bytecode that can be executed by a computer. In Java, this typically involves using a compiler (e.g., javac) to convert .java source files into .class files

***

# Different Tools of java compilation

In the Java ecosystem, there are several tools commonly used for compiling Java code. Here are some of the prominent ones

**1.Java Compiler (javac)**: The standard Java Compiler provided with the Java Development Kit (JDK). It is a command-line tool for compiling Java source code files (.java) into bytecode (.class) files.

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


# Step 1: Create a Simple Java Project with Maven

1. Create a basic Maven project with a simple Java class and a unit test. Here's a simple structure
   
   ![image](https://github.com/avengers-p7/Documentation/assets/156644891/a944e7a8-27a8-49bb-a0be-6d9f44b015e0)

**MyApp.java**

![image](https://github.com/avengers-p7/Documentation/assets/156644891/d56e8f1c-6ac4-45a0-89ed-064727f68673)



![image](https://github.com/avengers-p7/Documentation/assets/156644891/15f2faad-fc1e-450d-9cf7-63f5fe4f249a)


**MyAppTest.java**


![image](https://github.com/avengers-p7/Documentation/assets/156644891/8cddd856-c015-4e6f-8ad8-6a7bb1e73581)


**pom.xml**


![image](https://github.com/avengers-p7/Documentation/assets/156644891/8ca998cd-f7c6-4b8d-9b4e-683899b01519)



# Step 2: Set Up a GitHub Repository


Create a GitHub repository and push the Maven Java project to it.



![image](https://github.com/avengers-p7/Documentation/assets/156644891/97ec5532-be96-48c1-bf7b-633d3f9ff4cd)



# Step 3: Install Jenkins and Maven


Install Jenkins and Maven on your server. Follow the official installation guides for Jenkins and Maven.


![image](https://github.com/avengers-p7/Documentation/assets/156644891/e99acfef-d1ff-4b8e-9b2a-fc9ba4c8e79e)




# Step 4: Configure Jenkins


1.  Install the necessary plugins in Jenkins:

    GitHub plugin

    Maven Integration plugin

    ![image](https://github.com/avengers-p7/Documentation/assets/156644891/368154b9-6c51-4e58-86f6-02fdb851aad3)



     ![image](https://github.com/avengers-p7/Documentation/assets/156644891/6564dba4-4b0b-47fe-971a-790944a76f5d)



3. Configure the JDK and Maven in Jenkins:

    Go to "Manage Jenkins" > "Global Tool Configuration."

    Add JDK and Maven installations.



   ![image](https://github.com/avengers-p7/Documentation/assets/156644891/900de25c-c17c-42ce-a4cf-379bcef000f7)








    ![image](https://github.com/avengers-p7/Documentation/assets/156644891/6cdc4494-2d3a-433f-b337-f65a7e2a7068)







   ![image](https://github.com/avengers-p7/Documentation/assets/156644891/f6d6d0ba-cbd8-43ee-a86d-66049c13d679)


   

# Step 5: Trigger the Jenkins Job

Make a change in your GitHub repository and push it to trigger the Jenkins job. Jenkins will automatically start the pipeline, compile the Java code using Maven, and execute any 

other tasks you've defined in your pipeline.

***

# Conclusion

In conclusion, implementing effective Continuous Integration (CI) checks within the context of Java application design is crucial for ensuring the reliability, maintainability, and efficiency of the software development process. By integrating CI checks into the development workflow, teams can establish a systematic approach to identifying and addressing issues early in the development cycle. 

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












