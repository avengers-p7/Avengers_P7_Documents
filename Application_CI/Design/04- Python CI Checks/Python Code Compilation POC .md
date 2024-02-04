# POC of Code Compilation in Python

|   Author        |  Created on   |  Version   | Last updated by  | Last edited on |
| --------------- | --------------| -----------|----------------- | -------------- |
| Vikram Bisht    |  31 Jan 2024  |  Version 1 | Vikram Bisht     | 3 Feb  2024    |

# Table of Contents
- [Introduction](#Introduction)
- [Pre-requisites](#pre-requisites)
- [Flow Diagram](#flow-diagram)
- [POC](#POC)
- [Output](#Output)
- [Conclusion](#conclusion)
- [Contact Information](#contact-information)
- [Resources and References](#resources-and-references)
***

# Introduction
Code compilation in Python refers to the process of converting human-readable source code into machine-readable binary code.

# Pre-requisites

| **Tool**   |    
| --------   | 
|  Python    | 
|  PyInstaller    |

| **Code**               |
| --------               | 
|  Any Python code       |

# Flow Diagram
![image](https://github.com/avengers-p7/Documentation/assets/79625874/598286d2-6207-4d45-836b-44e92542a114)



# POC of Code Compilation in Python

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
pip install pyinstaller
```      
![image](https://github.com/avengers-p7/Documentation/assets/79625874/84b0de82-bddc-4a17-8ad6-0a4dfe079c66)


**Step-3** Run pyinstaller
``` shell 
pyinstaller filename.py
```      
![image](https://github.com/avengers-p7/Documentation/assets/79625874/6b311996-fdda-441e-b403-00b2bb401589)

# Output
This will generate (dist and build) directory containing the compiled executable

![image](https://github.com/avengers-p7/Documentation/assets/79625874/d61e84c0-7c77-46b1-8516-586fe81d424e)

**dist:** This directory contains the distributed files. Inside this directory, you'll find the standalone executable file along with any additional files needed for the application to run. This is the directory you'll distribute to users.

**build:** This directory is used during the build process and contains temporary files generated during compilation. It's safe to delete this directory once the compilation process is complete and you have the final executable in the 'dist' directory.



# Conclusion

For beginners, PyInstaller offers a straightforward way to compile Python code into standalone executables. As projects grow in complexity, exploring advanced tools like Cython and Nuitka can provide additional performance optimizations.

# Contact Information

|  Name                     |        	Email Address           |
| ------------              | --------------------------------|
| Vikram Bisht              |  Vikram.Bisht@opstree.com       |  

# Resources and References
[Python Code Compilation](https://avengers-p7.atlassian.net/browse/AP-96.md) 

[POC](https://pyinstaller.org/en/v6.3.0/)

