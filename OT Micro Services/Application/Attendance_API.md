# Attendance-API Setup 

|   Authors        |  Created on   |  Version   | Last updated by | Last edited on |
| -----------------| --------------| -----------|---------------- | -------------- |
| Vidhi Yadav      | 10 Jan 2024   |     v1     | Vidhi Yadav     | 17 Jan 2024    |

# Introduction
Attendance API is a Python-based microservice designed to handle attendance-related transactions in the context of the OT-Microservices ecosystem. This microservice serves as a central component for managing attendance records and transactions, providing a set of RESTful APIs for integration with other services.

# Key Components
**Flask Web Framework**: The API is built using Flask, a lightweight and flexible web framework for Python, which simplifies the development of RESTful APIs.

**PostgreSQL Database**: PostgreSQL serves as the primary database for storing attendance records. Its relational nature ensures data integrity and facilitates efficient querying.

**Redis Cache Management**: Redis is employed as a cache management middleware, enhancing performance and responsiveness by storing API responses for quick retrieval.

**Prometheus and OpenTelemetry Metrics**: The API supports monitoring and observability through integration with Prometheus and OpenTelemetry, providing metrics for performance analysis.

**Liquibase**: To track the changes over time, liquibase acts as a version control for your database schema.  
Swagger Integration: Swagger is integrated for API documentation, making it easy for developers to test and interact with API endpoints.

# Flow Diagram 
<img width="802" alt="Screenshot 2024-01-12 at 1 04 42 PM" src="https://github.com/avengers-p7/Documentation/assets/156056349/c8e7795b-a96e-4570-b47a-cb0e2fda8b4f">


# Pre-Requisites
  Before running the Attendance API, certain pre-requisites need to be configured:
* PostgreSQL Database
* Redis
* Poetry (Package Manager)
* Liquibase (Database Schema Version Control)

# System Requirements:
 | Requirement | Recommendation |
 |-------------|----------------|
 | Processor/Instance Type |  Dual-Core/t2.medium |
 | RAM (Memory) |	4 Gigabytes  |
 | Disk Space | 16 GB or 2GB per core |
 | OS Required (Linux Distributions) | Ubuntu 22.04 LTS, Debian, or CentOS 7/8 |

 # Important Ports
   |  Inbound Traffic|	Description  |
   |---------|---------|
   | 5432	| Postgresql port|
   | 6379 | Redis port | |
   | 8080 | Attendance API port |
   | 22 | Port 22 to establish an SSH connection to an EC2 |
 
# API Installation
## 1. Install Dependencies:

*Install make:*
```shell
sudo apt update
sudo apt install make
```
*Install pip:*
```shell
sudo apt install python3-pip
```
    
*Install pylint:*
     sudo apt install pylint

*Install poetry:*

*  Use the `make build` command to install all the necessary dependencies using Poetry.
   *Install Poetry*
    ```shell
       pip3 install poetry
    ```
<img width="627" alt="Screenshot 2024-01-12 at 2 54 09 PM" src="https://github.com/avengers-p7/Documentation/assets/156056349/7d918115-faa1-4ff2-9a0e-0ee57a5a96c4">

## 2. Install Pre-Requisites:
*  For data storage and cache you need to setup postgreSQL and redis either as a container or locally. To setup locally you may use the following commands:

*Install Postgres*
```shell
sudo apt update
sudo apt install postgresql
```
<img width="1028" alt="Screenshot 2024-01-12 at 2 47 15 PM" src="https://github.com/avengers-p7/Documentation/assets/156056349/46a21c38-8ef8-4d57-bafa-b6a76649f310">


To create Database and user
```shell
sudo -u postgres psql
```
```shell
CREATE DATABASE attendance_db;
``` 
NOTE: remember to alter the superuser password based on the config.yaml file. Otherwise, the connection would not be established. 

To Alter the password you may use the following command
```shell
ALTER USER postgres WITH PASSWORD 'password';
``` 
*Install Redis* 
```shell
sudo apt install redis-server
```
<img width="1107" alt="Screenshot 2024-01-12 at 2 48 08 PM" src="https://github.com/avengers-p7/Documentation/assets/156056349/8ae0c0cc-0edd-436b-a6b4-9ee5bb3b75ed">

Liquibase, it is an open-source database-independent library for tracking, managing, and applying database schema changes. Liquibase 
helps in versioning and managing database schema changes in a flexible and automated way.

    
*Install Liquibase*
```shell
wget -O- https://repo.liquibase.com/liquibase.asc | gpg --dearmor > liquibase-keyring.gpg && \
cat liquibase-keyring.gpg | sudo tee /usr/share/keyrings/liquibase-keyring.gpg > /dev/null && \
echo 'deb [arch=amd64 signed-by=/usr/share/keyrings/liquibase-keyring.gpg] https://repo.liquibase.com stable main' | sudo tee /etc/apt/sources.list.d/liquibase.list
``` 
```shell
sudo apt-get update
``` 
```shell
sudo apt-get install liquibase
```
<img width="1150" alt="Screenshot 2024-01-12 at 2 53 29 PM" src="https://github.com/avengers-p7/Documentation/assets/156056349/f1bf824c-f540-4703-b254-ec87ccecef52">

