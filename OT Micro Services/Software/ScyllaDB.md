# ScyllaDB Installation Guide

|   Author     |  Created on   |  Version   | Last updated by | Last edited on |
| ------------ | --------------| -----------|---------------- | -------------- |
| Vikram BISHT | 10 Jan 2024   |     v1     | Vikram Bisht    | Vikram Bisht   |

---

# Introduction

Welcome to the ScyllaDB Installation Guide! ScyllaDB is a highly performant and scalable NoSQL database that combines the best features of Apache Cassandra with innovative optimizations, resulting in superior throughput and lower latency. Designed for high-performance applications, ScyllaDB provides seamless scalability and fault tolerance, making it an excellent choice for various use cases.

## Key Features

* **Scalability:** Easily handle large amounts of data and growing workloads by scaling horizontally.
* **Flexibility:** Adapt to diverse application needs with a NoSQL database model, offering flexibility in data modeling.
* **Performance:** Achieve superior throughput and low-latency performance, making ScyllaDB ideal for high-performance applications.
* **Fault Tolerance:** Ensure high availability and fault tolerance with a distributed architecture that distributes data across multiple nodes.

---

# Licensing

| License Type                         | Description                                   | Commercial Use | Open Source |
| ------------------------------------ | --------------------------------------------- | --------------- |------------- |
| Affero General Public License (AGPL) | Free and open for public use and modification | Yes             | Yes         |

---

# Software Overview

|   Software   |  Version   |
| ------------ | -----------|
|     ScyllaDB |    5.4.1   |

---

# System Requirements

|   System Requirement              |             Minimum                     |
|-----------------------------------|-----------------------------------------|
| Processor/Instance Type           |             t2.medium                   | 
| RAM                               |      4 Gigabytes or Dual-Core           |
| Disk Space                        |       16 GB or 2GB per core             |
| OS Required (Linux Distributions) | Ubuntu 20.04 LTS, Debian, or CentOS 7/8 |

---

# Important Ports

| Ports         | Description                                                                                | 
| ------------- |--------------------------------------------------------------------------------------------|
| 22            | Port 22 is used to establish an SSH connection to an EC2 instance and access a shell       |
| 443           | It is a standard port for secure communication over the internet between client and server |
| 9042          | Port for ScyllaDB                                                                          |

---

# Dependencies

|   Run-time Dependency    |                Version     | 
| ------------------------ |----------------------------|
|      Java                |               11 or 17     |

---

## How to Setup/Install ScyllaDB

### 1. Add ScyllaDB APT repository to your system.

### Step 1: Create a directory for APT keyrings
    sudo mkdir -p /etc/apt/keyrings

### Step 2: Import ScyllaDB GPG key
    sudo gpg --homedir /tmp --no-default-keyring --keyring /etc/apt/keyrings/scylladb.gpg --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys d0a112e067426ab2

### Step 3: Download ScyllaDB APT repository configuration file
    sudo wget -O /etc/apt/sources.list.d/scylla.list http://downloads.scylladb.com/deb/debian/scylla-5.4.list

### 2. Install ScyllaDB packages

### Update the package list to ensure it has the latest information about available packages
    sudo apt-get update

### Install ScyllaDB packages with the -y flag to automatically answer yes to prompts
    sudo apt-get install -y scylla

---

## Configure and Run ScyllaDB
This script tunes system settings and determines optimal configurations.

### Run scylla_setup script
    sudo scylla_setup

  The script displays some information and then asks a question, for example:
  Do you want to select the default (yes/no):

  To choose the default (yes), just press 'Enter' without typing anything.

![image](https://github.com/avengers-p7/Documentation/assets/156056709/9f9b14d4-ee03-49bb-8c6b-643125baaed9)


### Run ScyllaDB as a service

    sudo systemctl start scylla-server

### Configure parameters in /etc/scylla/scylla.yaml

Edit the following parameters in the configuration file:

    * seeds - The IP address of the first node.
    * listen_address - The IP address for node-to-node connections.
    * rpc_address - The IP address for client connections (Thrift, CQL).

![image](https://github.com/avengers-p7/Documentation/assets/156056709/a983ea56-9e40-4668-880e-75f1b11a1e80)

### Restart ScyllaDB as a service

    sudo systemctl restart scylla-server

# Getting Started

## Check ScyllaDB Cluster Status

To check if your ScyllaDB cluster is working fine, use the `nodetool` command. This command provides information about the nodes in the ScyllaDB cluster:

     nodetool status

![image](https://github.com/avengers-p7/Documentation/assets/156056709/4bfbbc5c-61a2-490f-9b07-0a82df61af03)


## Interact with ScyllaDB using Cqlsh

To interact with ScyllaDB and execute CQL queries, use the cqlsh command:

    cqlsh <Node-Private-IP>

![image](https://github.com/avengers-p7/Documentation/assets/156056709/c04e6e42-da36-45f0-96fe-4b7ec69de3b0)

##Creating a Keyspace & Table in Scylla

    CREATE KEYSPACE IF NOT EXISTS employee_db
      WITH replication = {'class': 'SimpleStrategy', 'replication_factor': 1};

![image](https://github.com/avengers-p7/Documentation/assets/156056709/df990d44-6af6-4059-8a36-dce0b0e10787)


### Use Your Keyspace to create table
    USE employee_db;

![image](https://github.com/avengers-p7/Documentation/assets/156056709/6c132bb6-9f10-4a18-9bb5-76a47acc483a)

### Create a Table Inside Keyspace

    CREATE TABLE IF NOT EXISTS employee_info (
        id text, name text, designation text, department text,
        joining_date date, address text, office_location text,
        status text, email text, phone_number text,
        PRIMARY KEY (id, joining_date)
    ) WITH CLUSTERING ORDER BY (joining_date DESC);

![image](https://github.com/avengers-p7/Documentation/assets/156056709/9142cd9b-55e0-490a-9561-5428787e7c8b)


#Conclusion

Congratulations! You have successfully installed and configured ScyllaDB on your system. ScyllaDB's robust features and performance capabilities make it a reliable choice for your NoSQL database needs. Explore its functionalities and leverage its scalability to build high-performance applications.

#References
	
|  Source                  |                Description | 
| ------------------------ |----------------------------|
| https://opensource.docs.scylladb.com/stable/getting-started/install-scylla/install-on-linux.html | Prerequisites, Installation & Configuration |
| https://github.com/OT-MICROSERVICES/documentation-template/wiki/Software-Template                | Document format followed from this link     |
