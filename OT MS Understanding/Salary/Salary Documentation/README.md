
# Salary API Documentation

| **Author** | **Created on** | **Last updated by** | **Last edited on** | **Reviwer L0** |**Reviwer L1** |**Reviwer L2** |
|------------|----------------|----------------------|---------------------|---------------|---------------|---------------|
| Pravesh Kumar      | 12-11-24      | Pravesh Kumar             | 16-11-24           | Khushi, Shikha  | | |

## Table of Contents
- [Salary-API overview](#salary-api-overview)
- [Purpose of the Salary API](#purpose-of-the-salary-api)
- [Architecture](#architecture)
- [ScyllaDB](#scylladb)
- [Redis](#redis)
- [Migrate](#migrate)
- [Maven](#maven)
- [Swagger](#swagger)
- [Conclusion](#conclusion)
- [Contact Information](#contact-information)
- [References](#references)

  
## Salary-API overview

The Salary API is a vital microservice in the OT-Microservices project, handling employee salary data and transactions. It operates independently, integrating with other services like Employee and Attendance APIs. Designed for high performance, scalability, and reliability, it is optimized for cloud environments and follows modern development practices.

## Purpose of the Salary API

### The primary purpose of the Salary API

- Manage and process salary records for employees.

- Integrate easily with other microservices within the OT-Microservices ecosystem.
  
- Support efficient data storage, retrieval, and calculation related to employee compensation.
  
- It is essential in automating payroll processes, enhancing accuracy in employee compensation records, and simplifying the financial operations within the organization.

### Supported features of the Salary API

The system uses Spring Boot with Tomcat, ScyllaDB for salary data storage, Redis for caching, and Prometheus/OpenTelemetry for monitoring. Swagger provides API documentation, and database migrations are handled using the Migrate tool.

### Components of the Salary API

- [ScyllaDB](https://www.scylladb.com/)

- [Redis](https://redis.io/)

- [Migrate](https://github.com/golang-migrate/migrate)

- [Maven](https://maven.apache.org/)

## Architecture

![Screenshot 2024-11-13 at 11 47 43 PM](https://github.com/user-attachments/assets/4b74d22c-97f8-4d12-8636-e75c9c04d350)

## ScyllaDB

ScyllaDB is a high-performance NoSQL database, designed as a drop-in replacement for Apache Cassandra. It offers low-latency, high-throughput storage, optimized for scalable applications and efficiently utilizes modern multi-core CPUs.

### Why ScyllaDB

ScyllaDB offers high performance with low latency, making it ideal for real-time applications. It is compatible with Cassandra, supports automatic data sharding, and minimizes the need for manual tuning by automating database management tasks.

### Use Cases

ScyllaDB is used in IoT applications for real-time data collection from millions of devices and in financial services for processing large transaction volumes with low latency, supporting fraud detection and analytics.
  
![ScyllaDB-Manager](https://github.com/user-attachments/assets/4d7403a8-d947-4390-bf26-d1d032302498)

## Redis

Redis is an open-source, in-memory data store used for caching, session management, and messaging. It supports various data structures and provides fast read and write performance.

### Why Redis

Redis is used for caching, session management, real-time messaging through Pub/Sub, and data persistence, allowing quick data retrieval, reduced load on databases, and recovery after restarts.

### Use Cases

Redis is used for web caching to improve response times, leaderboard systems for ranking in gaming or social media, and real-time analytics for event data aggregation in monitoring or ad tech applications.

![9c501ae0-6878-464e-bb4c-f61b40c6f8be](https://github.com/user-attachments/assets/0c103a35-b906-4df0-84ce-00bc03f7d3c6)

## Migrate

Database migration tools like migrate are essential for managing schema changes in evolving applications, particularly in Go environments, ensuring consistent, version-controlled schemas across different environments.

### Why Migrat

Database migration tools provide schema versioning, ensure consistency across environments, and allow reversible changes for safe deployment and rollback of schema modifications.

### Use Cases

Database migration tools enable schema evolution without manual scripts, automate migrations in CI/CD pipelines, and manage multi-tenant applications with separate databases or schemas for each tenant.

## Maven

Maven is a build automation and dependency management tool for Java applications, using a declarative configuration file (pom.xml) to simplify project builds and dependency resolution.

### Why Maven

Maven automates dependency management, ensures build consistency, promotes standardized project structures, and supports plugins for tasks like testing, packaging, and deployment.

### Use Cases


Maven automates Java project builds, handles dependency resolution, manages multi-module projects, and integrates with CI tools like Jenkins for automated build and testing.

![maven-architecture-1024x250](https://github.com/user-attachments/assets/33814d03-39b7-4e99-bb55-e5173eb61dfe)

## Swagger

Swagger is an open-source toolset for designing, building, documenting, and testing RESTful APIs. It leverages the OpenAPI Specification (OAS) to standardize API definitions and provide interactive documentation.

### Key Benefits

Swagger UI provides interactive API documentation, uses the OpenAPI Specification for standardization, generates client SDKs in multiple languages, and enhances collaboration between frontend and backend teams.
  
### Core Components

Swagger tools include Swagger UI for interactive API documentation, Swagger Editor for creating OpenAPI specs, Swagger Codegen for generating client SDKs and server stubs, and the OpenAPI Specification (OAS) for standardizing REST API documentation.

### Common Use Cases

Swagger tools offer interactive API documentation, endpoint testing, client SDK generation, and enhance team collaboration by providing a unified source for API specifications.

## Conclusion

The Salary API in the OT-Microservices system efficiently manages salary transactions, using ScyllaDB for scalable storage, Redis for caching, Migrate for version control, Swagger for documentation, and Maven for builds. It offers high performance, seamless integration with other microservices, and supports scalability and continuous deployment.


# Contact Information

| **Name** | **Email address**            | **Github ID**
|----------|-------------------------------|-------------------|
| Pravesh Kumar    |  pravesh.kumar611@gmail.com           | Pravesh899 |

# References

| **Link** | **Description**            |
|----------|-------------------------------|
| [What is Redis and How Does it Work? - Medium](https://medium.com/@ayushsaxena823/what-is-redis-and-how-does-it-work-cfe2853eb9a9)   |  Overview of Redis' structure and functions.          |
| [ScyllaDB Installation Guide](https://opensource.docs.scylladb.com/stable/getting-started/install-scylla/install-on-linux.html)   | Comprehensive guide for installing ScyllaDB on Linux. |
| [Swagger](https://swagger.io/docs/specification/v2_0/what-is-swagger/)   | Swagger Docs |
| [Maven](https://maven.apache.org/what-is-maven.html)   | Maven Introduction |


