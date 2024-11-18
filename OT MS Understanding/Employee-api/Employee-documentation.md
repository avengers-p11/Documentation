# Employee API Documentation 

| Created/Modified | Version | Author               | Comment         | Reviewer      |
|-------------------|---------|----------------------|-----------------|------------------|
| 12-11-2024        | V1      | Anjali Dhiman | Initial Commit LO  | Shreya Jaiswal  |
| 18-11-2024        | V2      | Anjali Dhiman | L0 Feedback    |  Khushi Malhotra |


## Table of Contents
1. [Purpose](#purpose)
2. [Introduction](#introduction)
3. [Architecture](#architecture)
4. [Pre-requisites](#pre-requisites)
5. [Features](#features)
6. [Tools Used](#tools-used)
7. [Database and Caching](#database-and-caching)
   - [1.ScyllaDB](#1.scylladb)
   - [2.Redis](#2.redis)
8. [Conclusion](#conclusion)
9. [Contact Information](#contact-information)
10. [Reference Links](#reference-links)

## Purpose
Employee API is a Go-based microservice designed to manage all employee-related data and transactions within the OT-Microservices stack. It provides a centralized backend service for storing and accessing employee information and can run across multiple operating systems, as it is platform-independent. The application requires the Go runtime for execution.


## Introduction

The Employee API is a Golang-based REST API designed for managing employee information. This application integrates ScyllaDB as its primary database and uses Redis for caching. The API is built with the Gin framework, which ensures fast and scalable operations for RESTful transactions.


## Architecture
![image](https://github.com/user-attachments/assets/50d18e52-0e94-48d3-9db7-28ba439e819f)

## Pre-requisites
To get started, ensure you have the following installed and set up on your machine:

- Go (Golang) - Version 1.18
- ScyllaDB - Make sure you have an accessible ScyllaDB instance with the appropriate keyspaces and tables for employee data and RAM of VM (20).
- Redis (optional) - For caching functionality, an active Redis instance is recommended but not required.
These components must be accessible over the network or from within the same environment as the API.



## Features

| Feature                     | Description                                                                                          |
|-----------------------------|------------------------------------------------------------------------------------------------------|
| **CRUD Operations**         | Full Create, Read, Update, and Delete functionality for managing employee records.                  |
| **High-Performance Storage**| Built on ScyllaDB, optimized for distributed, high-throughput workloads with a Cassandra-compatible interface. |
| **Redis Caching**           | Optional integration with Redis to cache frequently requested employee data, improving response times and reducing database load. |
| **API Documentation**       | Self-updating, interactive API documentation powered by Swagger, making it easy to test and understand endpoints. |
| **Scalable and Lightweight**| Built with Go for efficiency and concurrency, enabling scalability and handling of high request volumes. |



## Tools Used

| Tool             | Description                                                                                                   |
|-------------------|---------------------------------------------------------------------------------------------------------------|
| **Go (Golang) 1.22** | The primary language for development, chosen for its performance, simplicity, and efficient handling of concurrent requests. |
| **ScyllaDB**        | A distributed, highly available, and Cassandra-compatible NoSQL database optimized for low-latency, high-throughput applications. |
| **Redis**           | An in-memory data store used for caching frequently accessed data, reducing database load and improving API response times. |
| **Swagger**         | Automatically generates API documentation accessible and interactable through a web interface.              |
| **Make Command**    | A build automation tool for running repetitive tasks (e.g., building the app, running migrations) via a Makefile. |
| **Migrate**         | A database migration tool ensuring schema consistency with the application’s requirements.                  |
| **JQ**              | A command-line JSON processor for parsing and handling JSON data.                                          |




## Database and Caching
This microservice utilizes ScyllaDB and Redis to efficiently handle data storage and retrieval. Each of these components serves a distinct purpose within the application:

### 1. ScyllaDB
ScyllaDB is the primary persistent database for the Employee API, responsible for storing all core employee-related data, such as employee details, locations, and designations.

### Why ScyllaDB?

ScyllaDB is a high-performance NoSQL database compatible with Apache Cassandra, optimized for lower latencies and higher throughput, making it ideal for applications requiring fast data access at scale. Its distributed architecture allows it to manage large volumes of data across multiple nodes, ensuring scalability, high availability, and durability. Additionally, ScyllaDB’s fault-tolerant design supports replication and partitioning, providing resilience to failures and safeguarding data even during node outages. This database was chosen for the Employee API to deliver a reliable, efficient storage solution capable of handling substantial data loads as the employee dataset grows.
For a detailed setup, see the (https://github.com/avengers-p11/Documentation/blob/main/OT%20MS%20Understanding/ScyllaDB/Scylladb-documentation.md)

### 2. Redis
Redis serves as an in-memory caching layer to enhance performance by storing frequently accessed data temporarily.


### Why Redis?
Redis operates entirely in-memory, enabling ultra-fast data access, ideal for caching and reducing database load by minimizing repeated ScyllaDB queries. It supports flexible caching strategies, such as Least Recently Used (LRU) eviction, to keep cache data relevant. While optional, Redis enhances API response times, boosting efficiency by caching frequently accessed data.
For a detailed setup, see the (https://github.com/avengers-p11/Documentation/blob/main/OT%20MS%20Understanding/Redis/Redis%20Documentation/README.md#rich-data-structures)

## Conclusion
The Employee API is a robust microservice designed to manage employee data within the OT Microservices architecture. It integrates seamlessly with the Attendance API and Salary API, and leverages ScyllaDB for high-performance data storage. By incorporating Redis for caching, Swagger for API documentation, and Prometheus for monitoring, it ensures efficient operations and scalability. This API is intended to serve as a backbone for employee-related services, providing easy extensibility and maintainability.

We encourage contributions, bug reports, and feedback to help improve the overall functionality and usability of the project. For any issues or feature requests, feel free to open an issue or pull request.

## Contact Information
| Name| Email Address      |
|-----|--------------------------|
| Anjali Dhiman | anjalidhiman.as@gmail.com |

| GitHub | URL |
|----------|---------|
|  Anjaliopstree  |  https://github.com/Anjaliopstree  |


## Reference Links
| Links | Description      |
|-----  |--------------------------|
| https://github.com/OT-MICROSERVICES/documentation-template/wiki/Application-Template | documentation-template |
| https://github.com/OT-MICROSERVICES/employee-api/tree/main?tab=readme-ov-file | Employee api | 
| https://www.simplyblock.io/glossary/what-is-scylladb/    | Scylladb |
| https://www.geeksforgeeks.org/introduction-to-redis-server/ | Redis |
