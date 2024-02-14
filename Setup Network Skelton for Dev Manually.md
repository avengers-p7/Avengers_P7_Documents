# Documentation of Setup Network Skelton for Dev Manually




# Introduction 

Virtual Private Cloud (VPC) for a development network is crucial in building a secure and isolated environment within AWS to develop and test applications. A VPC allows developers to define their virtual network topology, including IP address ranges, subnets, route tables, and access control policies. By creating a VPC, developers gain granular control over network resources and can implement security measures tailored to their needs. This setup enables teams to experiment with different configurations, deploy multiple environments, and collaborate on projects without impacting production systems. In this process, developers can launch EC2 instances, deploy databases, and configure networking components such as internet gateways and security groups to simulate real-world scenarios and ensure that applications perform as expected. Overall, setting up a VPC for a development network lays the foundation for efficient and secure software development practices within the AWS cloud environment.

# Virtual Private Cloud

Amazon VPC lets you provision a logically isolated section of the Amazon Web Services (AWS) cloud where you can launch AWS resources in a virtual network that you define. You have complete control over your virtual networking environment, including a selection of your IP address ranges, creation of subnets, and configuration of route tables and network gateways. You can also create a hardware Virtual Private Network (VPN) connection between your corporate data center and your VPC and leverage the AWS cloud as an extension of your corporate data center.



# Components of  VPC


Amazon VPC comprises a variety of objects that will be familiar to customers with existing networks:

|Components | Description |
|------------|-------------|
|A Virtual Private Cloud | A logically isolated virtual network in the AWS cloud. You define a VPC’s IP address space from the ranges you select|
|Subnet | A segment of a VPC’s IP address range where you can place groups of isolated resources|
|Internet Gateway |The Amazon VPC side of a connection to the public Internet|
|NAT Gateway |A highly available, managed Network Address Translation (NAT) service for your resources in a private subnet to access the Internet|
|Route Table| A route table contains a set of rules, called routes, that are used to determine where network traffic from your subnet or gateway is directed|
|DNS Hostname |The Amazon DNS server resolves a public DNS hostname to the public IPv4 address of the instance outside the network of the instance|
|CIDR |Classless Inter-Domain Routing|



# Let’s start the implementation


Virtual Private Cloud (VPC) manually involves several steps, primarily configuring networking components such as subnets, route tables, internet gateways, and security groups. Below is a basic guide to manually setting up a VPC for a development network on AWS:

**Step 01. Create a VPC**

1. Login to your AWS Console.


![image](https://github.com/avengers-p7/Documentation/assets/156644891/50a144d2-d0a9-4d42-b594-1f56dd23c36d)


2. Create your VPC with a Valid CIDR and name.


![image](https://github.com/avengers-p7/Documentation/assets/156644891/5f775baa-7aa3-4d5d-a3f0-4a64348af8e9)




![image](https://github.com/avengers-p7/Documentation/assets/156644891/63a0e499-cf3b-432f-a480-72d7b323d5a3)




![image](https://github.com/avengers-p7/Documentation/assets/156644891/bc3dbcdb-61ee-4f64-b0da-b29cb99287cf)





![image](https://github.com/avengers-p7/Documentation/assets/156644891/9a7fe07f-0f93-4950-a2f6-662532be42cb)




**Step 02. Create 2 Public Subnets & Create 2 Private Subnets**

1. Click Subnet and create your Subnet with:
2. Public Subnet 1 and Public Subnet 2 valid Name & VPC.
3. Valid Subnet range which is a valid IPv4 CIDR Block.
4. Repeat steps 2 & 3, with Private Subnet too.


![image](https://github.com/avengers-p7/Documentation/assets/156644891/07cd76f5-5ad5-44d5-bb2c-948a7d7466d5)




![image](https://github.com/avengers-p7/Documentation/assets/156644891/571ef3cc-3b5d-423a-8b80-585cdedae781)



**Step 03. Create IGW (Internet Gateway) & Attach to the VPC**



![image](https://github.com/avengers-p7/Documentation/assets/156644891/abe9a358-7372-4984-abca-2e6412991a6b)



![image](https://github.com/avengers-p7/Documentation/assets/156644891/5de3af68-6d20-484b-9471-e80ff40c3735)



![image](https://github.com/avengers-p7/Documentation/assets/156644891/1a821470-dd14-4ca8-84ff-e7257aabe3dc)



![image](https://github.com/avengers-p7/Documentation/assets/156644891/e4903eec-dd25-4188-837c-46a50b2d9d79)




# Step 04. Create Public and Private Route Table


**Route table concepts**

The following are the key concepts for route tables.

Main route table — The route table that automatically comes with your VPC. It controls the routing for all subnets that are not explicitly associated with any other route table.

Custom route table — A route table that you create for your VPC.

Edge association — A route table that you use to route inbound VPC traffic to an appliance. You associate a route table with the internet gateway or virtual private gateway, and specify the network interface of your appliance as the target for VPC traffic.

Route table association — The association between a route table and a subnet, internet gateway, or virtual private gateway.

Subnet route table — A route table that’s associated with a subnet.

Gateway route table — A route table that’s associated with an internet gateway or virtual private gateway.

Local gateway route table — A route table that’s associated with an Outposts local gateway. For information about local gateways, see Local Gateways in the AWS Outposts User Guide.

Destination — The range of IP addresses where you want traffic to go (destination CIDR). For example, an external corporate network with a 172.16.0.0/12 CIDR.

Target — The gateway, network interface, or connection through which to send the destination traffic; for example, an internet gateway.

Local route — A default route for communication within the VPC


1. Create a Route table in the same VPC.
   
2. Make sure you selected the right VPC and give a proper tag.



![image](https://github.com/avengers-p7/Documentation/assets/156644891/ce5cc55d-3bca-4ef2-a31a-66559cc7275c)



# Step 05. Add IGW in Public Route table (0.0.0.0/0)

Click on the Public route table and click on the edit button.

Click on Add route from 0.0.0.0/0

Select Internet gateway from Target drop-down menu.

Click on save the routes.



![image](https://github.com/avengers-p7/Documentation/assets/156644891/2644d8dc-91dd-47be-9b45-3e45705a2d49)




![image](https://github.com/avengers-p7/Documentation/assets/156644891/ec0862e0-4cbb-492b-9dbe-cd42d9a3a1aa)



![image](https://github.com/avengers-p7/Documentation/assets/156644891/7d16fc7a-ea36-42e5-ade2-88779344da67)




# Step 07. Create a NAT Gateway in Public Subnet

Select a Public Subnet

Create a new Elastic IP and associate

click on Create NAT Gateway



![image](https://github.com/avengers-p7/Documentation/assets/156644891/0c63cc2b-c89e-4933-8c6f-24e228e9e229)




 ![image](https://github.com/avengers-p7/Documentation/assets/156644891/78ee8abb-fa1e-4f08-9fc9-e9df637f1753)





![image](https://github.com/avengers-p7/Documentation/assets/156644891/a5edebd4-8674-4b06-a8ec-4c0aba07ebcc)



# Step 08. Add NAT GW into the Private Route Table

1. Click on the Private route table and click on the edit button.
2. Click on Add route from 0.0.0.0/0
3. Select nat gateway from Target drop-down menu.
4. Click on save the routes.
























`















 
