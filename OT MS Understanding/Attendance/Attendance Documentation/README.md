#    **Attendance API Documentation**
#    **(OT-MICROSERVICES)**

| **Author**            | **Created on** | **Version** | **Last updated by**       | **Last edited on** | **Reviewer L0**  | **Reviewer L1**   | **Reviewer L2**   |
|-----------------------|----------------|-------------|---------------------------|---------------------|------------------|-------------------|----------------|
| Mohit Saini      |   11-11-24       | v1 | Mohit Saini          |     22-11-24            | Khushi   |      |     |




**Table of Contents**

-   [**Overview**](#overview)

-   [**Purpose**](#purpose)

-   [**System Requirements**](#related-resources)

-   [**Dependency**](#related-resources)

-   **[Architecture](#related-resources)**

-    [**Flow Diagram**](#related-resources)

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
#

### Related Resources
**For detailed information of system requirements, architecture, flow diagram, and installation steps, please refer to the following resources**
| Link         | Description         |
|--------------|------------------------|
| [Attendance API](https://github.com/avengers-p11/Documentation/blob/main/OT%20MS%20Understanding/Attendance/Attendance%20POC/README.md) |POC of Attendance records and data flow.| 


# Components

-   [PostgreSQL](https://www.postgresql.org/)

-   [Redis](https://redis.io/)

-   [Poetry](https://python-poetry.org/)

-   [Liquibase](https://docs.liquibase.com/)

## PostgreSQL

PostgreSQL is a great choice for managing attendance data because it handles organized data well, ensures the data is safe and correct through ACID (Atomicity, Consistency, Isolation, and Durability), and can grow as your project gets bigger. It also makes it easy to analyze attendance and create reports.

**Why?**

 | **Why It's Used**      | **Details**                                                                                              |
|------------------------|----------------------------------------------------------------------------------------------------------|
| Relational Database    | PostgreSQL is a free and safe database that keeps your data correct and organized.                        |
| Handling Attendance    | It works well for storing things like users, dates, and events, and can do complicated searches easily.    |
| Scalability            | It can grow with your project as more data comes in, making it perfect for big projects.                   |



## Redis

Redis (**RE**mote **DI**ctionary **S**erver) is good for this project because it keeps data in memory, making the app faster by not needing to fetch it from the database every time. It helps quickly manage user sessions and send real-time updates, like when an attendance record is changed. Unlike other databases, Redis is much faster for handling temporary data like sessions or cached records

**Why?**

| **Why It's Used**      | **Details**                                                                 |
|------------------------|-----------------------------------------------------------------------------|
| **Caching**            | Stores frequently accessed data, like attendance records, in memory to make the app faster. |
| **Session Management** | Keeps track of user sessions quickly, so users stay logged in and their actions are stored. |
| **Real-Time Updates**  | Sends instant updates to users, like notifying them when their attendance record is updated. |




## Poetry

Poetry is good for this project because it helps manage Python libraries easily, ensuring everything stays organized and works the same across different systems. It also makes it simple to package and share your Python app.

![image](https://github.com/user-attachments/assets/7dc99b98-b068-4147-9254-7bc50ca8a465)


**Why?**

| **Why It's Used**          | **Details**                                                                  |
|----------------------------|------------------------------------------------------------------------------|
| **Dependency Management**   | Manages Python libraries for the project, ensuring everything is organized and works smoothly across all environments. |
| **Project Packaging**       | Helps package and prepare the Python app for easy sharing and deployment.     |
| **Version Control**         | Ensures that all team members use the same library versions, making the project run consistently on different machines. |

## 

## **Liquibase** 

In Attendance Application we used Liquibase helps to manage changes the database easily. It keeps track of all updates in a file so everyone uses the same version of the database. If something goes wrong, we can go back to an earlier version. Liquibase also updates the database automatically when we add new features, making it simple and safe to work as a team.

**Why?**

| **Why It's Used**        | **Details**                                                                 |
|--------------------------|-----------------------------------------------------------------------------|
| **Database Management**   | Liquibase helps us track and manage changes to the attendance database, making sure everything stays up-to-date in all environments. |
| **Version Control**       | Liquibase tracks database changes, just like Git tracks code changes, so the whole team uses the same version of the database. |
| **CI/CD Integration**     | Liquibase automatically updates the attendance database whenever the app is updated, keeping both in sync. |


# Conclusion

The Attendance uses PostgreSQL for secure data storage, Redis for fast data access, Liquibase for smooth database updates, and Poetry for managing dependencies. These technologies work together to create a fast, scalable, and reliable system for managing attendance data. The API is designed to be efficient and easy to maintain, making it suitable for real-world use.

#  Contact Information


| **Name**    | **Email address**         |
|-------------|---------------------------|
| Mohit Saini | <it.mohitsaini@gmail.com> |


# References

| **Link** | **Description** |
|------------------------------------------------------|------------------|
| https://github.com/avengers-p11/Documentation/tree/main/OT%20MS%20Understanding/Redis/Redis%20Documentation| PostgreSQL installation and configuration |
| https://chandrapurnimabhatnagar.medium.com/how-to-install-liquibase-database-devops-34ca9a6d9705 | Liquibase installation |
| https://github.com/avengers-p11/Documentation/blob/main/OT%20MS%20Understanding/PostgresSQL/PostgresSQL-documentation.md| Redis|

