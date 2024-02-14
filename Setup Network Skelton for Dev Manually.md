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


# Let’s start the implementation.

 
