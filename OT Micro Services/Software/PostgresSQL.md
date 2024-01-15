
| Author | Created on | Version | Last updated by | Last edited on |
|--------|------------|---------|-----------------|----------------|
|Shikha  | 11-01-2024 | v16    | Shikha          | 11-01-2024     |

# Introduction
PostgreSQL is a powerful open-source relational database management system (RDBMS). It is known for its extensibility, standards compliance, and support for SQL (Structured Query Language). 

# Purpose

PostgreSQL serves as a robust relational database management system (RDBMS) with a primary purpose of efficiently and securely managing and organizing structured data.

# Key Features:
| Feature | Description |
|---------|-------------|
|Locking Mechanism | PostgreSQL supports a robust locking mechanism to control access to data and ensure transactional integrity. |
|High Availability | PostgreSQL provides features for high availability, including data replication and standby servers, to minimize downtime and ensure continuous operation. |
| Free and Open-Source Software | PostgreSQL is free and open-source, allowing users to use, modify, and distribute the software without licensing fees. |
| ACID-Compliant | PostgreSQL follows ACID properties (Atomicity, Consistency, Isolation, Durability) to ensure reliable and consistent transactions. |
| Fault Tolerance |PostgreSQL has the capability for fault tolerance, allowing it to continue operating even in the presence of hardware or software failures. |
|Support for Image, Video, Audio | PostgreSQL supports storage of image, video, and audio data, making it suitable for applications that deal with multimedia content. |
|Graphical Data Support | PostgreSQL supports graphical data, making it versatile for applications that require storage and retrieval of visual content. |
| Low Maintenance Requirement |PostgreSQL is designed for efficient and low-maintenance operation, providing stability and ease of management. |
| MVCC (Multi-Version Concurrency Control)  | PostgreSQL uses MVCC to handle concurrent access to the database, allowing multiple transactions to occur simultaneously without interfering with each other. |
| High Recovery Capability | PostgreSQL has high recovery capabilities, ensuring data consistency and integrity even after system failures or crashes. |
| User-Defined Data Types | PostgreSQL allows users to define custom data types, providing flexibility and adaptability to specific application requirements. |
| Table Inheritance | PostgreSQL supports table inheritance, enabling the creation of new tables that inherit properties and columns from existing tables. |
| Cross-Platform Compatibility | PostgreSQL is compatible with various operating systems, making it versatile and suitable for deployment in diverse environments. |

# System Requirements:
| Aspect | Recommendation |
|--------|----------------|
|Processor/Instance Type | t2.medium|
| RAM (Memory) | 4 Gigabytes or Dual-Core |
| Disk Space | 16 GB or 2GB per core |
| OS Required (Linux Distributions) | Ubuntu 22.04 LTS, Debian, or CentOS 7/8 |

# Important Ports:
| 22 | Port 22 is used to establish an SSH connection to an EC2 instance and access a shell |
|----|--------------------------------------------------------------------------------------|
| 443 | It is a standard port for secure communication over the internet between client and server |
| 5432 | Port for PostgreSQL |

## How to Setup/Install PostgreSQL

# 1. Add PostgreSQL APT repository to your system.
###  Step 1: Create the file repository configuration:
     sudo sh -c 'echo "deb https://apt.postgresql.org/pub/repos/apt $(lsb_release -cs)-pgdg main" > /etc/apt/sources.list.d/pgdg.list'
###  Step 2: Import the repository signing key:
     wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add -

# 2. Update the package lists:
###  Update the package list to ensure it has the latest information about available packages
     sudo apt-get update

###  Install the latest version of PostgreSQL and-y flag to automatically answer yes to prompts.
###  If you want a specific version, use 'postgresql-12' or similar instead of 'postgresql':
     sudo apt-get -y install postgresql

     
 ![image](https://github.com/avengers-p7/Documentation/assets/156056746/a272cacb-c0c0-49c7-b617-b49bf5a3251f)

 ### Verify Installation:
     psql -V

#    Configure and Run PostgreSQL:
###  Show status PostgreSQL Service
     sudo systemctl status postgresql
     
     

![Screenshot from 2024-01-12 19-08-23](https://github.com/avengers-p7/Documentation/assets/156056746/6441e9fb-1cd8-4868-a0f5-d2f5183c7243)

## If PostgreSQL is  running by default, and you need to start restart stop  it manually, you can use the following commands.

###  Start PostgreSQL Service
     sudo systemctl start postgresql

###  Restart PostgreSQL Service
     sudo systemctl restart postgresql

### Stop PostgreSQL Service
    sudo systemctl stop postgresql

### Access PostgreSQL Prompt:
    sudo -u postgres psql

 ![image](https://github.com/avengers-p7/Documentation/assets/156056746/6250cb64-d418-4978-af02-365733987500)
   


###    Create a user with a password
       CREATE USER myuser WITH PASSWORD 'secretpassword';

 ![image](https://github.com/avengers-p7/Documentation/assets/156056746/9361214c-a12b-4707-9cd6-ef15a4afe517)

###  List username
     SELECT usename FROM pg_user;

 ![image](https://github.com/avengers-p7/Documentation/assets/156056746/9b3dadc1-a5eb-4037-a76e-7e5185b59c6e)





### Create a Database:
    CREATE DATABASE your_database_name;
    

![image](https://github.com/avengers-p7/Documentation/assets/156056746/072dacc9-4d7d-46ec-b495-c80f8df822f3)

### List database name:
    SELECT datname FROM pg_database;
    

![image](https://github.com/avengers-p7/Documentation/assets/156056746/33b5f515-21f8-42b7-b2ba-686b959e9623)


# Conclusion:
  
Congratulations! You have successfully installed and configured PostgreSQL on your system. PostgreSQL, with its powerful features and commitment to standards compliance, emerges as a reliable choice for your relational database needs. Dive into its extensive functionalities, including ACID compliance, high availability, and support for diverse data types. Leverage its stability and versatility to build robust and scalable applications. As an open-source solution, PostgreSQL offers a cost-effective and community-driven option for developers and enterprises. Explore the rich ecosystem of tools and extensions, and harness the potential of PostgreSQL to create high-performance and secure database-driven applications.

# Contact Information

| Shikha Tripathi | shikha.tripathi.snaatak@mygurukulam.co |
|-----------------|----------------------------------------|





# References
| Links | Description |
|--------|-----------------|
| https://www.postgresql.org/download/ | Prerequisites, Installation & Configuration |
| https://github.com/OT-MICROSERVICES/documentation-template/wiki/Software-Template | Document format followed from this link|

