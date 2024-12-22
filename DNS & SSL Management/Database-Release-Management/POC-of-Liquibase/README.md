# Liquibase POC Documentation
![image](https://github.com/user-attachments/assets/f3ed32db-5047-4fed-a7f6-83cea0a3119d)


| Author        | Created on | Version | Last updated by | Last edited on |
  |-------------|---------|-------------|-------------|---------|
  | Raman Tripathi | 20-12-24 | version 1 | Raman Tripathi | 20-11-24 |




 **Table of Contents**                                  
 [Introduction](#introduction)                            
 [Pre-requisites](#pre-requisites)                        
 [Architecture](#architecture)                            
 [Step-by-Step Setup Guide in Ubuntu](#step-by-step-setup-guide-in-ubuntu) 
 [Best Practices](#best-practices)                        
 [Backup and Rollback Strategy](#backup-and-rollback-strategy) 
 [Conclusion](#conclusion)                                
 [Contact Information](#contact-information)              
 [References](#references)                                

## Introduction
Liquibase is an open-source library for tracking, managing, and applying database schema changes. It allows database schema management and version control, making it easier to support iterative development and continuous integration practices.

## Pre-requisites

| Requirement                             | Description                                                        |
|-----------------------------------------|--------------------------------------------------------------------|
| Database                                | A running instance of a database (e.g., MySQL, PostgreSQL, etc.)   |
| Java Development Kit (JDK)              | JDK 8 or higher installed                                          |
| SQL and Database Operations Knowledge   | Basic understanding of SQL and database operations                 |


## Features

**Tracking** : Liquibase keeps a record of database changes with a unique ID and author for easy identification.

**Mananging** : It uses centralized changelog files to manage and synchronize all database changes.

**Applying Database Changes** : Automatically applies changes to the database with support for rollback if needed.

## Architecture


Liquibase operates through a series of `changelogs` written in XML, YAML, JSON, or SQL, which define the alterations needed for the database schema. These changelogs are processed by the Liquibase engine, which then applies them to the target database. The Liquibase infrastructure consists of the following components:

1. **Database**: The target database where changes are applied.
2. **Changelogs**: Files that contain the changesets.
3. **Command-line Interface (CLI)**: Primary interface to run Liquibase commands.
4. **Database Driver**: A connector for Liquibase to interact with the target database.


## Step-by-Step Setup Guide 

### 1. Install Java Development Kit (JDK)
 Kindly use this documentation to install a specific version of Java.
- References
 https://www.oracle.com/in/java/technologies/downloads/#java11

### 2. Install PostgresSQL 
- References
https://github.com/avengers-p11/Documentation/blob/main/OT%20MS%20Understanding/PostgresSQL/PostgresSQL-documentation.md

### 3. Install Liquibase
````sh
sudo snap install liquibase
````
<img width="644" alt="image" src="https://github.com/user-attachments/assets/c6ca3b87-6faa-4afa-9832-123f6cb49267" />



 To verification installation
````sh
liquibase --version
````
<img width="1110" alt="image" src="https://github.com/user-attachments/assets/dbc27004-1f5f-4b6d-8e05-0dbcc2830bf1" />

## For Connecting with DB

  **Set Up Environment Variables**:
    ```sh
    export PATH=$PATH:/path/to/liquibase
    ```

 ## **Create a Liquibase Properties File** (`liquibase.properties`):
     
  Purpose-- Centralize configuration settings for Liquibase, reducing the need to specify configurations in every command and 
  improving security and consistency.

  Contents -  `url`, `username`, `password`, `changeLogFile`, `driver`.                                                                                   

    
  ```
    url=jdbc:postgresql://localhost:5432/attendance_db
    username=postgres
    password=password
    changeLogFile=migration/db-changelog.xml
   ```

 ## **Create ChangeLog File** (`db-changelog.xml`):
         
 A changelog file in Liquibase is used to define and track database schema changes in a version-controlled manner. It ensures consistent and repeatable deployments by recording each change in a structured format (XML, YAML, JSON, or SQL). This helps in managing database versions and enables easy rollback if needed.

    <?xml version="1.0" encoding="UTF-8"?>

    <databaseChangeLog
        xmlns="http://www.liquibase.org/xml/ns/dbchangelog"
        xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
        xsi:schemaLocation="http://www.liquibase.org/xml/ns/dbchangelog
                            http://www.liquibase.org/xml/ns/dbchangelog/dbchangelog-3.8.xsd">

        <!-- Example changeSet -->
        <changeSet author="your_name" id="1" context="test">
            <createTable tableName="example_table">
                <column name="id" type="int">
                    <constraints primaryKey="true" nullable="false"/>
                </column>
                <column name="name" type="varchar(255)">
                    <constraints nullable="false"/>
                </column>
            </createTable>
        </changeSet>

    </databaseChangeLog>
    

 ## **Run Liquibase Update**:
   
```    
liquibase --changeLogFile=db-changelog.xml update
```
<img width="1061" alt="image" src="https://github.com/user-attachments/assets/2dc6422a-13fb-4d27-b501-54001e52b6d8" />


## Best Practices

| **Best Practice**        | **Description**                                                                 |
|--------------------------|---------------------------------------------------------------------------------|
| **Version Control**      | Store your changelog files in a version control system (e.g., Git).              |
| **Granular Changesets**  | Make changesets small and granular to facilitate easier troubleshooting and rollback. |
| **Testing**              | Always test changesets in a staging environment before applying them to production. |
| **Documentation**        | Document changesets thoroughly to ensure they are understandable by other team members. |


## Backup and Rollback Strategy

1. **Backup**:
      A backup strategy in Liquibase involves regularly saving database states to secure locations, ensuring data integrity and facilitating quick recovery in case of errors. It typically includes scheduled backups, pre-deployment backups before applying changes, and automated verification processes to ensure backup reliability.

    - Perform a database dump before applying any changes.
      
    ```sh
     pg_dump -h localhost -p 5432 -U postgres -d attendance_db > backup.sql
    ```






2. **Rollback**:
      A rollback strategy in Liquibase involves reverting database changes to a previous state if deployment issues occur. It typically          includes utilizing Liquibase commands or rollback scripts to undo specific changes, ensuring data integrity by backing up before          rollback, and testing rollback procedures in a staging environment for reliability.
    - Define rollback procedures within your changesets.
    ```xml
    <changeSet id="1" author="yourname">
        <rollback>
            <dropTable tableName="example_table"/>
        </rollback>
    </changeSet>
    ```
    - Execute rollback if needed.
    ```sh
    liquibase rollbackCount 1
    ```


## Conclusion
Liquibase is a powerful tool for managing database schema changes, providing a reliable way to track, version, and deploy changes. By following best practices and having a solid backup and rollback strategy, you can effectively manage your database schema lifecycle.

## Contact Information
| Name| Email Address      |
|-----|--------------------------|
| Raman Tripathi | raman.tripathi.snaatak@mygurukulam.co |

| GitHub | URL |
|----------|---------|
|  Raman-tripathi07  |  https://github.com/Raman-tripathi07 |

## References
| Reference                          | URL                                                                 |
|------------------------------------|---------------------------------------------------------------------|
| Liquibase Official Documentation   | [Liquibase Official Documentation](https://www.liquibase.org/documentation.html) |
| Java JDK Documentation             | [Java JDK Documentation](https://docs.oracle.com/en/java/)          |
