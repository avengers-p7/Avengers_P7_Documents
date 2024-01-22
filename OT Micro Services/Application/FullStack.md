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

Our OT microservices full stack setup is crafted with a modern and modular architecture, prioritizing scalability and efficiency. The system features dedicated APIs for managing employees (**Employee**), salaries (**Salary**), and attendance(**Attendance**), ensuring precision in workforce-related processes.At the heart of our system lies **PostgreSQL**, a reliable database renowned for handling structured data, providing a robust foundation for crucial business information. **ScyllaDB**, a powerful NoSQL database, excels in efficiently managing large datasets, making it particularly valuable in scenarios where high performance and scalability are essential. Additionally, **Redis** plays a crucial role as an in-memory data store, enhancing system responsiveness by quickly providing access to frequently used information.This combination of technologies forms the backbone of our microservices.

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

### Application Setup

**Step 1** First we need to setup Attendance API with the help of above mentioned [Attendance API Documentation](https://github.com/avengers-p7/Documentation/blob/main/OT%20Micro%20Services/Application/Attendance_API.md)  

**Step 2** Setup Salary API with the help of above mentioned [Salary API Documentation](https://github.com/avengers-p7/Documentation/blob/main/OT%20Micro%20Services/Application/Salary_API.md)  

**Step 3** Setup Employee API with the help of above mentioned [Employee API Documentation](https://github.com/avengers-p7/Documentation/blob/main/OT%20Micro%20Services/Application/Employee_API.md) 

**Step 4** Setup Frontend API with the help of above mentioned [Frontend Documentation](https://github.com/avengers-p7/Documentation/blob/main/OT%20Micro%20Services/Application/Frontend.md) 

### Software Installation

**Step 1**  Install PostgreSQL Database with the help of above mentioned [PostgreSQL Documentation](https://github.com/avengers-p7/Documentation/blob/main/OT%20Micro%20Services/Software/PostgresSQL.md)  

**Step 2**  Install Scylla Database with the help of above mentioned [ScyllaDB Documentation](https://github.com/avengers-p7/Documentation/blob/main/OT%20Micro%20Services/Software/ScyllaDB.md)

**Step 3**  Install Redis Database with the help of above mentioned [Redis Documentation](https://github.com/avengers-p7/Documentation/blob/main/OT%20Micro%20Services/Software/Redis.md) 


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




