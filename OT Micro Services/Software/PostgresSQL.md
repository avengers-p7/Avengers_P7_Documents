
| Author | Created on | Version | Last updated by | Last edited on |
|--------|------------|---------|-----------------|----------------|
|Shikha  | 11-01-2024 | v16    | Shikha          | 11-01-2024     |
---------------------------------------------------------------------------------------------------------------------------------------------
## Introduction
PostgreSQL is a powerful open-source relational database management system (RDBMS). It is known for its extensibility, standards compliance, and support for SQL (Structured Query Language). 


------------------------------------------------------------------------------------------------------------------------------------------

## Key Features:
| Feature | Description |
|---------|-------------|
| **Open Source** | PostgreSQL is an open-source relational database management system. |
| **Transaction Support** | Ensures the execution of a series of operations as a single unit, providing atomicity and consistency. |
| **Concurrency Control** | Manages simultaneous access to data to prevent conflicts and ensure data integrity in concurrent environments. |
| **Advanced Querying Capabilities** | Supports complex queries, including the ability to  join tables, filter data, and aggregate results. |
|  **Replication and High  Availability** | Offers mechanisms for duplicating data across multiple nodes to enhance reliability and availability. |         |

--------------------------------------------------------------------------------------------------------------------------------------------
## PostgreSQL Architecture

![image](https://github.com/avengers-p7/Documentation/assets/156056746/20aebe9c-2452-4171-9153-015c35fbaf1b)




----------------------------------------------------------------------------------------------------------------------------------------------


## System Requirements:
| Aspect | Recommendation |
|--------|----------------|
|Processor/Instance Type | Dual-Core /t2.medium|
| RAM (Memory) | 4 Gigabytes |
| Disk Space | 16 GB or 2GB per core |
| OS Required (Linux Distributions) | Ubuntu 22.04 LTS, Debian, or CentOS 7/8 |

-----------------------------------------------------------------------------------------------------------------------------------------------

### Important Ports
| Inbound Traffic|	Description |
|----|--------------------------------------------------------------------------------------|
| 22 | Port 22 is used to establish an SSH connection to an EC2 instance and access a shell |
| 443 | It is a standard port for secure communication over the internet between client and server |
| 5432 | Port for PostgreSQL |


----------------------------------------------------------------------------------------------------------------------------------------------

## How to Setup/Install PostgreSQL

### 1. Add PostgreSQL APT repository to your system.
###  Step 1: Create the file repository configuration:
     sudo sh -c 'echo "deb https://apt.postgresql.org/pub/repos/apt $(lsb_release -cs)-pgdg main" > /etc/apt/sources.list.d/pgdg.list'
###  Step 2: Import the repository signing key:
     wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add -

### 2. Update the package lists:
###  Update the package list to ensure it has the latest information about available packages
     sudo apt-get update

###  Install the latest version of PostgreSQL and-y flag to automatically answer yes to prompts.
     sudo apt-get -y install postgresql

   
    
  
   ![image](https://github.com/avengers-p7/Documentation/assets/156056746/349a395c-6bca-482d-bc90-e7b01c9a746e)
 


 ### Verify Installation:
     psql -V

##    Run PostgreSQL:
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

##   Configure PostgreSQL Settings

    sudo nano /etc/postgresql/<version>/main/postgresql.conf

###  Restart postgreSQL Service:
     sudo systemctl restart postgresql


----------------------------------------------------------------------------------------------------------------------------------------------

##  Monitoring
   Monitoring, in the context of computer systems and software, refers to the continuous process of observing, gathering, and analyzing data 
   related to the performance, health, and behavior of a system or application. 

##  Install pgAdmin:
### Install the public key for the PgAdmin4 repository:
    curl -fsSL https://www.pgadmin.org/static/packages_pgadmin_org.pub | sudo gpg --dearmor -o /etc/apt/trusted.gpg.d/pgadmin.gpg

###  Create the repository configuration file:
     sudo sh -c 'echo "deb https://ftp.postgresql.org/pub/pgadmin/pgadmin4/apt/$(lsb_release -cs) pgadmin4 main" > 
     /etc/apt/sources.list.d/pgadmin4.list'

###  Update the package lists to synchronize the repository.
     sudo apt update

###  Run the following command to install pgAdmin:
     sudo apt install pgadmin4

###  After the GUI setup finishes, initiate the primary pgAdmin configuration with this command:
     sudo /usr/pgadmin4/bin/setup-web.sh
     
 ![image](https://github.com/avengers-p7/Documentation/assets/156056746/7f877ac4-460f-4fca-8561-4727ad5fe14d)


###  To access the pgAdmin web-based interface, enter the following in your web browser’s address bar:
     185.185.185.185/pgadmin4
     

![image](https://github.com/avengers-p7/Documentation/assets/156056746/8f9948be-0f52-47f8-a357-fde25ef20a0d)



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

---------------------------------------------------------------------------------------------------------------------------------------------


## Conclusion:
  
Congratulations! You have successfully installed and configured PostgreSQL on your system. PostgreSQL, with its powerful features and commitment to standards compliance, emerges as a reliable choice for your relational database needs. Dive into its extensive functionalities, including ACID compliance, high availability, and support for diverse data types. Leverage its stability and versatility to build robust and scalable applications. As an open-source solution, PostgreSQL offers a cost-effective and community-driven option for developers and enterprises. Explore the rich ecosystem of tools and extensions, and harness the potential of PostgreSQL to create high-performance and secure database-driven applications.

-----------------------------------------------------------------------------------------------------------------------------------------------

## Contact Information

| Shikha Tripathi | shikha.tripathi.snaatak@mygurukulam.co |
|-----------------|----------------------------------------|





## References
| Links | Description |
|--------|-----------------|
| https://www.postgresql.org/download/ | Prerequisites, Installation & Configuration |
| https://github.com/OT-MICROSERVICES/documentation-template/wiki/Software-Template | Document format followed from this link|

