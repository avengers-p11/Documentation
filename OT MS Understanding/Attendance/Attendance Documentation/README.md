#    **Attendance API Documentation**
#    **(OT-MICROSERVICES)**

| **Author**            | **Created on** | **Version** | **Last updated by**       | **Last edited on** | **Reviewer L0**  | **Reviewer L1**   | **Reviewer L2**   |
|-----------------------|----------------|-------------|---------------------------|---------------------|------------------|-------------------|----------------|
| Mohit Saini      |   11-11-24       | v1 | Mohit Saini          |     15-11-24            | Khushi   |      |     |




**Table of Contents**

-   [**Overview**](#overview)

-   [**Purpose**](#purpose)

-   [**System Requirements**](#system-requirements)

-   [**Dependency**](#dependency)

-   **[Architecture](#architecture)**

-    [**Flow Diagram**](#flow-diagram)

-   **[Components](#components)**

    -   [PostgreSQL](#postgresql)[Redis](#redis)

    -   [Poetry](#poetry)

    -   [Liquibase](#liquibase)

-   [**Conclusion**](#conclusion)

-   [**Contact Information**](#contact-information)

-   **[References](#references)**

# Overview

This project is designed to create an Attendance API that integrates
with **PostgreSQL** for storing data, **Redis** for caching, and
uses **Liquibase** for database change management. The system is also
configured to manage Python dependencies using **Poetry**.

**Technology Stack**

1.  **PostgreSQL** - A relational database system used for storing
    attendance data.

2.  **Redis** - A fast in-memory key-value store used for caching.

3.  **Poetry** - A Python dependency manager to handle project
    dependencies.

4.  **Liquibase** - A database change management tool that helps manage
    schema changes in a controlled manner.

# Purpose

This document provides detailed information about the Attendance Microservices, which is a Python-based API designed to manage attendance efficiently.

# Pre-requisites

Before diving into application deployment, let’s ensure the following
Hardware, Software and Security requirements are met.

## System Requirements

| **Hardware Specifications** | **Minimum**         | **Recommendation**              |
|-----------------------------|---------------------|----------------------------------|
| Processor                  | Dual-core          | Quad-core processor             |
| RAM                        | 4GB                | 8GB or higher                   |
| Disk                       | 20GB               | 50GB or higher                  |
| OS                         | Ubuntu (22.04)     | Latest LTS version of Ubuntu    |
| VM                         |  t2.medium         |  t3.large                       |




## Dependency


| **Name** | **Version** | **Description** |
|-----------------|----------|---------------------------------------------|
| **Python 3.11** | 3.10.12 | The programming language used to build the application. |
| **Poetry** | 1.8.4 | Python dependency manager for managing packages and virtual environments. |
| **PostgreSQL-devel** | 14.13 | Development libraries required for PostgreSQL interaction. |
| **Liquibase** | 4.1.1 | Database schema versioning tool used for managing database migrations. |

# Architecture

![image](https://github.com/user-attachments/assets/3317237b-7508-4454-8648-67e5e12b80fe)

# Flow Diagram

![image](https://github.com/user-attachments/assets/1d64e9e6-7cfd-48fe-845c-ac29ad982dec)


# Components

-   [PostgreSQL](https://www.postgresql.org/)

-   [Redis](https://redis.io/)

-   [Poetry](https://python-poetry.org/)

-   [Liquibase](https://docs.liquibase.com/)

## PostgreSQL

PostgreSQL is an open-source object relational database management
system used for transactional and analytical workloads. It incorporates
and expands upon the SQL programming language, offering an array of
features designed to securely store and efficiently scale even the most
complex data workloads.

**Use Cases**

 | **Feature**                         | **Description**                                                                                          |
|-------------------------------------|----------------------------------------------------------------------------------------------------------|
| **Support for Complex Data Relationships** | Effectively manages relationships between entities (users, records) using foreign keys and constraints. |
| **Advanced Querying and Data Retrieval** | Offers robust SQL features and indexing for efficient data access and reporting.                         |
| **Scalability and Performance**      | Handles large datasets and multiple users without performance loss, supporting growth through indexing and replication. |
| **Data Backup and Recovery**        | Provides reliable backup tools and quick recovery options to protect attendance data.                   |


## Redis

Redis (**RE**mote **DI**ctionary **S**erver) is an open source,
in-memory, NoSQL key/value store that is used primarily as an
application cache or quick-response database. It stores data in memory,
rather than on a disk or solid-state drive (SSD), which helps deliver
unparalleled speed, reliability, and performance.

**Use Cases**

| **Feature**                         | **Description**                                                                                           |
|-------------------------------------|-----------------------------------------------------------------------------------------------------------|
| **In-memory Storage**               | Redis stores data in memory, allowing for extremely fast read and write operations.                        |
| **Data Structures**                 | Supports various data structures such as strings, hashes, lists, sets, and sorted sets.                   |
| **Persistence Options**             | Provides multiple persistence mechanisms like snapshots and append-only files (AOF).                      |
| **Scalability**                     | Redis supports horizontal scaling through clustering and partitioning.                                    |



## Poetry

**What is Poetry**

Poetry is a tool designed to handle dependency management and packaging
in Python projects. It leverages the pyproject.toml file, introduced in
PEP 518, to define project requirements, manage virtual environments,
and package projects for distribution. Poetry’s goal is to make Python
development more predictable, manageable, and efficient.

![image](https://github.com/user-attachments/assets/7dc99b98-b068-4147-9254-7bc50ca8a465)


**Use cause**

| **Feature**                         | **Description**                                                                                           |
|-------------------------------------|-----------------------------------------------------------------------------------------------------------|
| **Dependency Management**           | Poetry handles dependencies in a simple and efficient way, ensuring the right versions are installed.     |
| **Package Publishing**              | Allows easy publishing of Python packages to the Python Package Index (PyPI).                             |
| **Virtual Environment Management**  | Automatically creates and manages virtual environments for each project to isolate dependencies.          |
| **Version Management**              | Poetry helps manage and lock project dependencies with specific version numbers to ensure consistency.    |

## 

## **Liquibase** 

**What is Liquibase**

Liquibase is an open-source database migration tool that allows
developers to define and manage changes to their database schema in a
declarative manner. Instead of writing manual SQL scripts to alter the
database structure, Liquibase lets you describe the desired changes in
XML, YAML, or JSON formats, making the process more human-readable and
version-controllable.


**Use cause **

| **Feature**                         | **Description**                                                                                           |
|-------------------------------------|-----------------------------------------------------------------------------------------------------------|
| **Database Version Control**        | Liquibase helps track, manage, and apply database changes in a version-controlled manner.                 |
| **Database Schema Management**      | It provides tools for managing schema changes across different environments in a consistent way.          |
| **Changelog Files**                 | Uses XML, YAML, JSON, or SQL-based changelogs to define database changes and maintain a clear history.     |
| **Rollback Capability**             | Liquibase allows you to roll back changes to a previous state, ensuring safety and flexibility in database management. |
| **Cross-Platform Support**          | Works across multiple database platforms such as MySQL, PostgreSQL, Oracle, SQL Server, and more.          |

# Conclusion

The Attendance uses PostgreSQL for secure data storage, Redis for fast data access, Liquibase for smooth database updates, and Poetry for managing dependencies. These technologies work together to create a fast, scalable, and reliable system for managing attendance data. The API is designed to be efficient and easy to maintain, making it suitable for real-world use.

#  Contact Information


| **Name**    | **Email address**         |
|-------------|---------------------------|
| Mohit Saini | <it.mohitsaini@gmail.com> |


# References

| **Link** | **Description** |
|------------------------------------------------------|------------------|
| https://medium.com/devops-technical-notes-and-manuals/how-to-install-and-configure-postgresql-on-ubuntu-20-04-4fd3cf072d6f | PostgreSQL installation and configuration |
| https://chandrapurnimabhatnagar.medium.com/how-to-install-liquibase-database-devops-34ca9a6d9705 | Liquibase installation |
| https://github.com/avengers-p11/Documentation/tree/main/OT%20MS%20Understanding/Redis/Redis%20Documentation| Redis|