To establish the connect between liquibase and postgres you need to make changes in liquibase.properties file. This is how you may do it. 

<img width="883" alt="Screenshot 2024-01-18 at 12 19 23 PM" src="https://github.com/avengers-p7/Documentation/assets/156056349/1e68f50a-d880-49e1-b841-f6ba98318418">



## 3.  Run Migrations:
*  Ensure the PostgreSQL database is up and running, then use `make run-migrations` to keep track of database schema updates.

<img width="1383" alt="Screenshot 2024-01-11 at 10 07 06 PM" src="https://github.com/avengers-p7/Documentation/assets/156056349/9f9f629a-6929-4480-a489-19582f691e3f">

## 4.  Run the Application:
*  To Load your application on gunicorn server and make it available for incoming HTTP request you may run this following command:
```shell
gunicorn app:app --log-config log.conf -b 0.0.0.0:8080
```
Once the setup is done, you can access the swagger page on http://localhost:8080/apidocs/ and track your endpoints. The page would look something like this 

<img width="1344" alt="Screenshot 2024-01-11 at 10 46 38 PM" src="https://github.com/avengers-p7/Documentation/assets/156056349/5f41585e-65f1-4e2e-81bf-ec72377a65b9">

You may further test your API methods using swagger. If test cases are passed, results should look like this:

<img width="1317" alt="Screenshot 2024-01-11 at 10 47 56 PM" src="https://github.com/avengers-p7/Documentation/assets/156056349/3537c15b-df10-436b-bffa-134a1baa8cbe">


<img width="1302" alt="Screenshot 2024-01-11 at 10 48 42 PM" src="https://github.com/avengers-p7/Documentation/assets/156056349/c254ea89-3267-4f29-a387-c3f8a421826a">


<img width="1308" alt="Screenshot 2024-01-11 at 10 49 25 PM" src="https://github.com/avengers-p7/Documentation/assets/156056349/25ec75f6-7680-49e9-899b-de8f6ed55504">


# API Endpoints 

## Endpoints Information

| **Endpoint**                     | **API Method** | **Description**                                                                                      |
|----------------------------------|------------|------------------------------------------------------------------------------------------------------|
| /metrics                         | GET        | Health check and performance metrics for application                    |
| /apidocs                         | GET        | Swagger endpoint for the application API documentation                       |
| /api/v1/attendance/create        | POST       | Data creation endpoint which accepts certain JSON body to add records in database     |
| /api/v1/attendance/search        | GET        | For searching records using the params in the URL                                  |
| /api/v1/attendance/search/all    | GET        | Endpoint for searching each data across the system             |                                
| /api/v1/attendance/health        | GET        | Provides shallow health check information about application health and readiness        |
| /api/v1/attendance/health/detail | GET        | Provides detailed health check about dependencies as well like - PostgresSQL and Redis |

## Best Practices for API security

1. **Always use TLS:** Use HTTPS to encrypt data transmitted between clients and the API server. This helps prevent man-in-the-middle attacks. Obtain and install an SSL certificate for your domain.

2. **Use OAuth for SSO:** Nearly every app will need to associate some private data with a single person. That means user accounts, and that means logging in and logging out. SSO allows users to verify themselves with a trusted third party (e.g., Google, Microsoft Azure, AWS) via token exchange to access a resource.

#  Troubleshoot
1. **Problem -** There was a need to create and manage mocks in pytest for testing, but this functionality wasn't built into pytest itself.
   
   **Solution -** The problem was resolved by installing the pytest-mock plugin using the command: `pip install pytest-mock`. The plugin provides a "mocker" fixture for creating and managing mocks in test functions.


<img width="1186" alt="Screenshot 2024-01-11 at 11 16 31 PM" src="https://github.com/avengers-p7/Documentation/assets/156056349/97e0f816-7a19-4bbf-b1af-c35bf95a1b26">


2. **Problem -** Encountered issues in pylint analysis, poetry dependency installation, and connectivity with PostgreSQL and Redis during the project.

   **Solution -** Resolved pylint and dependency problems by individually installing required packages. Modified config.yaml to fix connectivity issues with PostgreSQL and Redis containers.

# Contact Information

|Vidhi Yadav                     | vidhi.yadhav.snaatak@mygurukulam.co                                                                                      
|---------------------------------|------------------------------------------------------------|

# References

|     Description                  | References  
| ---------------------------------| ------------------------------------------------------------------- |
|     Error Handling               | https://bobbyhadz.com/blog/disable-missing-module-docstring-pylint
|     Attendance Documentation     | https://github.com/OT-MICROSERVICES/attendance-api/tree/main        
|     Error Handling               | https://pytest-with-eric.com/introduction/fixture-mocker-not-found/)https://pytest-with-eric.com/introduction/fixture-mocker-not-found/


