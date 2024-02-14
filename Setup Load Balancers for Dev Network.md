# Documentation of setup loadbalancer 





# Introduction 

A load balancer is a critical networking component designed to evenly distribute incoming traffic across multiple servers or resources, ensuring efficient resource utilization and high availability. Serving as a traffic cop, it intelligently routes requests based on predefined algorithms or rules, preventing any single server from becoming overwhelmed. Load balancers monitor the health of servers in real-time, directing traffic only to healthy instances and seamlessly redistributing requests if any server fails or becomes overloaded. With capabilities for session persistence and scalability, load balancers optimize performance, enhance reliability, and mitigate potential bottlenecks in modern network architectures. Whether implemented as hardware appliances, software solutions, or cloud services, load balancers play a fundamental role in maintaining seamless operations for web applications, services, and distributed systems.


***

# What is an Application Load Balancer?


Elastic Load Balancing automatically distributes your incoming traffic across multiple targets, such as EC2 instances, containers, and IP addresses, in one or more Availability Zones. It monitors the health of its registered targets, and routes traffic only to the healthy targets. Elastic Load Balancing scales your load balancer as your incoming traffic changes over time. It can automatically scale to the vast majority of workloads.

Elastic Load Balancing supports the following load balancers: Application Load Balancers, Network Load Balancers, Gateway Load Balancers, and Classic Load Balancers. You can select the type of load balancer that best suits your needs. This guide discusses Application Load Balancers. For more information about the other load balancers



***


# What is Application Load Balancer 

A load balancer serves as the single point of contact for clients. The load balancer distributes incoming application traffic across multiple targets, such as EC2 instances, in multiple Availability Zones. This increases the availability of your application. You add one or more listeners to your load balancer.

A listener checks for connection requests from clients, using the protocol and port that you configure. The rules that you define for a listener determine how the load balancer routes requests to its registered targets. Each rule consists of a priority, one or more actions, and one or more conditions. When the conditions for a rule are met, then its actions are performed. You must define a default rule for each listener, and you can optionally define additional rules.

Each target group routes requests to one or more registered targets, such as EC2 instances, using the protocol and port number that you specify. You can register a target with multiple target groups. You can configure health checks on a per target group basis. Health checks are performed on all targets registered to a target group that is specified in a listener rule for your load balancer.


**The following diagram illustrates the basic components. Notice that each listener contains a default rule, and one listener contains another rule that routes requests to a different target group. One target is registered with two target groups**



