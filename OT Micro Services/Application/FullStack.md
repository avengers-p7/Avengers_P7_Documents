# OT Microservices Full Stack Setup Guide

| **Author** | **Created On** | **Last Updated** | **Document Version** |
| ---------- | -------------- | ---------------- | -------------------- |
| **Shreya Jaiswal** | 14-01-2024 | 22-01-2024 | V1 |
| **Parasharam Desai** | 14-01-2024 | 22-01-2024 | V1 |

*** 
# Table Of Content

### 01. [Introduction](#Introduction)

### 02. [Prerequisites](#Prerequisites)

### 03. [System Requirements](#System-Requirements)

### 04. [Dependencies](#Dependencies)

### 05. [Ports](#Ports)                                                                 

### 06. [Architecture](#Architecture)

### 07. [Full Stack Setup](#Full-Stack-Setup)

### 08. [Conclusion](#Conclusion)

### 09. [Reference](#Reference)

### 10. [Contact Information](#Contact-Information)

***

# Introduction

**Modern and Modular Architecture**
Our OT microservices full stack setup is designed with a contemporary and modular architecture, placing a strong emphasis on scalability and efficiency.

**Dedicated APIs for Workforce Management**
The system incorporates dedicated APIs for managing crucial aspects of the workforce, including employees (Employee), salaries (Salary), and attendance (Attendance). This ensures precision in handling workforce-related processes.

**Central Role of PostgreSQL**
At the core of our system is PostgreSQL, a reliable and widely acclaimed relational database known for its proficiency in handling structured data. It provides a robust foundation for storing and managing crucial business information.

**ScyllaDB for Large Datasets**
The system leverages ScyllaDB, a powerful NoSQL database, known for its efficiency in managing large datasets. This makes it particularly valuable in scenarios where high performance and scalability are essential.

**Redis for Enhanced System Responsiveness**
Playing a crucial role, Redis serves as an in-memory data store. Its purpose is to enhance system responsiveness by swiftly providing access to frequently used information. This contributes to a more agile and responsive overall system.

**Technological Backbone**
The combination of PostgreSQL, ScyllaDB, and Redis forms the robust technological backbone of our microservices architecture. This strategic blend of technologies ensures a reliable, scalable, and high-performance foundation for our system.

***
# Prerequisites

Before initiating the setup process, it is crucial to thoroughly review the following documentation and ensure the installation of all dependencies in a systematic manner. This step-by-step approach guarantees a smooth setup of our OT microservices full stack:

