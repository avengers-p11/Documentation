#    **Attendance API Documentation**
#    **(OT-MICROSERVICES)**

| **Author**            | **Created on** | **Version** | **Last updated by**       | **Last edited on** | **Reviewer L0**  | **Reviewer L1**   | **Reviewer L2**   |
|-----------------------|----------------|-------------|---------------------------|---------------------|------------------|-------------------|----------------|
| Mohit Saini      |   11-11-24       | v1 | Mohit Saini          |     15-11-24            | Kushi   |      |     |




**Table of Contents**

-   [**Overview**](#overview)

-   [**Purpose**](#purpose)

-   [**System Requirements**](#system-requirements)

-   [**Dependency**](#dependency)

-   **[Architecture](#architecture)**

-   **[Components](#components)**

    -   [PostgreSQL](#postgresql)[Redis](#redis)

    -   [Poetry](#poetry)

    -   [Liquibase](#liquibase)

-   [**Conclusion**](#conculsion)

-   [**Contact Information**](#contact-information)

-   **[References](#references)**

# Overview

This project is designed to create an Attendance API that integrates
with **PostgreSQL** for storing data, **Redis** for caching, and
uses **Liquibase** for database change management. The system is also
configured to manage Python dependencies using **Poetry**.

**Technology Stack:**

1.  **PostgreSQL** - A relational database system used for storing
    attendance data.

2.  **Redis** - A fast in-memory key-value store used for caching.

3.  **Poetry** - A Python dependency manager to handle project
    dependencies.

4.  **Liquibase** - A database change management tool that helps manage
    schema changes in a controlled manner.

# Purpose

Attendance REST API is designed to simplify and automate attendance management processes. It provides an efficient and scalable solution for handling attendance-related transactions, ensuring accurate data storage, fast retrieval, and seamless integration with other systems. This API utilizes PostgreSQL for reliable database management, Redis for caching, and a Python-based tech stack for flexibility and performance, making it suitable for modern microservices architectures.

# Pre-requisites

Before diving into application deployment, let’s ensure the following
Hardware, Software and Security requirements are met.

## System Requirements

| **Hardware Specifications** | **Minimum Recommendation** |
|-----------------------------|----------------------------|
| Processor                   | Dual core                  |
| RAM                         | 4GB                        |
| Disk                        | 20GB                       |
| OS                          | Ubuntu (22.04)             |

## 

## Dependency


| **Name** | **Version** | **Description** |
|-----------------|----------|---------------------------------------------|
| **Python 3.11** | 3.10.12 | The programming language used to build the application. |
| **Poetry** | 1.8.4 | Python dependency manager for managing packages and virtual environments. |
| **PostgreSQL-devel** | 14.13 | Development libraries required for PostgreSQL interaction. |
| **Liquibase** | 4.1.1 | Database schema versioning tool used for managing database migrations. |

# Architecture

![image](https://github.com/user-attachments/assets/3317237b-7508-4454-8648-67e5e12b80fe)

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

**Why PostgreSQL:**

PostgreSQL has quickly become a popular choice among database solutions
largely due to its comprehensive features that address various aspects
such as performance, security, programming extensions, and configuration
options.

PostgreSQL provides a robust, scalable, and feature-rich solution to
meet the storage, querying, and data integrity needs of the Attendance
API project. It aligns well with the project’s requirement for reliable
data storage, advanced querying, and scalability.

**Use Cases:**

-   **Support for Complex Data Relationships**: Effectively manages
    relationships between entities (users, records) using foreign keys
    and constraints.

-   **Advanced Querying and Data Retrieval**: Offers robust SQL features
    and indexing for efficient data access and reporting.

-   **Scalability and Performance**: Handles large datasets and multiple
    users without performance loss, supporting growth through indexing
    and replication.

-   **Data Backup and Recovery**: Provides reliable backup tools and
    quick recovery options to protect attendance data.

## Redis:

Redis (**RE**mote **DI**ctionary **S**erver) is an open source,
in-memory, NoSQL key/value store that is used primarily as an
application cache or quick-response database. It stores data in memory,
rather than on a disk or solid-state drive (SSD), which helps deliver
unparalleled speed, reliability, and performance.

**Why Redis:**

Redis is an in-memory data structure store known for
its **lightning-fast data access**, providing sub-millisecond response
times ideal for caching. It offers **data persistence** options to
prevent data loss during system failures, with methods like RDB
snapshots and AOF logging. Additionally, Redis supports a variety
of **versatile data structures** such as strings, lists, and sets,
making it suitable for diverse applications beyond caching, including
real-time analytics and messaging.

![image](https://github.com/user-attachments/assets/8f69a4d4-981f-4992-8ac0-929596955bc3)


**Use causes:**

-   **Caching Attendance Data**: Redis stores frequently accessed
    records in memory, reducing database queries and enhancing response
    times.

-   **Session Management**: Redis handles session data and
    authentication tokens, providing fast lookups and offloading the
    main database.

-   **Faster API Responses**: In-memory data retrieval with Redis
    improves response speed, enhancing user experience.

-   **Temporary Data Storage**: Redis can set expiration times on cached
    data, auto-clearing temporary info (like sessions) to maintain cache
    efficiency and save memory.

## Poetry

**What is Poetry**

Poetry is a tool designed to handle dependency management and packaging
in Python projects. It leverages the pyproject.toml file, introduced in
PEP 518, to define project requirements, manage virtual environments,
and package projects for distribution. Poetry’s goal is to make Python
development more predictable, manageable, and efficient.

![image](https://github.com/user-attachments/assets/7dc99b98-b068-4147-9254-7bc50ca8a465)


**Why Poetry:**

**Dependency Management**: Poetry simplifies handling project
dependencies by using a single configuration file, pyproject.toml,
consolidating settings and dependencies in one place and reducing the
need for multiple files like requirements.txt and setup.py.

**Deterministic Builds**: By creating a poetry.lock file, Poetry locks
specific versions of all dependencies, ensuring consistent installations
across environments, enabling repeatable builds.

**Improved Dependency Resolution**: Poetry’s powerful dependency
resolver manages complex dependency trees effectively, providing clear
error messages and ensuring package compatibility.

**Use cause:**

-   **Simplified Dependency Management**: It manages all dependencies in
    a single pyproject.toml file, replacing the need for multiple files
    like requirements.txt and setup.py.

-   **Ensuring Consistent Environments**: The poetry.lock file locks
    specific dependency versions, ensuring consistency across different
    environments.

-   **Automated Virtual Environment Handling**: Poetry automatically
    creates and manages a virtual environment, preventing dependency
    conflicts with other Python projects.

## 

## **Liquibase** 

**What is Liquibase**

Liquibase is an open-source database migration tool that allows
developers to define and manage changes to their database schema in a
declarative manner. Instead of writing manual SQL scripts to alter the
database structure, Liquibase lets you describe the desired changes in
XML, YAML, or JSON formats, making the process more human-readable and
version-controllable.

**Why Liquibase:**

-   **Database Version Control**: Tracks and manages database schema
    changes systematically, similar to code versioning.

-   **Collaboration**: Facilitates teamwork by ensuring consistent
    application of schema changes across different environments.

-   **Cross-Database Compatibility**: Works with various database
    systems (e.g., MySQL, PostgreSQL, Oracle), allowing easy transitions
    between them.

-   **Automated Rollbacks**: Supports automated rollback of changes in
    case of errors during migrations, ensuring data safety.

-   **Easy Tracking and Auditing**: Generates a changelog for a detailed
    history of schema changes, simplifying audits and issue tracking.

**Use cause :**

-   **Version Control for Database Changes**: Liquibase allows each
    database schema change (like adding tables, columns, or indexes) to
    be versioned, making it easy to track and audit modifications.

-   **Automated Database Migrations**: Liquibase manages database
    migrations automatically through changelogs, ensuring consistency
    across different environments (development, staging, production)
    without manual intervention.

-   **Rollback Support**: In case of errors, Liquibase provides rollback
    functionality, allowing the database to revert to a previous stable
    state, which is crucial for maintaining data integrity and
    reliability.

# Conculsion :


The Attendance API is a strong system designed to manage attendance data
efficiently. It uses PostgreSQL for reliable data storage, Redis for
fast caching, and Liquibase for smooth database schema management.
Poetry helps with dependency management, ensuring consistent
environments during development. The API offers high performance with
quick response times, secure session handling, and dependable database
migrations. By using these technologies, the Attendance API is built for
scalability, reliability, and maintainability, ensuring smooth
operations for attendance-related tasks in real-world scenarios.

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

