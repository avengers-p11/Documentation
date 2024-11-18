# ScyllaDB Documentation

| **Author** | **Created on** | **Version** | **Last edited on** | **Reviewer** |
|------------|----------------|-------------------|---------------------|----------|
| Anjali Dhiman  | 12-11-24      | V1.2  | 15-11-24           | Shreya Jaiswal, Khushi Malhotra |

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
ScyllaDB is a high-performance, NoSQL database designed to handle large-scale data applications with low latency and high throughput, even under heavy workloads. Built in C++ for optimized performance, it is fully compatible with Apache Cassandra, enabling straightforward migrations with minimal code changes while using the same Cassandra Query Language (CQL) and drivers. ScyllaDB is crafted to make efficient use of system resources through asynchronous I/O and avoids Java-based garbage collection, ensuring consistent performance with lower CPU and memory requirements. Known for its scalability, ScyllaDB enables seamless horizontal scaling, making it suitable for applications that need to accommodate rapid data growth and fluctuating traffic demands. Additionally, it incorporates robust fault tolerance features, including data replication, automatic failover, and multi-region support, to ensure continuous data availability and reliability in production environments.

## Introduction
## What is ScyllaDB?
![image](https://github.com/user-attachments/assets/7cdf2df0-9bfa-42f3-98f3-056b5899bbe1)

ScyllaDB is a high-performance distributed NoSQL database that delivers  low-latency, high-throughput data processing for modern applications. It is designed as a drop-in replacement for Apache Cassandra, offering compatibility with Cassandra's data model and query language (CQL) while significantly boosting performance and scalability. ScyllaDB is written in C++, providing efficiency benefits over Java-based solutions, and employs a shared-nothing architecture that enables seamless horizontal scalability across clusters of commodity hardware. With its focus on performance, scalability, and compatibility, ScyllaDB is well-suited for use cases requiring real-time data processing, such as IoT, analytics, and online transaction processing (OLTP) applications.

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

- Sharded Architecture: ScyllaDB employs a sharded architecture, where each CPU core is responsible for one or more shards of the data. This design eliminates the need for a central coordination node, improving scalability and performance.
- Data Model: ScyllaDB uses a wide-column store, similar to Cassandra, with tables that consist of rows and columns. The primary key consists of a partition key and optional clustering columns.
- Replication and Consistency: ScyllaDB supports different consistency levels, including QUORUM, LOCAL_QUORUM, ONE, and ALL, allowing you to balance between availability and consistency.
- Write and Read Path: ScyllaDB implements a write path optimized for low latency. Writes are initially written to a memory table (MemTable) and later flushed to disk (SSTable). The read path uses a combination of MemTable, SSTable, and Bloom Filters for efficient data retrieval.


## Advantages & Disadvantages

|Advantages|	Disadvantages|
|----------|----------------|
|**High Performance:** ScyllaDB is optimized for low-latency and high-throughput workloads, making it suitable for real-time data processing.	|**Resource Intensive:** ScyllaDB can be resource-intensive, requiring significant CPU and memory resources to achieve optimal performance.|
|**Scalability:** Designed to scale horizontally across multiple nodes seamlessly, enabling it to handle large volumes of data and high traffic.	|**Complex Configuration:** Initial setup and configuration can be complex, requiring careful tuning to achieve the best performance.|
|**Shared-Nothing Architecture:** Each node operates independently, providing fault tolerance and high availability through automatic data replication.	|**Limited Ecosystem:** Compared to more established databases like Cassandra, ScyllaDB has a smaller ecosystem of third-party tools and community support.|
|**Compatibility:** Offers compatibility with Apache Cassandra's data model and CQL, making it easier for users to migrate from Cassandra.	|**Learning Curve:** Users familiar with traditional RDBMS or other NoSQL databases may face a learning curve when adapting to ScyllaDB's architecture and concepts.|
|**Flexibility:** Supports dynamic scaling, allowing nodes to be added or removed without downtime.	|**Limited OS Support:** Primarily supports Linux distributions (Ubuntu, Debian, Rocky), which may not be suitable for all environments.|
|**Community and Enterprise Support:** Available in both open-source and enterprise editions, providing options for different levels of support and features.	|**Dependency on Java:** Requires Java (JDK 11 or later) to be installed, adding an extra layer of dependencies to manage.|



## Installation 
Follow the link for the installation Document:
()

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
