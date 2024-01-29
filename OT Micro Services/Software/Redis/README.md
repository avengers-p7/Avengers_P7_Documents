# Manual Setup of Redis

|   Author        |  Created on   |  Version   | Last updated by  | Last edited on |
| --------------- | --------------| -----------|----------------- | -------------- |
| Khushi Malhotra |  09 Jan 2024  |  Version 1 | Khushi Malhotra  | 19 Jan 2024    |

![image](https://github.com/avengers-p7/Documentation/assets/156056460/8b4c51f4-dcfd-480a-928c-606797276a4a)  

# Introduction  


Redis is an open-source, in-memory data structure. Redis stores data in memory and supports a mechanism to persist data to disk. Redis is popular for caching, session management, real-time analytics, and pub/sub applications.


# Purpose

- In-memory data structure store, used as:
	- Cache
	- Database
	- Message broker
	- Streaming engine

- Known for:
	- High performance
	- Flexibility
	- Ease of use 
 

# Key Features

| **Features**   | **Description**                                                                |
|-------------------|---------------------------------------------------------------------------|
| **Speed**            | Data lives in RAM, not on disks, for **blazing-fast** access and response times. |
|  **Durability**     | Choose from options like write-back with journaling or persistent memory for data protection beyond server crashes. |
|  **Availability**   | Built-in replication ensures continuous operation even if servers fail. |
| **Scalability**    | Cluster multiple servers to handle growing data volumes and concurrent requests. |


# Software Overview

- Open-source (BSD licensed)
- Written in ANSI C
- Single-threaded architecture
- Client-server model


# System Requirements

#### The minimum requirements of a Redis infrastructure for non-productive OutSystems environments are the following:

|   System Requirement              |             Minimum                        |
|-----------------------------------|--------------------------------------------|
| Processor/Instance Type           |             Dual Core/t2.medium            | 
| RAM                               |               4GB                          |
| Disk Space                        |               10GB                         |            
| OS Required (Linux Distributions) | Ubuntu 20.04 LTS, Debian, or CentOS 7/8    |


# Ports

| Configuration       | Port  | 
| ------------------- |-------|
| Redis Default port  | 6379  |
         
                                                         
# Dependencies

| Dependencies           | Description            | 
| ---------------------- |------------------------|           
| Run-time dependencies  | None                   |



# Redis Setup Guide

Here is a snippet view showcasing the use of Redis in OT-Microservices.

![image](https://github.com/Parasharam-DevOps/Avenger-P7/assets/132131379/57b0df34-d415-4c50-abc2-240add12e423)



# Install on Ubuntu/Debian

You can install recent stable versions of Redis from the official [packages.redis.io](http://packages.redis.io/) APT repository.

# Prerequisites

### Run the following commands to install Redis.

#### Step 1: Import the Redis GPG key

	curl -fsSL https://packages.redis.io/gpg | sudo gpg --dearmor -o /usr/share/keyrings/redis-archive-keyring.gpg

#### Step 2: Add the Redis repository to the system's package manager

	echo "deb [signed-by=/usr/share/keyrings/redis-archive-keyring.gpg] https://packages.redis.io/deb $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/redis.list

#### Step 3: Update the package manager's repository information

	sudo apt-get update

#### Step 4: Install Redis server

	sudo apt-get install -y redis-server


#### Step 5: Verify Installation

	redis-cli --version
	redis-server --version

#### Step 6: Activate the redis-server service 

    sudo systemctl start redis-server.service 

    sudo systemctl status redis-server.service

![image](https://github.com/avengers-p7/Documentation/assets/156056709/63d809b4-484b-4c4f-b78e-b3abbb2fbc60)

#### Step 7:  Redis Connection Confirmation
    
![image](https://github.com/avengers-p7/Documentation/assets/156056709/5f17f6c9-a36f-4004-9e7f-2d6b992c49ab)


# Setup the Master Node

This section shows how to set up the master node with password authentication.
- Connect to your master server over SSH.
- Open the configuration file 
 
     sudo vim /etc/redis/redis.conf

- Find the following configuration, uncomment and edit them. Change <YOUR_PASSWORD> to a secure password. The bind configuration allows the Redis server 
  to be accessible from other nodes.

### `bind 0.0.0.0`
  
![image](https://github.com/avengers-p7/Documentation/assets/156056709/165b85e3-db1d-406c-87db-f09d2b16500f)


![image](https://github.com/avengers-p7/Documentation/assets/156056709/3fec53be-b18b-42b2-9c6a-61fb9a780ecd)


### requirepass "<YOUR_PASSWORD>"

![image](https://github.com/avengers-p7/Documentation/assets/156056709/4b97dec8-8481-4b53-b488-9681d61df26b)


###  masterauth "<YOUR_PASSWORD>"

![image](https://github.com/avengers-p7/Documentation/assets/156056709/99c6cab1-bcf7-4bd1-bff9-d59803e1f459)


### Restart the redis-server service.

    sudo service redis-server restart

### See the Status of redis-server.

    sudo systemctl status redis-server
***

# Security

### Redis CLI Authentication and Access

Data Security: It safeguards your data from unauthorized access, preventing breaches, tampering, or deletion. This is crucial for protecting sensitive information stored in Redis.

Access Control: You can grant permission to specific users or groups, limiting their access to certain commands or data sets. This prevents misuse and ensures users only interact with what they need.

Operational Safety: Authentication guards against accidental or malicious actions by authorized users. Mistakes or misuse can affect Redis performance and data integrity, which authentication helps mitigate.

![image](https://github.com/avengers-p7/Documentation/assets/156056709/59c56b34-1f5f-4540-8114-1318493348f2)

| Step                        | Description                                                                                                              |
|-----------------------------|--------------------------------------------------------------------------------------------------------------------------|
| **Server Connection**       | The user connects to the Redis server using the `redis-cli` command. This initiates the command-line interface for interacting with Redis. |
| **Authentication Requirement** | The initial "ping pong" command fails with a "NOAUTH Authentication required" error. This indicates that the server has authentication enabled, meaning clients need to provide credentials before accessing data. |
| **Authentication Attempt**  | The user attempts to authenticate using the `AUTH password` command, providing the correct password. The server responds with "OK," confirming successful authentication. |
| **Access Granted**          | Once authenticated, the user can execute Redis commands, such as `ping`, which now returns "PONG" as expected.             |

***

# Advantages and Disadvantges of Redis

| **Advantages**                            | **Description**                                                                                                                                                                   |
|-------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| High Performance                          | Redis stores data in memory, leading to significantly faster read and write speeds compared to disk-based databases. Ideal for real-time applications like caching, leaderboards, and session management. |
| Data Structures                           | Redis supports various data structures (lists, sets, hashes, sorted sets) beyond simple key-value pairs, allowing efficient storage and retrieval of complex data models.               |
| Scalability                               | Easily scalable horizontally by adding more nodes to a cluster, enabling handling of increasing data volumes and concurrent users.                                                 |
| Flexibility                               | Offers high flexibility through diverse data structures, multiple persistence options, and Lua scripting capabilities, allowing for various use cases and customization.             |
| Pub/Sub                                   | Supports publish/subscribe functionality for real-time data messaging between applications, suitable for building chat applications, notifications, and event-driven systems.       |


| **Disadvantages**                         | **Description**                                                                                                                                                                   |
|-------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Memory Requirements                       | Storing data in memory can be expensive, especially for large datasets, making it less suitable for applications dealing with massive amounts of data.                             |
| Limited Persistence                       | By default, Redis stores data in memory, making it volatile and lost upon server restarts. While persistence options exist, they impact performance and introduce complexity.      |
| Not for Complex Queries                   | Focuses on simple key-value retrieval and lacks the ability to perform complex joins, aggregations, and other SQL-like queries.                                                  |
| Data Modeling Challenges                  | While offering diverse data structures, its key-value nature can lead to modeling challenges compared to relational databases when handling complex relationships between data.    |
| Security Concerns                         | In-memory data storage requires robust security measures to protect against unauthorized access and potential memory vulnerabilities.                                                |

    
# Conclusion
--------------------------------------------------------------------------------------------------------------------
Redis rockets your app's performance with lightning-fast data access, but keep your persistence needs elsewhere.


# Contact Information
| Name            | Email Address                        |
|-----------------|--------------------------------------|
| Khushi Malhotra | khushi.malhotra.snaatak@mygurukulam.co |


# Resources and References

| Source                                                | Description                                    |
| ----------------------------------------------------- | ---------------------------------------------- |
| [How to Install and Secure Redis on Ubuntu 20.04](https://www.digitalocean.com/community/tutorials/how-to-install-and-secure-redis-on-ubuntu-20-04) | Prerequisites, Installation & Configuration |
| [Redis Documentation](https://redis.io/docs/about/)   | Understanding of Redis Software                |