| **APIs/Software** | **Link** |
| ----------------- | -------- |
| Frontend | [Frontend Documentation](https://github.com/avengers-p7/Documentation/blob/main/OT%20Micro%20Services/Application/Frontend.md) |
| Attendance API | [Attendance API Documentation](https://github.com/avengers-p7/Documentation/blob/main/OT%20Micro%20Services/Application/Attendance_API.md) |
| Salary API | [Salary API Documentation](https://github.com/avengers-p7/Documentation/blob/main/OT%20Micro%20Services/Application/Salary_API.md) |
| Employee API | [Employee API Documentation](https://github.com/avengers-p7/Documentation/blob/main/OT%20Micro%20Services/Application/Employee_API.md) |
| Redis Link | [Redis Documentation](https://github.com/avengers-p7/Documentation/blob/main/OT%20Micro%20Services/Software/Redis.md) |
| ScyllaDB Link | [ScyllaDB Documentation](https://github.com/avengers-p7/Documentation/blob/main/OT%20Micro%20Services/Software/ScyllaDB.md) |
| PostgreSQL Link | [PostgreSQL Documentation](https://github.com/avengers-p7/Documentation/blob/main/OT%20Micro%20Services/Software/PostgresSQL.md) |

By carefully following these guides, you'll be ready to set up our microservices system accurately.


***

# System Requirements

|   System Requirement              |             Minimum                     |
|-----------------------------------|-----------------------------------------|
| Instance Type                     |             t2.large                    | 
| RAM                               |               8GB                       |
| Disk Space                        |              30GB                       |
| OS Required (Linux Distributions) |          Ubuntu 22.04 LTS, Debian       |


***

# Dependencies

Assuming you've followed the prerequisite documentation steps, the required dependencies for the setup should already be installed. However, for clarity, here's a recap of the dependencies:

### Build time Dependency

|          Name            |             Description               |
| ------------------------ |---------------------------------------|
| maven                    |   Build automation tool                 |
| java17                   |   Java Development Kit (JDK)            |
| poetry                   |   Python dependency management         |
| GNU make                 |   Build automation tool                 |
| npm                      |   Node package manager                  |


### Runtime Dependency

|          Name            |          Description                  |
| ------------------------ |---------------------------------------|
| ScyllaDB                 |    Database for employee API            |
| redis                    |   In-memory data store                  |
| postgres                 |   Relational database                   |
| liquibase                |   Database schema migration             |
| migrate                  |   Database migration tool               |
| jq                       |   Command-line JSON processor           |
| pylint                   |   Python linting tool                   |
| Node.js                  | JavaScript runtime for scalable network applications using Chrome's V8 engine. |

***

# Important Ports

Specify the important ports used by the microservices and their descriptions.

|Inbound Ports  | Description               |
|--------|---------------------------|
| 22     | SSH port                  |
| 3000   | Default REACTJS port      |
| 8080   | All API ports (Collective)|

| Outbound Ports  | Description          | 
|--------|----------------------|
| 5432   | PostgreSQL port       | 
| 6379   | Redis port            | 
| 9042   | Scylla DB port        | 
| 8080   | All API ports (Collective)| 

                    
***

# Architecture

![image](https://github.com/Parasharam-DevOps/Avenger-P7/assets/132131379/57b0df34-d415-4c50-abc2-240add12e423)


***
# Full Stack Setup

**Attendance API Setup**

First we need to setup Attendance API with the help of above mentioned [Attendance API Documentation](https://github.com/avengers-p7/Documentation/blob/main/OT%20Micro%20Services/Application/Attendance_API.md) 

![image](https://github.com/avengers-p7/Documentation/assets/156056444/79d4d041-5f0c-4746-982e-f6871ac4c5b9)

**Salary API Setup**

Setup Salary API with the help of above mentioned [Salary API Documentation](https://github.com/avengers-p7/Documentation/blob/main/OT%20Micro%20Services/Application/Salary_API.md)  

![image](https://github.com/avengers-p7/Documentation/assets/156056444/fc25571a-7348-4262-9ad8-c3e1eee191e8)

**Employee API Setup**

Setup Employee API with the help of above mentioned [Employee API Documentation](https://github.com/avengers-p7/Documentation/blob/main/OT%20Micro%20Services/Application/Employee_API.md) 

![image](https://github.com/avengers-p7/Documentation/assets/156056444/266b3207-80b2-40c8-8dfb-99875804ad33)

**Frontend Setup**

Setup Frontend with the help of above mentioned [Frontend Documentation](https://github.com/avengers-p7/Documentation/blob/main/OT%20Micro%20Services/Application/Frontend.md) 

![image](https://github.com/avengers-p7/Documentation/assets/156056444/95934702-af71-4c32-928c-4bee540db938)



***
# Conclusion

In conclusion, the OT Microservices Full Stack Setup provides a modern and modular architecture that emphasizes scalability and efficiency. With dedicated APIs for employee management, salary processing, and attendance tracking, the system ensures precision in workforce-related processes.

The combination of robust databases such as PostgreSQL for structured data, ScyllaDB for efficient handling of large datasets, and Redis as an in-memory data store forms the backbone of our microservices. 

***

# Contact Information


| Name                 | Email                      |
| -------------------- | -------------------------- |
| Shreya Jaiswal       | shreya.jaiswal.snatak@mygurukulam.co |                          
| Parasharam Desai     |  parasharam.desai.snaatak@mygurukulam.co   |

***

# Reference

| Source               | Description                |
| -------------------- | -------------------------- |
| [Frontend Documentation](https://github.com/avengers-p7/Documentation/blob/main/OT%20Micro%20Services/Application/Frontend.md)            | Fronend Setup Documentation |
| [Attendence_API Documentation]( https://github.com/avengers-p7/Documentation/blob/main/OT%20Micro%20Services/Application/Attendance_API.md)            | Attendence_Api Setup Documentation |
| [Employee_API Documentation](https://github.com/avengers-p7/Documentation/blob/main/OT%20Micro%20Services/Application/Employee_API.md)            | Employee_API Setup Documentation |
| [Salary_API Documentation](https://github.com/avengers-p7/Documentation/blob/main/OT%20Micro%20Services/Application/Salary_API.md) | Salary_API Setup Documentation |
| [PostgreSQL Documentation](https://github.com/avengers-p7/Documentation/blob/main/OT%20Micro%20Services/Software/PostgresSQL.md) | PostgreSQL Setup Documentation |
| [Redis Documentation](https://github.com/avengers-p7/Documentation/blob/main/OT%20Micro%20Services/Software/Redis.md) | Redis Setup Documentation |
| [ScyllaDB Documentation](https://github.com/avengers-p7/Documentation/blob/main/OT%20Micro%20Services/Software/ScyllaDB.md) | SycllaDB Setup Documentation |




