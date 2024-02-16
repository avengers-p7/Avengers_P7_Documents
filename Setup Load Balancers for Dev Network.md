# Documentation of setup load balancer 

| Author                                                           | Created on  | Version    | Last Updated by | Last Updated on |
| ---------------------------------------------------------------- | ----------- | ---------- | --------------- | --------------- |
| Nidhi Bhardwaj                                                    | 16-02-2024  | 1.0        | Nidhi Bhardwaj   | 16-02-2024      |




# Table of Content 

1. [Introduction](#Introduction)
2. [What is  Application Load Balancer](#What-is-Application-Load-Balancer)
3. [Application Load Balancer](#Application-Load-Balancer)
4. [Advanatges of Loadbalancer](#Advanatges-of-Loadbalancer) 
5. [Types of Load balancers](#Types-of-Load-Balancers)
6. [POC of Load-Balancer](#POC-of-Load-Balancers)
7. [Conclusion](#Conclusion)
8. [Contact Information](#Contact-Information)
9. [References](#References)
   



# Introduction 

A load balancer is a critical networking component designed to evenly distribute incoming traffic across multiple servers or resources, ensuring efficient resource utilization and high availability. Serving as a traffic cop, it intelligently routes requests based on predefined algorithms or rules, preventing any single server from becoming overwhelmed. Load balancers monitor the health of servers in real time, directing traffic only to healthy instances and seamlessly redistributing requests if any server fails or becomes overloaded. With capabilities for session persistence and scalability, load balancers optimize performance, enhance reliability, and mitigate potential bottlenecks in modern network architectures. Whether implemented as hardware appliances, software solutions, or cloud services, load balancers play a fundamental role in maintaining seamless operations for web applications, services, and distributed systems.



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


***


# POC of Load-Balancer 


**Step 1** Launch the two instances on the AWS management console named Dev A and Dev B. Go to services and select the load balancer.



![image](https://github.com/avengers-p7/Documentation/assets/156644891/4c19d2e8-5419-4246-ba1c-a59d0c13ba37)




**Step 2** Click on Create the load balancer.



![image](https://github.com/avengers-p7/Documentation/assets/156644891/f4e6bddf-eb7f-4eb5-898e-1435ed20455b)




**Step 3** Select Application Load Balancer and click on Create.




![Screenshot from 2024-02-15 21-27-29](https://github.com/avengers-p7/Documentation/assets/156644891/0e921075-9c94-4712-b643-f9a12ad837ef)







**Step 4** Here you are required to configure the load balancer. Write the name of the load balancer. Choose the scheme as internet facing.



![image](https://github.com/avengers-p7/Documentation/assets/156644891/bbcdee5e-e000-40a7-b017-ae3feda25c51)





 **Step 5** Add at least 2 availability zones. Select eu-north-1a and eu-north-1b



![image](https://github.com/avengers-p7/Documentation/assets/156644891/ab580dd7-c0f8-4f53-ac0b-466445ffef68)





**Step 6** We don’t need to do anything here. Click on Next: Configure Security Groups





![image](https://github.com/avengers-p7/Documentation/assets/156644891/cd8fdefe-2c54-4528-a37c-f750dd57c92b)





**Step 7**  Select the default security group. Click on Next: Configure Routing





![image](https://github.com/avengers-p7/Documentation/assets/156644891/494b8916-fe03-4784-aebe-05008f7ded41)






**Step 8** Choose the name of the target group to be my target group. Click on Next: Register Targets.





![Screenshot from 2024-02-15 21-52-45](https://github.com/avengers-p7/Documentation/assets/156644891/9fe11b2a-3313-4b63-92ea-1d24721b6435)






**Step 9** Choose Dev A and  Dev B and click on Add to register. Click on Next: Review.





![image](https://github.com/avengers-p7/Documentation/assets/156644891/337d1a06-dab1-430c-a1cd-231d02b49f7e)








![image](https://github.com/avengers-p7/Documentation/assets/156644891/51f7f645-192e-4af8-9b5e-30932f6af1c1)







**Step 10**  Congratulations!! You have successfully created a load balancer. Click on close.






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
|Documentation |             https://www.geeksforgeeks.org/launching-an-application-on-aws-beanstalk/?ref=ml_lbp|























 





































