

|   Author        |  Created on   |  Version   | Last updated by  | Last edited on |
| --------------- | --------------| -----------|----------------- | -------------- |
| Khushi Malhotra |  09 Jan 2024  |  Version 1 | Khushi Malhotra  | 11 Jan 2024    |


# Introduction
-----------------------------------------------------------------------------------------------------------------------------------------------------------
Redis is an open-source, in-memory data structure. Redis stores data in memory and supports a mechanism to persist data to disk. Redis is popular for caching, session management, real-time analytics, and pub/sub applications.

# Purpose
---------------------------------------------------------------------------------------------------------------------------------------------------------
   
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
---------------------------------------------------------------------------------------------------------------------------------------------------------

Speed: Data lives in RAM, not on disks, for blazing-fast access and response times.

Durability: Choose from options like write-back with journaling or persistent memory for data protection beyond server crashes.

Availability: Built-in replication ensures continuous operation even if servers fail.

Scalability: Cluster multiple servers to handle growing data volumes and concurrent requests.

# Software Overview
---------------------------------------------------------------------------------------------------------------------------------------------------------
- Open-source (BSD licensed)
- Written in ANSI C
- Single-threaded architecture
- Client-server model

# System Requirements
---------------------------------------------------------------------------------------------------------------------------------------------------------
|   System Requirement              |             Minimum                        |
|-----------------------------------|--------------------------------------------|
| Processor/Instance Type           |             t2.micro                       | 
| RAM                               | Depends on dataset size (at least 1GB)     |
| Disk Space                        | Minimal for binaries, more for persistence |            
| OS Required (Linux Distributions) | Ubuntu 20.04 LTS, Debian, or CentOS 7/8    |

# Important Ports
---------------------------------------------------------------------------------------------------------------------------------------------------------

| Configuration       | Port  | 
| ------------------- |-------|
| Redis Defualt port  | 6379  |

                                                                   
# Dependencies
---------------------------------------------------------------------------------------------------------------------------------------------------------

| Dependencies           | Description            | 
| ---------------------- |------------------------|           
| Run-time dependencies  | None                   |
| Other dependencies     | Optional Redis modules |


# Setup Guide
---------------------------------------------------------------------------------------------------------------------------------------------------------
![image](https://github.com/avengers-p7/Documentation/assets/156056460/1f731c1d-e0d3-4f91-aa93-3f9ac6b8830e)

Redis Masters: The two nodes on the left-hand side of the diagram are the Redis masters. They accept read and write requests from clients.

Redis Slaves: The two nodes on the right-hand side of the diagram are the Redis slaves. They replicate the data from the masters and can be used for read-only operations or to promote a slave to a master in case of a master node failure.

Sentinels: The three nodes at the top of the diagram are the sentinels. They monitor the health of the Redis masters and will automatically promote a slave to a master if a master fails.

# Install on Ubuntu/Debian
---------------------------------------------------------------------------------------------------------------------------------------------------------
You can install recent stable versions of Redis from the official [packages.redis.io](http://packages.redis.io/) APT repository.

# Prerequisites
- connect to each server over SSH
If you're running a very minimal distribution (such as a Docker container) you may need to install lsb-release, curl and gpg first:

### Run the following commands to install Redis.

    curl -fsSL https://packages.redis.io/gpg | sudo gpg --dearmor -o /usr/share/keyrings/redis-archive-keyring.gpg 

echo "deb [signed-by=/usr/share/keyrings/redis-archive-keyring.gpg] https://packages.redis.io/deb $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/redis.list

sudo apt-get update

sudo apt-get install -y redis-server

### Activate the redis-server service 

systemctl enable redis-server

sudo systemctl status redis-server

![image](https://github.com/avengers-p7/Documentation/assets/156056460/ca800e51-7c97-4031-aaa6-63db6be54ac0)


## Setup the Master Node
---------------------------------------------------------------------------------------------------------------------------------------------------------
This section shows how to set up the master node with password authentication.
- Connect to your master server over SSH.
- Open the configuration file 
 
  sudo vim /etc/redis/redis.conf

- Find the following configuration, uncomment and edit them. Change <YOUR_PASSWORD> to a secure password. The bind configuration allows the Redis server 
  to be accessible from other nodes.

### `bind 0.0.0.0`
  
![image](https://github.com/avengers-p7/Documentation/assets/156056460/634272e5-3749-428f-bbdc-ca08d399c068)

![image](https://github.com/avengers-p7/Documentation/assets/156056460/4ac687ea-1129-4cc1-a898-85263403d50b)

### requirepass "<YOUR_PASSWORD>"

![image](https://github.com/avengers-p7/Documentation/assets/156056460/0dd56ffd-0da1-4ee5-b93a-402da305ef98)

###  masterauth "<YOUR_PASSWORD>"

![image](https://github.com/avengers-p7/Documentation/assets/156056460/18136e0e-447b-45bb-ba27-702e3878637c)


### Restart the redis-server service.

    sudo service redis-server restart
    
### See the Status Of redis-server.

    sudo systemctl status redis-server
  

# Conclusion

Redis rockets your app's performance with lightning-fast data access, but keep your persistence needs elsewhere.

# Resources and References
---------------------------------------------------------------------------------------------------------------------------------------------------------
|  Source                  |                Description | 
| ------------------------ |----------------------------|
|(https://www.digitalocean.com/community/tutorials/how-to-install-and-secure-redis-on-ubuntu-20-04) | Prerequisites, Installation & Configuration |
|https://redis.io/docs/about/           | Understanding of Redis Software  |



