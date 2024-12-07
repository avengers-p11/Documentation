# Fullstack Documentation

|CREATED/UPDATED |VERSION|AUTHOR|COMMENT|
|--------|-----------|-------|---------|
|23-10-2024|1|Raman Tripathi| Full Stack Documentation | 

## Table of Contents
1. [Introduction](#introduction)
2. [Overall Component Architecture Flow](#overall-component-architecture-flow)
   * [Frontend Flow](#frontend-flow)
    * [Database Management](#database-management)
      *  [Employee API](#employee-api)
      * [The Attendance API](#the-attendance-api)
      * [The Salary API](#the-salary-api)


3. [User Flow](#user-flow)
5. [Conclusion](#conclusion)
6. [Contact Information](#contact-information)
7. [Refrences](#refrences)

## Introduction

Full Stack Development is the process of creating a complete web application that includes front-end, back-end, and database management. 

**Front-End**: This is what users see and interact with on the website. It focuses on the look and feel, making sure the site is easy to use and looks good.

**Back-End**: This is the behind-the-scenes part. It handles the server, the logic of the application, and ensures everything works correctly. It also manages security and data processing.

**Database Management**: This part is about storing and organizing all the data the application needs. It makes sure data can be easily accessed and managed.


## Overall Component Architecture Flow

### Frontend Flow

Front-end development focuses on the part of a web application that users see and interact with. It's all about designing how the app looks (user interface) and how it feels to use (user experience). Front-end developers use languages like HTML, CSS, and JavaScript to build this visual part of the website, making sure it's easy to use and works smoothly.

## Pre-Requisites
The frontend application have dependencies on other REST API of OT-Microservices.

<img width="656" alt="image" src="https://github.com/user-attachments/assets/c1e1609d-7c6d-4093-b05e-4a18a37562cf">


To run the application successfully, These things should be configured
For Refrence Links Below
* [POC](https://github.com/avengers-p11/Documentation/blob/main/OT%20MS%20Understanding/Frontend%20/Frontend%20POC/README.md) 
* [Employee API](https://github.com/avengers-p11/Documentation/blob/main/OT%20MS%20Understanding/Employee-api/Employee%20detailed%20documentation/README.md)
* [Attendance API](https://github.com/avengers-p11/Documentation/blob/main/OT%20MS%20Understanding/Attendance/Attendance%20POC/README.md)
* [Salary API](https://github.com/avengers-p11/Documentation/blob/main/OT%20MS%20Understanding/Salary/Salary%20Documentation/README.md)


### Backend Management

#### 1 .Employee-API
The Employee REST API is a Go-based microservice that manages all employee-related transactions within the OT-Microservices stack. It is fully platform-independent, meaning it can run on any type of operating system or platform.

<img width="656" alt="image" src="https://github.com/user-attachments/assets/79e8d9d9-0f77-4dee-9abe-dd2aff3018fb">


Create this same as above.
Pre-Requisites
For running the application, we need following things configured:
For Refrence Links Below
* [Documentation](https://github.com/avengers-p11/Documentation/blob/main/OT%20MS%20Understanding/Employee-api/Employee%20detailed%20documentation/README.md) 
* [POC](https://github.com/avengers-p11/Documentation/blob/main/OT%20MS%20Understanding/Employee-api/Employee%20-%20POC/README.md) 
* [ScyllaDB](https://github.com/avengers-p11/Documentation/blob/main/OT%20MS%20Understanding/ScyllaDB/ScyllaDB%20Documentation/README.md)
* [Redis](https://github.com/avengers-p11/Documentation/blob/main/OT%20MS%20Understanding/Redis/Redis%20Documentation/README.md)

#### 2. The Salary API
The Salary API is a Java-based microservice that handles all salary-related transactions and records within the OT-Microservices stack. It is platform-independent, meaning it can run on various operating systems. However, to run this application, a Java Runtime Environment (JRE) is required.

<img width="653" alt="image" src="https://github.com/user-attachments/assets/e580ede2-8432-40d8-988c-c2fb33440827">

We only need maven as build tool, but for running the application following things are required
For Refrence Link are below 
* [Documentation](https://github.com/avengers-p11/Documentation/blob/main/OT%20MS%20Understanding/Salary/Salary%20Documentation/README.md)
* [POC](https://github.com/avengers-p11/Documentation/blob/main/OT%20MS%20Understanding/Salary/Salary%20POC/README.md)
* [ScyllaDB](https://github.com/avengers-p11/Documentation/blob/main/OT%20MS%20Understanding/ScyllaDB/ScyllaDB%20Documentation/README.mda)
* [Redis](https://github.com/avengers-p11/Documentation/blob/main/OT%20MS%20Understanding/Redis/Redis%20Documentation/README.md)
* [Java](https://maven.apache.org/)

#### 3 .The Attendance api
The Attendance REST API is a Python-based microservice that manages all attendance-related transactions within the OT-Microservices stack. This application is cross-platform, meaning it can run on different operating systems. The only requirement to run it is the Python runtime environment.

<img width="656" alt="image" src="https://github.com/user-attachments/assets/2d440cc3-520d-4d35-998f-a525744cb533">

To run the application successfully, we need these things configured

PostgresSQL as a primary database for storing all the attendance records
Redis as cache management middleware for storing all API response
Below Have Refrence Links in detail
* [Documentation](https://github.com/avengers-p11/Documentation/blob/main/OT%20MS%20Understanding/Attendance/Attendance%20Documentation/README.md) 
* [POC](https://github.com/avengers-p11/Documentation/blob/main/OT%20MS%20Understanding/Attendance/Attendance%20POC/README.md) 
* [PostgresSQL](https://github.com/avengers-p11/Documentation/blob/main/OT%20MS%20Understanding/PostgresSQL/PostgresSQL-documentation.md) 
* [Redis](https://github.com/avengers-p11/Documentation/blob/main/OT%20MS%20Understanding/Redis/Redis%20Documentation/README.md)
* [Poetry](https://www.digitalocean.com/community/tutorials/how-to-install-poetry-to-manage-python-dependencies-on-ubuntu-22-04)
* [Liquibase](https://docs.liquibase.com/start/install/liquibase-linux-debian-ubuntu.html)

### Database Management

Database management is responsible for storing, accessing, and managing data for an application. It involves tasks such as creating databases, maintaining their performance, and optimizing them to ensure efficient data handling.
For Refrence Links Below
* [ScyllaDB](https://github.com/avengers-p11/Documentation/blob/main/OT%20MS%20Understanding/ScyllaDB/ScyllaDB%20Documentation/README.md)
  
* [PostgresSQL](https://github.com/avengers-p11/Documentation/blob/main/OT%20MS%20Understanding/PostgresSQL/PostgresSQL-documentation.md)
  
* [Redis](https://github.com/avengers-p11/Documentation/blob/main/OT%20MS%20Understanding/Redis/Redis%20Documentation/README.md)

### User Flow

---

| **User Registration Flow* |                
|---------------|
| User submits the registration form. |     
| Frontend validates the input. |                                     
| The request is sent to the backend. |                       
| The backend processes the registration and stores the data in the database. |        
| A response is sent back to the frontend. |                                      
---

| **User Login Flow** |                                                  
|---------------------|                                      
| User submits the login form. |                                       
| Frontend validates the input. |                                           
| The request is sent to the backend. |                                     
| The backend authenticates the user. |                                    
| A response is sent back to the frontend with a token. |            
---

| **Data Processing Flow** |                                                                                        
|---------------------------|
| Data is submitted from the frontend. |                                                               
| The backend processes the data. |                                                                         
| Data is validated and transformed. |                                                                
| Processed data is stored in the database. |                                                           
| Confirmation is sent back to the frontend. |      
                                                 
---
### Conclusion
This document gives a clear overview of full-stack development for the OT-MICROSERVICES project. It explains how the front end and back end work together and shares important practices for building strong and easy-to-maintain applications. 

## Contact Information

| Name          | Email Address                          | 
| ------------- |:--------------------------------------:|
| Raman Tripathi      | raman.tripathi.snaatak@mygurukulam.co |

## Refrences 

| Links          |
| ------------- |
|    https://github.com/OT-MICROSERVICES  | 
|     | 



