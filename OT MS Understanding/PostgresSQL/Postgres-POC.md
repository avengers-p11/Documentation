# POSTGRES INSTALLATION POC

<img width="415" alt="image" src="https://github.com/user-attachments/assets/9c8ecd07-97ce-492f-856c-9e5fc7b3a3f7" />

| **Author** | **Created on** | **Version** | **Last edited on** | **Reviewer** |
|------------|----------------|-------------------|---------------------|----------|
| Raman Tripathi  | 16-11-24      | V1.1  | 16-11-24           |  |
   

**Table of Contents**                               

[Introduction]( #introduction)  
      
[Prerequisite]( #prerequisite)

[Important Port](#imoprtant-Port) 

[Step-by-Step Setup Guide](#step-by-step-setup-guide)

[Conclusion](#conclusion)

[Contact Information](#contact-information)  
   
[References](#references)                               



## Introduction

PostgreSQL is a relational SQL database, which means it stores data in rows and columns. It was developed in 1986 by the University of California, Berkeley. It is widely used by many companies such as Apple, Cisco, Fujitsu, Instagram, Spotify, Skype, etc.
**"Additionally, we are using PostgreSQL in our project for the Attendance API."**

## Prerequisite


| Dependency          | Description                                                       |
|---------------------|-------------------------------------------------------------------|
| Python              | Recommended  3.6 or later                  |


## Important Port
 | 5432 |


## Step-by-Step Setup Guide 

### Install Postgres
We can install PostgreSQL in Window , Ubuntu and Mac etc. But As per our documentation we are moving forward with **ubuntu**.

#### STEP 1 : install from [official website](https://www.postgresql.org/download/)

To install postgres directly with apt command

```
sudo apt install postgresql postgresql-contrib -y
```
<img width="605" alt="image" src="https://github.com/user-attachments/assets/2f679819-d78f-473a-9e54-a33f445e1841" />


#### STEP 2 : To verify the installation and check the version of postgres

```
psql --version
```

<img width="607" alt="image" src="https://github.com/user-attachments/assets/19fa2f64-c848-481a-8099-1d9f2c2e856e" />


#### STEP 3 :  To start, enable, and check the status of PostgreSQL
```
sudo systemctl start postgresql
```
```
sudo systemctl enable postgresql
```
```
sudo systemctl status postgresql
```


<img width="583" alt="image" src="https://github.com/user-attachments/assets/a7825407-5d6c-40b0-93f8-2344f8f6475b" />


#### STEP 4 : for switching into postgres user
```
sudo -i -u postgres
```
<img width="480" alt="image" src="https://github.com/user-attachments/assets/96ef7413-1d14-4fff-b2d9-5c4af945afb3" />

#### STEP 5 : To go into postgres shell

```
psql
```

<img width="527" alt="image" src="https://github.com/user-attachments/assets/85883528-22cf-49bc-86c9-79a92803500d" />


#### STEP 6 : To create a database we can do 

```
create database database_name
```
For example, if you want to create a database called `my_new_db`, you would run:
```
CREATE DATABASE my_new_db;

```
<img width="428" alt="image" src="https://github.com/user-attachments/assets/029a50b1-5160-4cd0-98ed-b1ecf907a0ee" />


### To list the database 

```
\l
```

<img width="606" alt="image" src="https://github.com/user-attachments/assets/69a4e516-95eb-45ba-abb2-24c6c66e2971" />

### To delete a particular database

```
drop database database_name
```

<img width="607" alt="image" src="https://github.com/user-attachments/assets/e23e36eb-b950-4ff6-b555-b409be635072" />

## Conclusion
PostgreSQL is an ideal database for microservices due to its reliability, scalability, and support for complex queries. It helps manage data efficiently across distributed services, ensuring consistency, high performance, and flexibility as the system grows. Its advanced features make it a powerful choice for handling large volumes of data in microservice architectures.

## Contact Information 

| Name| Email Address      |
|-----|--------------------------|
| Raman Tripathi | raman.tripathi.snaatak@mygurukulam.co |

| GitHub | URL |
|----------|---------|
|  Raman-tripathi07  |  https://github.com/Raman-tripathi07  |

## References
| Links | Description |
|-------|-------------|
| [Postgres](https://www.postgresql.org/download/linux/ubuntu/) | Postgres download |
|      https://mygurukulam25.atlassian.net/jira/software/projects/SCRUM/boards/1?label=%23Radha&selectedIssue=SCRUM-14  |           For more information on PostgreSQL.  |


