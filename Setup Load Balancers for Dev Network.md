# Documentation of setup load balancer 

| Author                                                           | Created on  | Version    | Last Updated by | Last Updated on |
| ---------------------------------------------------------------- | ----------- | ---------- | --------------- | --------------- |
| Nidhi Bhardwaj                                                    | 16-02-2024  | 1.0        | Nidhi Bhardwaj   | 16-02-2024      |




![image](https://github.com/avengers-p7/Documentation/assets/156644891/0464b487-4177-4793-8778-a841e09e8e6f)







# Introduction 

A load balancer is a critical networking component designed to evenly distribute incoming traffic across multiple servers or resources, ensuring efficient resource utilization and high availability. Serving as a traffic cop, it intelligently routes requests based on predefined algorithms or rules, preventing any single server from becoming overwhelmed. Load balancers monitor the health of servers in real time, directing traffic only to healthy instances and seamlessly redistributing requests if any server fails or becomes overloaded. With capabilities for session persistence and scalability, load balancers optimize performance, enhance reliability, and mitigate potential bottlenecks in modern network architectures. Whether implemented as hardware appliances, software solutions, or cloud services, load balancers play a fundamental role in maintaining seamless operations for web applications, services, and distributed systems.



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
CLB offers a simple and easy-to-use load-balancing solution, but it lacks some of the advanced features and scalability capabilities of ALB and NLB.





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
|Load balancer| The load balancer distributes incoming application traffic across multiple targets (e.g., EC2 instances in multiple AWS availability zones) to increase application availability|
|Listener| A listener checks for client connection requests using the protocol and port configured by an organization per rules that determine how the Application Load Balancer routes requests to registered targets|
|Target group | Application Load Balancer routes requests to one or more registered targets (e.g., EC2 instances) using the protocol and port number configured by an organization|


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
# Routing method in load balancer

Load balancers use different routing methods to distribute incoming traffic across multiple backend servers or services. Each routing method has its own advantages and is suitable for different scenarios. Here are some common routing methods used in load balancers:


|Components|Description|
|----------|-----------|
|Round Robin | This is one of the simplest routing methods where each new connection or request is sent to the next backend server in line, looping back to the first server after reaching the end of the list. Round-robin is easy to implement and ensures that each server receives an equal share of the load. However, it doesn't take server load or capacity into account, so it may not be suitable for situations where servers have different capabilities |
|Least Connections| With this method, incoming requests are forwarded to the server with the fewest active connections. This helps to distribute the load more evenly among servers and prevents overloading of individual servers. It's particularly useful in scenarios where the workload on servers varies over time|
|IP Hash| In IP hash routing, the load balancer calculates a hash value based on the source IP address of the incoming request and uses this value to determine which backend server to route the request to. This ensures that requests from the same client are consistently directed to the same server, which can be useful for maintaining session persistence or sticky sessions|
|Weighted Round Robin |Weighted round-robin assigns a weight to each backend server, indicating its processing capacity or capability. Servers with higher weights receive a larger proportion of incoming traffic. This allows administrators to prioritize certain servers over others based on their capacity to handle the load|
|Least Response Time |This method routes incoming requests to the server with the lowest response time or latency. It continuously monitors the response times of backend servers and directs traffic to the server that is currently responding the fastest. This helps to optimize performance by minimizing response times for clients|
|Least Bandwidth |Similar to least connections, this method directs traffic to the server with the lowest bandwidth usage. It's useful for scenarios where bandwidth consumption varies significantly between servers|

The choice of routing method depends on factors such as the characteristics of the application, the workload on the servers, the desired level of session persistence, and the specific requirements of the deployment. Often, a combination of routing methods may be used within a load balancer configuration to optimize performance and ensure high availability.


***

# use cases of load balancer 


Load balancers play a crucial role in ensuring high availability, scalability, and efficient resource utilization for various types of applications and services. Here are some common use cases for load balancers

|Components | Description |Use cases |
|-----------|-------------|----------|
|Web Applications|Load balancers distribute incoming HTTP and HTTPS traffic across multiple web servers to ensure that no single server becomes overwhelmed with requests| E-commerce websites, social media platforms, news websites, and other web-based applications with high traffic volumes benefit from load balancers to maintain responsiveness and availability|
|API Services|Load balancers distribute incoming API requests across multiple backend servers to ensure consistent performance and availability|Microservices architectures, where multiple APIs handle different functionalities, benefit from load balancing to evenly distribute incoming requests among service instances|
|Streaming Services|Load balancers distribute incoming streaming media requests, such as video or audio content, to optimize performance and minimize latency for users.| Video streaming platforms, music streaming services, and live broadcasting platforms utilize load balancers to efficiently deliver content to users while maintaining a seamless streaming experience|
|Application Servers|Load balancers distribute traffic across multiple application servers to prevent overloading and ensure optimal resource utiliEnterprise applications, business management systems, and customer relationship management (CRM) platforms benefit from load balancers to handle concurrent user interactions and maintain application responsiveness|
|Database Servers|Load balancers can distribute database queries and transactions across multiple database servers to improve performance, scalability, and fault tolerance| High-traffic websites, e-commerce platforms, and data-intensive applications benefit from load balancers to evenly distribute database loads and prevent database bottlenecks|
|Internal Services|Load balancers route traffic between internal services or microservices within a private network to ensure optimal resource utilization and fault tolerance|Internal APIs, backend services, and internal communication channels within organizations benefit from load balancers to improve service reliability and scalability|
|Hybrid Cloud Deployments|Load balancers facilitate traffic distribution between on-premises infrastructure and cloud-based resources in hybrid cloud environments| Organizations with hybrid cloud architectures use load balancers to route traffic between on-premises data centers and cloud-based services, ensuring seamless connectivity and workload distribution|





# POC of Load Balancer 




**Step 1:   Launch the two instances on the AWS management console named Dev A and Dev B. Go to services and select the load balancer**



![image](https://github.com/avengers-p7/Documentation/assets/156644891/4c19d2e8-5419-4246-ba1c-a59d0c13ba37)





**Step 2: Click on Create the load balancer**





![image](https://github.com/avengers-p7/Documentation/assets/156644891/f4e6bddf-eb7f-4eb5-898e-1435ed20455b)






**Step 3: Select Application Load Balancer and click on Create**






![Screenshot from 2024-02-15 21-27-29](https://github.com/avengers-p7/Documentation/assets/156644891/0e921075-9c94-4712-b643-f9a12ad837ef)







**Step 4: Here you are required to configure the load balancer. Write the name of the load balancer. Choose the scheme as internet-facing**





![image](https://github.com/avengers-p7/Documentation/assets/156644891/bbcdee5e-e000-40a7-b017-ae3feda25c51)






 **Step 5: Add at least 2 availability zones. Select eu-north-1a and eu-north-1b**
 




![image](https://github.com/avengers-p7/Documentation/assets/156644891/ab580dd7-c0f8-4f53-ac0b-466445ffef68)







**Step 6:  We don’t need to do anything here. Click on Next: Configure Security Groups**






![image](https://github.com/avengers-p7/Documentation/assets/156644891/cd8fdefe-2c54-4528-a37c-f750dd57c92b)






**Step 7: Select the default security group. Click on Next: Configure Routing**






![image](https://github.com/avengers-p7/Documentation/assets/156644891/494b8916-fe03-4784-aebe-05008f7ded41)







**Step 8: Choose the name of the target group to be my target group. Click on Next: Register Targets**






![Screenshot from 2024-02-15 21-52-45](https://github.com/avengers-p7/Documentation/assets/156644891/9fe11b2a-3313-4b63-92ea-1d24721b6435)







**Step 9:  Choose Dev A and  Dev B and click on Add to register. Click on Next: Review**






![image](https://github.com/avengers-p7/Documentation/assets/156644891/337d1a06-dab1-430c-a1cd-231d02b49f7e)









![image](https://github.com/avengers-p7/Documentation/assets/156644891/51f7f645-192e-4af8-9b5e-30932f6af1c1)








**Step 10: Congratulations!! You have successfully created a load balancer. Click on close**






![image](https://github.com/avengers-p7/Documentation/assets/156644891/1379695a-8e4e-4f40-8011-84df6a228726)






# Conclusion 


In conclusion, the implementation of a load balancer in Amazon Web Services (AWS) offers significant benefits for enhancing the reliability, scalability, and performance of web applications. By distributing incoming traffic across multiple servers or instances, load balancers help prevent any single server from becoming overwhelmed, thus ensuring high availability and improved fault tolerance. AWS provides various types of load balancers, including Application Load Balancers (ALB), Network Load Balancers (NLB), and Classic Load Balancers, each catering to different use cases and traffic management needs. Additionally, AWS load balancers integrate seamlessly with other AWS services, such as Auto Scaling, ensuring that the infrastructure can dynamically adapt to fluctuating traffic demands. Through features like health checks and session persistence, load balancers in AWS further optimize the user experience and overall application performance. Overall, the integration of load balancers in AWS architecture is crucial for achieving robust, scalable, and resilient web applications in the cloud environment.







# Contact Information

|     Name         | Email  |
| -----------------| ------------------------------------ |
| Nidhi Bhardwaj    | nidhi.bhardwaj.snaatak@mygurukulam.co |




# References 


| Description                  | References  
| ------------------------ | ------------------------------------------------------------------- |
|Documentation |             https://www.geeksforgeeks.org/elastic-load-balancer-in-aws/
|Setup|       https://aws.amazon.com/what-is/load-balancing/#:~:text=Elastic%20Load%20Balancing%20(ELB)%20is,complex%20configurations%20or%20API%20gateways|






















 





































