# Code Compilation in Python CI Checks

|   Author     |  Created on   |  Version   | Last updated by | Last edited on |
| ------------ | --------------| -----------|---------------- |--------------- |
| Vikram BISHT | 26 Jan 2024   |     v1     | Vikram Bisht    | 29 Jan 2024    |

---
# Table of Contents 
+ [Introduction](#introduction)
+ [What is Code compilation](#What-is-Code-compilation)
+ [Why Code Compilation](#Why-Code-Compilation)
+ [Different Tools](#Different-Tools)
+ [Advantages](#Advantages)
+ [Proof of Concept](#Proof-of-Concept)
+ [Best Practices](#Best-Practices)
+ [Conclusion](#conclusion)
+ [Contact Information](#contact-information)
+ [References](#References)
***


# Introduction
Python code compilation refers to the process of translating Python source code into machine-readable bytecode or executable code. This document aims to provide a comprehensive overview of Python code compilation, its purpose, tools, advantages, best practices, and recommendations.

# What is Code compilation

Python code compilation involves converting human-readable Python source code into a format that can be executed by the Python interpreter. This process typically involves several steps, including lexical analysis, parsing, optimization, and generation of bytecode or machine code.


# Why Code Compilation

|  Reason                         |        Description                                                             |
| ---------                       | ------------------------------------------------------------------------------ |
| Performance                     | Compiled code can often execute faster than interpreted code                   |  
| Distribution                    | Compiled code can be distributed without exposing the original source code     |
| Platform Independence           | Compiled bytecode can run on any platform with a compatible Python interpreter |
| Code Optimization               | Compilation allows for optimization techniques to improve code efficiency      |


# Different Tools
Some popular tools for Python code compilation include:

* Cython
* Numba
* PyInstaller
* Nuitka
* PyOxidizer

Each tool offers unique features and capabilities for compiling Python code.

# Comparison

Comparison of Tools: Here is a comparison of the different tools for code compilation in Python:

| Tools                    |        Pros                                                        |          Cons                                     |
| ------------             | -------------------------------------------------------------------| --------------------------------------------------|
| Cython                   | High performance, C extensions support	                            |  Steeper learning curve                           |
| Numba                    | Just-in-time compilation, easy to use                              | 	Limited support for certain features             |
| PyInstaller              | Cross-platform packaging                                           |  Large distribution size                          |
| Nuitka                   | High optimization, compatible with CPython                         |  Limited support for some libraries               |
| PyOxidizer               | Standalone executables, easy to use                                | 	Limited documentation                            |


# Advantages

* Improved performance
* Enhanced code security
* Simplified distribution
* Better integration with existing codebases


# Proof of Concept

> [!NOTE]
> POC for Python  Code Compilation is prepared in different doc,if you want to see the code compilation of Python please use this link [Python Code compilation POC](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/04-%20Python%20CI%20Checks/Python%20Code%20Compilation%20POC%20.md) 
***


# Best Practices

When implementing code compilation in Python, the following best practices should be considered:
* Document your compilation process for future reference.
* Keep your dependencies and libraries updated for compatibility with compilation tools.
* Write clear and concise code to facilitate the compilation process.
* Use automated testing to ensure that the compiled code meets quality standards

# Conclusion

Python code compilation is a valuable technique for improving performance, code security, and distribution. Choose the compilation tool that best fits your project requirements and consider experimenting with different tools to optimize your code further.
<br>
For beginners, PyInstaller offers a straightforward way to compile Python code into standalone executables. As projects grow in complexity, exploring advanced tools like Cython and Nuitka can provide additional performance optimizations.


# Contact Information

|  Name                     |        	Email Address           |
| ------------              | --------------------------------|
| Vikram Bisht              |  Vikram.Bisht@opstree.com       |  

# References

|  Source                                                                                 |        Description    |
| ------------                                                                            | ----------------------|
| https://cython.org/                                                                     |       Cython          |  
| https://pyinstaller.org/en/stable/                                                      | pyinstaller           |	
| https://pyoxidizer.readthedocs.io/en/latest                                             | PyOxidizer            |
      