![image](https://github.com/avengers-p7/Documentation/assets/156644891/169eac07-8a17-4787-8cdb-8c17f1eac09d)



***


# Application Load Balancer components



In Amazon Web Services (AWS), an Application Load Balancer (ALB) is a highly scalable and feature-rich load balancing service designed to distribute incoming application traffic across multiple targets, such as EC2 instances, containers, or Lambda functions. The key components of an ALB in AWS include:

|Components | Description |
|-----------|-------------|
|Listener  | Listeners define the protocol and port on which the load balancer listens for incoming connections. You can configure multiple listeners on an ALB, each associated with a specific port and protocol (e.g., HTTP, HTTPS, WebSocket). Listeners are responsible for forwarding incoming requests to the appropriate target groups based on the routing rules defined |
|Target Groups |Target groups are logical groupings of targets (e.g., EC2 instances, containers, IP addresses) that receive traffic from the load balancer. When configuring an ALB, you specify one or more target groups for each listener. ALBs support dynamic registration and deregistration of targets with target groups, allowing for automatic scaling and high availability|
|Routing Rules| Routing rules determine how incoming requests are distributed to the target groups based on the request attributes, such as the host, path, or query parameters. ALBs support flexible routing options, including path-based routing, host-based routing, and header-based routing, enabling you to route traffic to different target groups based on specific conditions|
|Health Checks| Health checks are periodic checks performed by the ALB to assess the health and availability of the targets registered with the target groups. ALBs continuously monitor the health of targets and automatically route traffic only to healthy targets. If a target fails the health check, it is marked as unhealthy, and the ALB stops sending traffic to it until it passes the health check again|
|Security Policies |ALBs provide built-in support for SSL/TLS termination, allowing the load balancer to handle HTTPS traffic and offload SSL decryption from the backend targets. You can configure SSL certificates and security policies to enforce encryption and security best practices. Additionally, ALBs integrate with AWS Web Application Firewall (WAF) for advanced security protections against common web exploits and attacks|
|Access Logs and Monitoring  |ALBs generate access logs that capture detailed information about each request processed by the load balancer, including the source IP address, request path, response status code, and more. These access logs can be stored in Amazon S3 buckets for analysis and auditing purposes. Additionally, ALBs integrate with AWS CloudWatch for monitoring and metrics, allowing you to monitor the performance and health of your load balancer and applications in real-time.|




***


# Advanatges of Loadbalancer 

Using a load balancer in AWS offers several advantages:

|Components | Description |
|-----------|-------------|
|High Availability |Load balancers distribute incoming traffic across multiple instances or services, ensuring that if one instance fails, others can handle the traffic. This enhances the overall availability and fault tolerance of your application |
|Auto Scaling | Load balancers seamlessly integrate with AWS Auto Scaling, allowing you to automatically scale your application in response to changing traffic patterns. As demand increases, additional instances can be added to the load balancer's target groups, and as demand decreases, instances can be removed, optimizing resource utilization and cost efficiency|
|Improved Performance | By distributing traffic across multiple instances or services, load balancers can improve the performance of your application by preventing any single instance from becoming overwhelmed. This helps maintain consistent response times and ensures a smooth user experience even during periods of high traffic |
|SSL Termination |Load balancers support SSL termination, allowing them to handle HTTPS traffic and offload SSL decryption from the backend instances. This helps reduce the computational burden on the instances and simplifies certificate management|
|Flexibility| AWS offers different types of load balancers to suit various use cases, including Application Load Balancers (ALBs), Network Load Balancers (NLBs), and Classic Load Balancers (CLBs). Each type has its own features and capabilities, allowing you to choose the most suitable option for your specific requirements|
|Security |Load balancers provide security features such as access control lists (ACLs) and integration with AWS Web Application Firewall (WAF) to protect your application against common web exploits and attacks. They also support encryption of data in transit using SSL/TLS, ensuring the confidentiality and integrity of communication between clients and servers |
|Centralized Management |Load balancers can be managed through the AWS Management Console, CLI, or API, providing a centralized interface for configuring and monitoring your load balancer resources. This simplifies management tasks and allows for automation and integration with other AWS services|



***


# Types of load balancer 

In the context of AWS, there are primarily three types of load balancers:

**Application Load Balancer (ALB)**

ALB operates at the application layer (Layer 7) of the OSI model, making routing decisions based on the content of the request.
It supports advanced routing features such as path-based routing, host-based routing, and integration with AWS Lambda for serverless applications.
ALB is optimized for HTTP and HTTPS traffic, making it ideal for modern web applications, microservices architectures, and API endpoints.

**Network Load Balancer (NLB)**

NLB operates at the transport layer (Layer 4) of the OSI model, forwarding traffic based on IP protocol data.
It is designed to handle high-throughput, low-latency workloads, making it suitable for TCP and UDP traffic.
NLB provides ultra-low latency and scales to millions of requests per second, making it ideal for scenarios such as gaming, real-time communications, and IoT applications.

**Classic Load Balancer (CLB)**

CLB is the original load balancer offering in AWS, providing basic load balancing across multiple EC2 instances.
It operates at both the application and transport layers, supporting HTTP, HTTPS, TCP, and SSL traffic.
CLB offers a simple and easy-to-use load balancing solution, but it lacks some of the advanced features and scalability capabilities of ALB and NLB.


























