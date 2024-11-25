# ScyllaDB Documentation

| **Author** | **Created on** | **Version** | **Last edited on** | **L0 Reviewer** |
|------------|----------------|-------------------|---------------------|----------|
| Anjali Dhiman  | 12-11-24      | V1  | 15-11-24           | Shreya Jaiswal |
| Anjali Dhiman  | 12-11-24      | V2  | 17-11-24            | Khushi Malhotra|
| Anjali Dhiman  | 12-11-24      | V3  | 21-11-24            | Khushi Malhotra|

## Table of Contents
- [Purpose](#purpose)
- [Introduction](#introduction)
- [Features](#features)
- [System Requirements](#system-requirements)
- [Important Ports](#important-ports)
- [Architecture](#architecture)
- [Advantages & Disadvantages](#Advantages--Disadvantages)
- [Installation](#Installation)
- [Configuration](#configuration)
- [Monitoring](#monitoring)
- [Use Cases](#use-cases)
- [Conclusion](#conclusion)
- [Contacts](#contacts)
- [References](#references)

## Purpose
ScyllaDB is a high-performance NoSQL database that handles large-scale data with low latency and high throughput. Fully compatible with Apache Cassandra, it offers easy migration and efficient resource management. ScyllaDB scales horizontally and ensures high availability through data replication, automatic failover, and multi-region support.In the OT Microservice project, ScyllaDB serves as the primary database for the Employee and Salary APIs, providing fast and reliable data storage while supporting scalable growth. Its seamless integration with the project ensures efficient handling of data and high system performance.

## Introduction
## What is ScyllaDB?
![image](https://github.com/user-attachments/assets/7cdf2df0-9bfa-42f3-98f3-056b5899bbe1)

ScyllaDB is a high-performance distributed NoSQL database that delivers  low-latency, high-throughput data processing for modern applications. It is designed as a drop-in replacement for Apache Cassandra, offering compatibility with Cassandra's data model and query language (CQL) while significantly boosting performance and scalability. ScyllaDB is written in C++, providing efficiency benefits over Java-based solutions, and employs a shared-nothing architecture that enables seamless horizontal scalability across clusters of commodity hardware. With its focus on performance, scalability, and compatibility, ScyllaDB is well-suited for use cases requiring real-time data processing, such as IoT, analytics, and online transaction processing (OLTP) applications.

## Why we choose Scylladb?
We chose ScyllaDB for the Employee API because it’s a NoSQL database that can handle any type of data, whether structured or unstructured. It’s fast, reliable, and perfect for managing large employee records (Employee ID, Employee Name, Employee Email ID, Phone no., Job Role) and handling high traffic without delays. ScyllaDB easily integrates with Redis, allowing us to use Redis for caching frequently accessed data, which makes the API even faster. ScyllaDB scales easily and works well in real time, so our API stays quick and responsive.
## Features 

|       Features     |             Description                     |
|--------------------|-----------------------------------------|
| **Scalability:**   | It is designed to scale horizontally across multiple nodes seamlessly.                  | 
| **Performance:**   | It is optimized for low-latency and high-throughput workloads.         |
| **Shared-Nothing Architecture:**   | It follows a shared-nothing architecture where each node in the cluster operates independently.             |
| **Fault Tolerance:**   | It provides fault tolerance through replication. Data is automatically replicated across multiple nodes in a cluster. |
| **Flexibility:**     | ScyllaDB supports dynamic scaling, allowing you to add or remove nodes from the cluster without downtime.   |
| **Community and Enterprise Support:**     | It is available in both open-source and enterprise editions. |  


## System Requirements 

|   System Requirement              |             Minimum                     |
|-----------------------------------|-----------------------------------------|
| Processor                         |         Dual-Core  / t2 medium                     | 
| RAM                               |            4 GB                         |
| Disk Space                        |            20 GB                        |
| OS Required (Linux Distributions) | Ubuntu 24.04/22.04 LTS, Debian 10/11, Rocky 8/9 |



## Important Ports

 | Port   | Description                  |
|--------|------------------------------|
| 7000   | Inter-node communication     |
| 7001   | TLS inter-node communication |
| 7199   | JMX monitoring                |
| 9042   | CQL native transport          |
| 9142   | SSL CQL native transport      |
| 9160   | Thrift client API             |


## Architecture

- **Sharded Architecture:** ScyllaDB employs a sharded architecture, where each CPU core is responsible for one or more shards of the data. This design eliminates the need for a central coordination node, improving scalability and performance.
- **Data Model:** ScyllaDB uses a wide-column store, similar to Cassandra, with tables that consist of rows and columns. The primary key consists of a partition key and optional clustering columns.
- **Replication and Consistency:** ScyllaDB supports different consistency levels, including QUORUM, LOCAL_QUORUM, ONE, and ALL, allowing you to balance between availability and consistency.
- **Write and Read Path:** ScyllaDB implements a write path optimized for low latency. Writes are initially written to a memory table (MemTable) and later flushed to disk (SSTable). The read path uses a combination of MemTable, SSTable, and Bloom Filters for efficient data retrieval.


## Advantages & Disadvantages


| **Advantages**                                                              | **Disadvantages**                                                          |
|-----------------------------------------------------------------------------|---------------------------------------------------------------------------|
| **High Performance**: Optimized for low-latency and high-throughput workloads. | **Resource Intensive**: Requires significant CPU and memory for optimal performance. |
| **Scalable**: Easily scales horizontally to handle large data and traffic.    | **Complex Setup**: Initial configuration can be tricky and may need fine-tuning. |
| **Fault Tolerant**: Independent nodes with automatic data replication for high availability. | **Smaller Ecosystem**: Fewer third-party tools and community support compared to Cassandra. |
| **Cassandra Compatibility**: Easy migration for users familiar with Cassandra. | **Learning Curve**: New users may take time to adapt to ScyllaDB's architecture. |
| **Flexible**: Allows dynamic scaling without downtime.                         | **Limited OS Support**: Primarily supports Linux, not all environments. |
| **Support**: Both open-source and enterprise support available.              | **Java Dependency**: Requires Java (JDK 11 or later).                    |




## Installation 
Follow the link for the installation Document:
(https://github.com/avengers-p11/Documentation/blob/main/OT%20MS%20Understanding/ScyllaDB/ScyllaDB%20POC/README.md)

## Configuration

Configuring ScyllaDB involves setting up cluster topology, replication factors, and performance tuning parameters. Detailed configuration guides can be found in the [ScyllaDB Configuration Guide](https://opensource.docs.scylladb.com/stable/getting-started/system-configuration.html).



## Monitoring

- ScyllaDB offers robust monitoring and management tools, including integration with Prometheus and Grafana for real-time metrics and alerting. The JMX interface provides additional management capabilities.
- ScyllaDB Monitoring Stack is a full stack for ScyllaDB monitoring and alerting. The stack contains open source tools including Prometheus and Grafana, as well as custom ScyllaDB dashboards and tooling.
- follow the link for more detailed informaton: [Monitoring stack](https://monitoring.docs.scylladb.com/stable/)

## Use Cases 

ScyllaDB is ideal for various applications, including:

- **IoT:** Handling large volumes of data from connected devices in real-time.
- **Analytics:** Providing fast data processing and querying capabilities for large datasets.
- **Online Transaction Processing (OLTP):** Ensuring low-latency and high-throughput for transactional applications.
- **E-commerce:** Managing user sessions, product catalogs, and transaction data with high availability.


## Conclusion
In the OT-Microservices architecture, ScyllaDB is utilized in the Employee API as the primary database solution. It enables efficient storage and retrieval of employee-related data with features like high performance, scalability, and low latency. Its Cassandra-compatible architecture ensures easy integration, while distributed and fault-tolerant operations make it reliable for high-demand use cases.

## Contacts

| Name| Email Address      |
|-----|--------------------------|
| Anjali Dhiman | anjali.dhiman.snaatak@mygurukulam.co |

| GitHub | URL |
|----------|---------|
|  Anjaliopstree  |  https://github.com/Anjaliopstree  |


## References

| Source                                                                                     | Description                                |
| ------------------------------------------------------------------------------------------ | ------------------------------------------ |
| [ScyllaDB Installation Guide](https://opensource.docs.scylladb.com/stable/getting-started/install-scylla/install-on-linux.html) | Comprehensive guide for installing ScyllaDB on Linux. |
| [ScyllaDB Configuration Guide](https://www.scylladb.com/download/?platform=ubuntu-22.04&version=scylla-5.4#open-source) | Step-by-step instructions for configuring ScyllaDB. |
| [Application Template ](https://github.com/OT-MICROSERVICES/documentation-template/wiki/Application-Template) | Document format followed from this link   | 
