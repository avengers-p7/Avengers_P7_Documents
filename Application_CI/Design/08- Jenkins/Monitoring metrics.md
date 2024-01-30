# Monitoring Metrics of Jenkins 

***

| Author | Created on | last updated | Document Version | **Last Updated By** |
| ------ | ---------- | ------------ | ---------------- | ------------------- |
| Nidhi  | 30-01-24   | 30-01-24     |  V1              | Nidhi Bhardwaj |
 
***

# Tables of Content 

1.  Introduction
2.  Why is it Important to monitor Jenkins
3.  Key performance Metrics of Jenkins
4.  What is Prometheus
5.  features and components of Prometheus
6.  Monitoring Websites using Grafana and Prometheus
7.  Network Setup
8.  POC for Grafana and Prometheus
9.  conclusion
10. Contact Information 
11. References


***
# Introduction 

Jenkins is an integral part of many modern IT infrastructures. It allows organizations to model CI/CD pipelines via code, automate operational workflows, increase efficiency, and reduce the time it takes to test, ship, and deploy applications.

***

# Why is it Important to monitor Jenkins 

Monitoring Jenkins will allow you to predict errors, ensure high availability, optimize your configuration sets, and track the progress of key automation workflows.

# Ensure that critical automation workflows are working as expected

Organizations use Jenkins jobs and pipelines to automate various areas of the IT ecosystem. For example, they might have Jenkins pipelines that:

**Step 1**  Move code from a temporary branch to the master branch, and then to production.

**Step 2** Scan for memory leaks in newly committed code.

**Step 3** Perform static code analysis on the entire codebase every week

***

# Key performance Metrics of Jenkins 

Jenkins is an open-source automation server widely used for continuous integration and continuous delivery (CI/CD). Monitoring key performance metrics in Jenkins is crucial for ensuring the efficiency and reliability of your CI/CD pipeline. Here are some key performance metrics for Jenkins

|Name | Definition | Importance|
|------|------------|-----------|
|Build Success Rate |Percentage of successful builds compared to the total number of builds |Indicates the stability and reliability of the CI/CD pipeline |
|Build Duration | Average time taken for a build to complete | Helps identify bottlenecks and optimize the build process for efficiency |
|Queue Length|The number of jobs waiting to be executed in the build queue |Indicates the load on the Jenkins server and helps in resource planning |
|Node Utilization| Percentage of time Jenkins agents (nodes) spend executing builds|Ensures efficient utilization of available resources and identifies underutilized nodes|
 |Executor Utilization |Percentage of time Jenkins executors are busy running builds |Similar to node utilization, it helps optimize the use of available resources |
|Artifact Repository Size | The size of artifacts generated and stored during builds |Monitors the growth of artifacts and helps manage storage requirements|
|Job Failure Rate| Percentage of unsuccessful builds or job failures  | Identifies issues in the codebase or configuration that lead to build failures|
|Code Coverage|Percentage of code covered by automated tests| Measures the effectiveness of test coverage in ensuring code quality |
|Plugin Performance | Performance metrics for Jenkins plugins |Ensures that plugins do not significantly impact Jenkins performance|
|Pipeline Execution Time |Time taken for the entire CI/CD pipeline to execute| Measures the efficiency of the end-to-end automation process|

***

# What is Prometheus

Prometheus is an open-source monitoring and alerting toolkit designed for reliability and scalability. It was originally developed by SoundCloud and later became a standalone open-source project under the Cloud Native Computing Foundation (CNCF). Prometheus is commonly used for monitoring systems and applications in a cloud-native environment, particularly in the context of containerized applications and microservices.

# Here are key features and components of Prometheus:

|**Time-Series Data Model**|Prometheus follows a time-series data model, where metrics are identified by a combination of metric name and key-value pairs (labels). This allows for efficient querying and analysis of time-series data.|
|-------------------------|-----------------------------|
|**Data Scraping**|Prometheus collects metrics from monitored targets through a process called scraping. It regularly pulls metrics from HTTP endpoints exposed by the monitored services. This pull-based approach allows Prometheus to discover and monitor new services dynamically.|
**PromQL (Prometheus Query Language)**|PromQL is the query language used by Prometheus to retrieve and manipulate time-series data. It provides powerful capabilities for filtering, aggregating, and transforming metrics, enabling users to create meaningful dashboards and alerts.|
|**Multi-Dimensional Data Collection**|Prometheus collects various types of metrics, including counters, gauges, and histograms. It supports multi-dimensional data, allowing users to add labels to metrics for more granular and flexible querying.|
|**Alerting**|Prometheus includes a built-in alerting system. Users can define alerting rules based on PromQL queries, and Prometheus evaluates these rules regularly. When an alert condition is met, Prometheus can trigger notifications or integrate with external alerting systems|
|**Service Discovery**|Prometheus supports service discovery mechanisms, enabling automatic detection and monitoring of new instances of services as they come and go. This is crucial in dynamic environments, such as those using container orchestration platforms like Kubernetes|
|**Storage**|Prometheus stores time-series data locally in a time-series database. The local storage is optimized for efficient querying, and retention policies can be configured to control how long data is retained|
|**Exporters**|Prometheus can collect metrics from various sources using exporters. Exporters are small programs that expose metrics in a format that Prometheus can scrape. There are many official and third-party exporters available for popular software and systems|
|**Grafana Integration**|While Prometheus has a basic web interface for querying and visualizing data, it is commonly used in conjunction with visualization tools like Grafana. Grafana allows users to create rich and customizable dashboards using data from Prometheus|
|**Community and Ecosystem**|Prometheus has a vibrant open-source community and is part of the CNCF ecosystem. It is widely adopted in the cloud-native and DevOps communities, and its ecosystem includes integrations with other monitoring tools and platforms|


