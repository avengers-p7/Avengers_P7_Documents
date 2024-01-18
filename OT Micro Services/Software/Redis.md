# Manual Setup of Redis

|   Author        |  Created on   |  Version   | Last updated by  | Last edited on |
| --------------- | --------------| -----------|----------------- | -------------- |
| Khushi Malhotra |  09 Jan 2024  |  Version 1 | Khushi Malhotra  | 11 Jan 2024    |


# Introduction
--------------------------------------------------------------------------------------------------------------------
Redis is an open-source, in-memory data structure. Redis stores data in memory and supports a mechanism to persist data to disk. Redis is popular for caching, session management, real-time analytics, and pub/sub applications.


# Purpose
--------------------------------------------------------------------------------------------------------------------
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
--------------------------------------------------------------------------------------------------------------------
| **Features**   | **Description**                                                                |
|-------------------|---------------------------------------------------------------------------|
| **Speed**            | Data lives in RAM, not on disks, for **blazing-fast** access and response times. |
|  **Durability**     | Choose from options like write-back with journaling or persistent memory for data protection beyond server crashes. |
|  **Availability**   | Built-in replication ensures continuous operation even if servers fail. |
| **Scalability**    | Cluster multiple servers to handle growing data volumes and concurrent requests. |


# Software Overview
--------------------------------------------------------------------------------------------------------------------
- Open-source (BSD licensed)
- Written in ANSI C
- Single-threaded architecture
- Client-server model


# System Requirements
--------------------------------------------------------------------------------------------------------------------
#### The minimum requirements of a Redis infrastructure for non-productive OutSystems environments are the following:

|   System Requirement              |             Minimum                        |
|-----------------------------------|--------------------------------------------|
| Processor/Instance Type           |             Dual Core/t2.medium            | 
| RAM                               |               4GB                          |
| Disk Space                        |               10GB                         |            
| OS Required (Linux Distributions) | Ubuntu 20.04 LTS, Debian, or CentOS 7/8    |


# Important Ports
--------------------------------------------------------------------------------------------------------------------
| Configuration       | Port  | 
| ------------------- |-------|
| Redis Default port  | 6379  |
         
                                                         
# Dependencies
--------------------------------------------------------------------------------------------------------------------
| Dependencies           | Description            | 
| ---------------------- |------------------------|           
| Run-time dependencies  | None                   |
| Other dependencies     | Optional Redis modules |


# Redis Setup Guide
--------------------------------------------------------------------------------------------------------------------
Here is a snippet view showcasing the use of Redis in OT-Microservices.

![image](https://github.com/Parasharam-DevOps/Avenger-P7/assets/132131379/57b0df34-d415-4c50-abc2-240add12e423)



# Install on Ubuntu/Debian
--------------------------------------------------------------------------------------------------------------------
You can install recent stable versions of Redis from the official [packages.redis.io](http://packages.redis.io/) APT repository.

# Prerequisites
- connect to each server over SSH
If you're running a very minimal distribution (such as a Docker container) you may need to install lsb-release, curl and gpg first:

### Run the following commands to install Redis.

#### Step 1: Import the Redis GPG key

	curl -fsSL https://packages.redis.io/gpg | sudo gpg --dearmor -o /usr/share/keyrings/redis-archive-keyring.gpg

#### Step 2: Add the Redis repository to the system's package manager

	echo "deb [signed-by=/usr/share/keyrings/redis-archive-keyring.gpg] https://packages.redis.io/deb $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/redis.list

#### Step 3: Update the package manager's repository information

	sudo apt-get update

#### Step 4: Install Redis server

	sudo apt-get install -y redis-server


## Verify Installation

	redis-cli --version
	redis-server --version

### Activate the redis-server service 

    sudo systemctl start redis-server.service 

    sudo systemctl status redis-server.service

![image](https://github.com/avengers-p7/Documentation/assets/156056709/63d809b4-484b-4c4f-b78e-b3abbb2fbc60)

### Redis Connection Confirmation
#### redis-cli: 
This is the Redis command-line interface, and you're invoking it to interact with the Redis server.

#### 127.0.0.1:6379>: 
This is the Redis prompt, indicating that you are connected to the Redis server running on the local machine (127.0.0.1) on port 6379.

#### PING: 
This is a Redis command used to check if the server is running and responding. It's a simple "ping-pong" test.

#### PONG: 
The Redis server responds with "PONG," indicating that it is indeed running and responding to commands.

	redis-cli
    
![image](https://github.com/avengers-p7/Documentation/assets/156056709/5f17f6c9-a36f-4004-9e7f-2d6b992c49ab)


## Setup the Master Node
--------------------------------------------------------------------------------------------------------------------
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

### See the Status Of redis-server.

    sudo systemctl status redis-server

### Redis CLI Authentication and Access

![image](https://github.com/avengers-p7/Documentation/assets/156056709/59c56b34-1f5f-4540-8114-1318493348f2)


    
# Conclusion
--------------------------------------------------------------------------------------------------------------------
Redis rockets your app's performance with lightning-fast data access, but keep your persistence needs elsewhere.


# Contact Information
| Name            | Email Address                        |
|-----------------|--------------------------------------|
| Khushi Malhotra | khushi.malhotra.snaatak@mygurukulam.co |


# Resources and References
--------------------------------------------------------------------------------------------------------------------
|  Source                  |                Description | 
| ------------------------ |----------------------------|
|(https://www.digitalocean.com/community/tutorials/how-to-install-and-secure-redis-on-ubuntu-20-04) | Prerequisites, Installation & Configuration |
|https://redis.io/docs/about/           | Understanding of Redis Software  |


