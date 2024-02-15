
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

**Step 3: Edit all /etc/hosts For example for node1::**

```
10.252.55.129  node1
10.252.54.125  node2
10.252.54.87   node3
10.252.54.174  node4
10.252.54.81   haproxy
```

**Step 4: Install postgresql server software on node1,node2 and node3. Also stop postgresql service after installation:**
* Edit the PostgreSQL configuration file

```
sudo apt install postgresql postgresql-contrib -y
sudo systemctl stop postgresql```
```

**Step 6: Install patroni on node1,node2,node3**
```
sudo apt -y install python3-pip python3-dev libpq-dev
pip3 install --upgrade pip
sudo pip install patroni
sudo pip install python-etcd
sudo pip install psycopg2
```

**Step 7  Configuration of patroni on node1 node 2 and node3:**
Create /etc/patroni.yml and add below lines to patroni.yml
```
scope: postgres
namespace: /db/
name: node1
restapi:
  listen: 10.252.55.129:8008
  connect_address: 10.252.55.129:8008
etcd:
  host: 10.252.54.174:2379
bootstrap:
  dcs:
    ttl: 30
    loop_wait: 10
    retry_timeout: 10
    maximum_lag_on_failover: 1048576
    postgresql:
    use_pg_rewind: true
  initdb:
    - encoding: UTF8
    - data-checksums
  pg_hba:
    - host replication replicator   127.0.0.1/32 md5
    - host replication replicator   10.252.55.129/0   md5
    - host replication replicator   10.252.54.125/0   md5
    - host replication replicator   10.252.54.87/0   md5
    - host all all   0.0.0.0/0   md5
  users:
    admin:
       password: admin
       options:
       - createrole
       - createdb
postgresql:
   listen: 10.252.55.129:5432
   connect_address: 10.252.55.129:5432
   data_dir:     /data/patroni
   pgpass:     /tmp/pgpass
   authentication:
    replication:
      username:   replicator
      password:     "A1qaz2wsx3edc"
    superuser:
      username:   postgres
      password:     "B1qaz2wsx3edc"
      parameters:
      unix_socket_directories:  '.'
tags:
   nofailover:   false
   noloadbalance:   false
   clonefrom:   false
   nosync:   false
```
**Step 6: Start patroni services on node1,node2,node3**
```
sudo systemctl daemon-reload
sudo systemctl start patroni
```

In Below output we can see status of our PostgreSQL cluster. 

![image](https://github.com/avengers-p7/Documentation/assets/79625874/160b25ad-3dd6-43c9-98c2-4c0d5fea0a3a)

![image](https://github.com/avengers-p7/Documentation/assets/79625874/6922972a-32e0-4504-9380-e56d5c75fa42)


# Conclusion

This is a simplified guide, and the specific details may vary based on your operating system, PostgreSQL version, and the tools you choose.

Patroni is primarily responsible for managing the high availability aspects of PostgreSQL clusters, including automated failover and promotion of new primary nodes. However, Patroni itself does not handle logical replication directly. Logical replication is a feature provided by PostgreSQL itself.


# Contact Information

|  Name                     |        	Email Address           |
| ------------              | --------------------------------|
| Vikram Bisht              |  Vikram.Bisht@opstree.com       |  

# References

| Title                                      | URL                                           |
|--------------------------------------------|-----------------------------------------------|
| PostgreSQL documentation                   | https://docs.ansible.com/ansible/latest/index.html    |
| PostgreSQL Cluster                         |  [Link](https://medium.com/@murat.bilal/setting-up-a-postgresql-ha-cluster-0a4348fca444) |