***

# What is Graphana 


Grafana is an open-source platform for monitoring and observability that provides a flexible and powerful way to visualize and analyze metrics, logs, and other data. Originally focused on time-series data, Grafana has evolved into a comprehensive observability platform that can integrate with various data sources, including databases, logs, and other monitoring systems. It is widely used in the DevOps and IT communities for creating dashboards, exploring data, and setting up alerts.

**Here are key features and components of Grafana**:

|**Data Source Integration**|Grafana supports a wide range of data sources, including popular time-series databases like Prometheus, InfluxDB, Graphite, and others. It can also integrate with relational databases, log storage systems, and cloud-based services|
|----------------------------------|---------------------------------------------------|
|**Dashboard Creation**|Users can create highly customizable dashboards to visualize and analyze data. Grafana provides a drag-and-drop interface for adding panels, graphs, tables, and other visualizations to dashboards. Dashboards can contain panels from different data sources|
|**Plugins and Extensions**|Grafana has a rich ecosystem of plugins and extensions that extend its functionality. Users can install plugins to add support for additional data sources, integrate with alerting systems, or enhance visualization options|
|**Query Editor**|The query editor in Grafana allows users to construct queries using the specific syntax of the selected data source. It supports various query languages, such as PromQL for Prometheus or SQL for relational databases|
|**Alerting and Notifications**|Grafana provides a robust alerting system that allows users to set up alert rules based on the data being monitored. When alert conditions are met, Grafana can trigger notifications via channels like email, Slack, or others|
|**Templating**|Grafana supports templating, enabling dynamic dashboards that can adapt to changing conditions. Templating allows users to create variables in dashboards, making it easier to switch between different hosts, time ranges, or other parameters|
|**User Authentication and Authorization**|Grafana offers user authentication and authorization features. It supports integration with various authentication providers, including OAuth, LDAP, and others. Role-based access control (RBAC) allows administrators to define user roles and permissions|
|**Annotations**|Annotations in Grafana allow users to mark specific points or events on graphs, helping to correlate changes in metrics with external events or activities. Annotations can be manual or generated automatically|
|**Grafana Explore**|Grafana Explore is a feature that allows users to interactively explore and query their data. It supports ad-hoc queries and is particularly useful for investigating and troubleshooting issues|
|**Community and Integrations**|Grafana has a large and active community, and it is widely adopted in various industries. It integrates with many other tools and platforms in the observability and monitoring ecosystem|


***

# Monitoring Websites using Grafana and Prometheus

we are going to set up a Grafana and Prometheus server to monitor running websites 


**Network Setup**

1. Blackbox Setup
  
2. Prometheus setup
  
3. Grafana setup

***

# Folder Structure

Let’s clone the repo which contains the source code.

**git clone https://github.com/cmjagtap/Website-Monitoring**

