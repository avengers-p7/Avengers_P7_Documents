# POC of Static Code analysis in Python

|   Author        |  Created on   |  Version   | Last updated by  | Last edited on |
| --------------- | --------------| -----------|----------------- | -------------- |
| Vikram Bisht    |  31 Jan 2024  |  Version 1 | Vikram Bisht     | 3 Feb  2024    |

# Table of Contents
- [Introduction](#Introduction)
- [Pre-requisites](#pre-requisites)
- [Flow Diagram](#flow-diagram)
- [POC of Static Code Compilation in Python](#POC-of-Static-Code-Compilation-in-Python)
- [Output](#Output)
- [Conclusion](#conclusion)
- [Contact Information](#contact-information)
- [Resources and References](#resources-and-references)
***

# Introduction
Static code analysis is the process of analyzing source code without executing it. 

# Pre-requisites

| **Tool**   |    
| --------   | 
|  Python    | 
|  Pylint    |

| **Code**               |
| --------               | 
|  Any Python code       |

# Flow Diagram
![image](https://github.com/avengers-p7/Documentation/assets/79625874/719436d6-e814-494e-aed1-138734eccebe)


# POC of Static Code Compilation in Python

**Step-1** Clone the Repository:
- Open a terminal (or command prompt).
- Navigate to the desired directory using cd commands.
- Clone the repository using 

``` shell 
git clone https://github.com/avengers-p7/Attendance-API.git
```
![image](https://github.com/avengers-p7/Documentation/assets/79625874/f841215a-499d-4c7a-b629-fc4a8237572a)


**Step-2** Install python and pylint
``` shell 
sudo apt install python3
sudo apt install pylint
```      
![image](https://github.com/avengers-p7/Documentation/assets/79625874/7485e84c-3fc9-467b-a260-62462f4ed399)

**Step-3** Run pylint
``` shell 
pylint app.py
```      
![image](https://github.com/avengers-p7/Documentation/assets/79625874/87386afe-5989-4b36-9d05-3fbc2e977ec0)

# Output
The output we received from running pylint on app.py file indicates the quality of our Python code according to pylint's metrics.
our code has been rated at 10.00/10: This means that pylint has evaluated Python code and assigned it a score of 10 out of 10. This is the highest possible score, indicating that pylint didn't find any issues or violations of Python coding standards in your code.

# Conclusion

The output from pylint indicates that your Python code has been analyzed and evaluated against a set of coding standards and best practices. The conclusions you can draw from the pylint output are:
* High Quality Code
* Code Health

In summary, the pylint output indicates that your Python code is of excellent quality.  This should give you confidence in the reliability and maintainability of your codebase.

# Contact Information

|  Name                     |        	Email Address           |
| ------------              | --------------------------------|
| Vikram Bisht              |  Vikram.Bisht@opstree.com       |  

# Resources and References
[Static Code Compilation](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/04-%20Python%20CI%20Checks/Static%20code%20analysis(Python%20CI%20Checks).md) 

[POC](https://towardsdatascience.com/check-the-quality-of-your-code-with-pylint-f5d829bb441d)
