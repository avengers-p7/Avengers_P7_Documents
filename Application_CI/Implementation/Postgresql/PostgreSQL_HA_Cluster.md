
# PostgreSQL Cluster Setup
![image](https://github.com/avengers-p7/Documentation/assets/79625874/df98a36c-e308-46ba-8837-28fe0319021d)


|   Authors        |  Created on   |  Version   | Last updated by | Last edited on |
| -----------------| --------------| -----------|---------------- | -------------- |
| Vikram Bisht     |  11 Feb 2024  |     v1     | Vikram Bisht    | 12 Feb 2024    |

***


# Table of Contents
+ [Introduction](#Introduction)
+ [Pre-requisites](#Pre-requisites)
+ [Port-Numbers](#Port-Numbers)
+ [Steps-to-setup-Cluster](#Steps-to-setup-Cluster)
+ [Output Verification](#output-Verification)
+ [Conclusion](#conclusion)
+ [Contact Information](#contact-information)
+ [References](#references)

***

# Introduction
Setting up a High Availability (HA) cluster for PostgreSQL typically involves configuring multiple nodes to ensure data availability and reliability. There are various ways to achieve this, in this tutorial I deploy 3 PostgreSQL nodes with Patroni for HA setting up etcd for consensus, and using HAProxy to manage client connections.
***

# Pre-requisites

|  Pre-requisites	          |        	Description             |
| ------------              | --------------------------------|
| Multiple host             | T0 Setup Cluster                |
| PostgreSQL                | PostgreSQL needs to install in all the hosts. Here we have installed version 16  |

# Port Numbers

|   Port Number    |  Purpose      |  
| -----------------| --------------| 
| 22               | For SSH       |
| 5432             | PostdreSQL    |


# Steps to setup Cluster

Below are the steps to setup postgreSQL cluster

**Step 1: Create three AWS instances:** 

Create three AWS instances: You can use EC2 instances with a suitable instance type based on your expected workload. you can refer this [Link](https://docs.aws.amazon.com/efs/latest/ug/gs-step-one-create-ec2-resources.html) to create AWS instances. 

**Step 2: Upgrade all nodes** 

```
sudo apt update
sudo apt upgrade
```

**Step 3: Install PostgreSQL on all instances:**

```
sudo apt-get install postgresql
```
**Step 4: Configure PostgreSQL on all instances:**
* Edit the PostgreSQL configuration file

```
  sudo nano /etc/postgresql/[POSTGRESQL_VERSION]/main/postgresql.conf
```
Uncomment or edit the following lines in the postgresql.conf file:
```
listen_addresses = '*'
wal_level = replica
max_wal_senders = 3
wal_keep_size = 1GB
```
These settings configure PostgreSQL to listen on all available network interfaces, enable replication, set the maximum number of replication connections, and set the amount of storage to use for storing WAL (write-ahead logging) logs.

* Edit the PostgreSQL authentication file:
  
After saving the postgresql.conf file, you need to edit another file in the same directory:

```
sudo nano /etc/postgresql/[POSTGRESQL_VERSION]/main/pg_hba.conf
```
POSTGRESQL_VERSION refers to your PostgreSQL version.

* Add the following line to the pg_hba.conf file:

```
host replication replicator [SECOND_SERVER_IP]/32 trust
```
Replace SECOND_SERVER_IP with the IP address of the second server.
This setting allows replication connections from the second server with the replicator role.

* Restart PostgreSQL:
```
sudo systemctl restart postgresql
```
* Grant permissions to a replication role:
```
  sudo -u postgres psql
  CREATE USER replicator REPLICATION LOGIN CONNECTION LIMIT 3 ENCRYPTED PASSWORD 'your_password';
  \q
```

**Step 5: Set up replication:**
To set up a PostgreSQL cluster, you need to configure replication between the instances. You can use either logical replication or streaming replication. Logical replication allows you to replicate specific tables or databases, while streaming replication replicates the entire database. Here we used logical replication

* Configure PostgreSQL replication
  ```
  sudo -u postgres psql
  
  CREATE USER replicator REPLICATION LOGIN CONNECTION LIMIT 3 ENCRYPTED PASSWORD 'your_password';

  GRANT ALL PRIVILEGES ON DATABASE your_database TO replicator;

```













  


# Contact Information

|  Name                     |        	Email Address         |
| ------------              | --------------------------------|
| Vikram Bisht              |  Vikram.Bisht@opstree.com       |  

# References

| Title                                      | URL                                           |
|--------------------------------------------|-----------------------------------------------|
| Ansible documentation           | https://docs.ansible.com/ansible/latest/index.html    |
| PostgreSQL Document             |  [Link](https://github.com/avengers-p7/Documentation/blob/main/OT%20Micro%20Services/Software/PostgresSQL/README.md) |
| Ansible Dynamic Inventory       | https://www.youtube.com/watch?v=junPdh2yvbU&t=454s | 





