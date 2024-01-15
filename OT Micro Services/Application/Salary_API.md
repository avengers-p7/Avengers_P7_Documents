# Salary API

| Author | Created on  | Version    | Last Updated by | Last Updated on |
| -------- | ------- | -------------- | --------------| ---------------- |
| Harshit Singh  | 10-01-2024  | 1.0   | Harshit Singh | 15-01-2024 |

## Purpose

Salary API is a Java-based microservice which is responsible for all the salary-related transactions and records in **[OT-Microservices](https://github.com/OT-MICROSERVICES)** stack. The application is platform-independent and can be run on multiple operating systems. **[Java Runtime](https://www.java.com/en/download/manual.jsp)** would be required to run this application.

### Key Components  

- **Spring boot** based web framework, which uses tomcat as a web server.
- **ScyllaDB** is used as the primary database for storing all the salary data.
- **Redis** as cache manager to store the cache response.
- **Prometheus and Open-telemetry** metrics support for monitoring and observability.
- Database migration using the tool called **[migrate](https://github.com/golang-migrate/migrate)**.

## Pre-Requisites

The Salary API application has some database, cache manager and package dependencies. Some of the dependencies are optional and some are mandatory. To compile the application, we only need `maven` as a build tool, but for running the application following things are required:-

- **[ScyllaDB](https://www.scylladb.com/)**
- **[Redis](https://redis.io/)**
- **[Migrate](https://github.com/golang-migrate/migrate)**
- **[Maven](https://maven.apache.org/)**
- **[Java 17](https://www.digitalocean.com/community/tutorials/how-to-install-java-with-apt-on-ubuntu-22-04)**

Maven will be used as a package manager to download specific versions of dependencies to run the Salary API.

## Architecture

![image](https://github.com/avengers-p7/Documentation/assets/156056444/7ef9b753-4127-47c0-b692-bb1a97e228b6)

## Application

For building the Salary API application, we can use `make` commands with our **[Makefile](./Makefile)**. But first, we need to install the dependencies which can be simply done using the `make` command.

```shell
make build
```

For building the docker image artifact of the attendance API, we can invoke another make command.

```shell
make docker-build
make docker-push
```

Also, Salary API contains different test cases and code quality-related integrations. To check the code quality, we can use `checkstyle` plugin with Maven. Also, for code coverage and unit testing, we are using Jacoco, and Junit respectively.

```shell
make fmt
make test
```

```shell
mvn checkstyle:checkstyle
# For unit testing and code coverage
mvn test
```

The test cases are present in **[src/test/java/com/opstree/microservice/salary](./src/test/java/com/opstree/microservice/salary)**. For dev testing, the Swagger UI can be used for sample payload generation and requests. The swagger page will be accessible on http://localhost:8080/salary-documentation.

Before running the application, we have to make sure our mandatory database (ScyllaDB and Redis) is up and running. Configuration properties will be configured inside **[application.yml](./src/main/resources/application.yml)** file. Also, once the property file is defined and configured properly, we need to run migrations to create database, schema etc. The connection details for migration are available in **[migration.json](./migration.json)**.

```shell
make run-migrations
```

Once the schema, table and database are configured, we can start our application using Java runtime.

```shell
java -jar target/salary-0.1.0-RELEASE.jar
```

## Endpoint Information

| **Endpoint**                   | **Method** | **Description**                                                                               |
|--------------------------------|------------|-----------------------------------------------------------------------------------------------|
| `/api/v1/salary/create/record` | POST       | Data creation endpoint which accepts certain JSON body to add salary information in database  |
| `/api/v1/salary/search`        | GET        | Endpoint for searching data information using the params in the URL                           |
| `/api/v1/salary/search/all`    | GET        | Endpoint for searching all information across the system                                      |
| `/actuator/prometheus`         | GET        | Application healthcheck and performance metrics are available on this endpoint                |
| `/actuator/health`             | GET        | Endpoint for providing shallow healthcheck information about application health and readiness |

## Contact Information

[Opstree Opensource](mailto:opensource@opstree.com)