![image](https://github.com/avengers-p7/Documentation/assets/156644891/8921d93f-174e-4401-ba4b-f26df7c1869a)

***

# Folder Structure

**blackbox_exporter-0.18**.-: Contains a black-box exporter binary and configuration file.

**docker-compose.yml**: It’s a docker file to set up a Grafana and Prometheus server.

**Prometheus.yml**: Prometheus configuration file to scrap data from the black-box exporter.

**dashboard.json**: contains Grafana dashboard configuration

***

# Blackbox Exporter Setup

The black-box exporter allows BlackBox probing of endpoints over HTTP, HTTPS, DNS, TCP, and ICMP.

Navigate to the blackbox_exporter-0.18.0.Linux-amd64 directory. blackbox.yml is the configuration file for a black-box exporter. Here we are going to use the HTTP GET module

![image](https://github.com/avengers-p7/Documentation/assets/156644891/63c53ba8-9013-4201-b56f-bcb5c695bce2)


**Let’s start the Blackbox exporter with the following command**

**./blackbox_exporter --config.file=blackbox.yml &> output.log &**

The black-box exporter should start in the background.

We can check the black-box status using the following command

**netstat -tunlp**

![image](https://github.com/avengers-p7/Documentation/assets/156644891/cec72c0d-6f02-40d3-9a12-69a425047ea9)


Now Let’s navigate to the browser and hit the following address http://localhost:9115, we can see black-box metrics.

![image](https://github.com/avengers-p7/Documentation/assets/156644891/76aead40-4cf4-4b79-ba12-733eeebbff62)


***

# Grafana and Prometheus Setup

Let’s navigate back to the Website-Monitoring directory. prometheus.yml file contains a docker script to fetch metrics from the black-box exporter.

![image](https://github.com/avengers-p7/Documentation/assets/156644891/8568341a-9ce9-4c88-ad66-eabd6b5e6946)

In the targets, you can add your websites.

Here, I am using **github.com, hackerrank.com, google.com**to demonstrate the demo.

# Please change your blackbox exporter IP address in above configuration file.

**docker-compose.yml** file contains docker script to pull the image and start Grafana and Prometheus.

![image](https://github.com/avengers-p7/Documentation/assets/156644891/c9a0df00-3ace-4ba8-8ab8-8934b5c1289a)


# Execute the following command to start Grafana and Prometheus

**cd Website-Monitoring**

 **docker-compose up -d**

 After this command,

Grafana docker container started on port 3000

Prometheus docker container started on port 9090

![image](https://github.com/avengers-p7/Documentation/assets/156644891/b816a364-1061-4700-ba6e-e6c9928adcde)


# Use the following command to see running containers

**docker ps -a**

![image](https://github.com/avengers-p7/Documentation/assets/156644891/2da6ed45-43a3-404a-a748-41ab0207d3d1)


# Prometheus

Let’s navigate to Prometheus address http://localhost:9090/targets we should see all the black-box in the running status as follows.

![image](https://github.com/avengers-p7/Documentation/assets/156644891/9f4a5e04-45a6-42bb-887d-ba97eeded7ce)

**The above figure shows we have completed the Prometheus setup**

# Grafana

Let’s navigate to Prometheus address http://localhost:3000 we should see the Grafana login screen as follows

![image](https://github.com/avengers-p7/Documentation/assets/156644891/1131869d-4381-4ace-bc5c-29475fdf9386)


Grafana Login Screen

**The Login credentials of Grafana are as follows**

![image](https://github.com/avengers-p7/Documentation/assets/156644891/bd87cbdb-2764-43b8-bdbd-9179f4deb348)


After Login we can see the following screen

![image](https://github.com/avengers-p7/Documentation/assets/156644891/1c8481c1-cc20-42cf-b89e-392a685e17e2)


**Grafana Welcome Page**

On the left side, we can see the Setting icon, click on the icon, and then click on Data Sources.

![Screenshot from 2024-01-30 22-54-43](https://github.com/avengers-p7/Documentation/assets/156644891/53b32a03-1c09-4074-9dcd-33dcc39aa5c6)


Then select Prometheus.

![Screenshot from 2024-01-30 22-54-43](https://github.com/avengers-p7/Documentation/assets/156644891/e336581b-2749-4c42-af18-8fbe548179df)


Add the local host address or Prometheus server address with the listening port.

![Screenshot from 2024-01-30 22-57-10](https://github.com/avengers-p7/Documentation/assets/156644891/1f2ac600-4a6c-426a-a2ce-47ed48c7f9b6)


Select HTTP Method method to GET then save and test.

![image](https://github.com/avengers-p7/Documentation/assets/156644891/0206b062-a29d-4c99-9002-20a045471bd0)

![image](https://github.com/avengers-p7/Documentation/assets/156644891/5d3dd248-94b1-4d56-be1c-2cd10665edb2)


**Here** We are going to import the existing website monitoring dashboard.

Select upload JSON file and upload the dashboard.json file from the Website-Monitoring directory.

The following screen should appear on the screen.

![image](https://github.com/avengers-p7/Documentation/assets/156644891/9d7f8ed4-3a26-4d88-8979-3834898c28a6)


After some time all the data will get updated on the dashboard.

We can see the website is up and running.

***

# Clean up

Execute the following script to clean all docker containers and remove BlackBox exporter.


![image](https://github.com/avengers-p7/Documentation/assets/156644891/3aaf28c5-e384-4e7f-85f5-f231764bd257)

***

# Conclusion 

Jenkins is the go-to tool to automate the testing, analysis, and code deployment. It enables organizations to set up fully automated, multi-step CI/CD pipelines that enhance productivity and reduce time to production. Monitoring a Jenkins instance allows you to increase its performance, predict malfunctions, and avoid downtime.

***

# Contact Information

| Name | Email ID |
|----- | -------- |
| NIDHI BHARDWAJ | nidhi.bhardwaj.snaatak@mygurukulam.co |


***

# Reference

| Reference  | Description |
| ---------  | ----------- |
|https://www.site24x7.com/learn/jenkins-performance-monitoring.html| link for Documentation |
|https://www.site24x7.com/learn/jenkins-performance-monitoring.html |link for setup |





























