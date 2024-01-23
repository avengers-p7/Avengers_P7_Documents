# Documentations of  Code Complication in Java CI checks

|Author  | Created on |version | last updated on|
|--------|------------|---------|----------------|
|Nidhi Bhardwaj | 23-01-2024  | V1 | 23-01-2024 |

# Introduction 

Java CI code compilation in the context of checking in code. Continuous Integration (CI) is a development practice that emphasizes frequent integration of code changes and automated testing. 

**Definition**: Continuous Integration is a development practice where developers frequently integrate their code changes into a shared repository. Each integration triggers automated processes such as builds, tests, and validations.

**Objective**: To detect and address integration issues early in the development process, ensuring a consistent and reliable codebase.


# Different Tools of java Complication 

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
Integrations with IDEs	Integrated	Integration available (e.g., Eclipse, IntelliJ IDEA)	Integration available (e.g., IntelliJ IDEA)	Integration available (e.g., Eclipse)
Community Support	N/A	Active community support	Active community support	Moderate community support













