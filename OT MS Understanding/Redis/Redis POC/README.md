# REDIS POC

| **Author**            | **Created on** | **Version** | **Last updated by**       | **Last edited on** | **Reviewer**      |
|-----------------------|----------------|-------------|----------------------------|---------------------|-------------------|
| Anugra W. Lepcha      | 12-11-24       | Version 1.1  | Anugra W. Lepcha           | 14-11-24           | Shreya Jaiswal    |

## Table of Contents

1. [Introduction](#redis)
2. [Redis Setup Prerequisites](#redis-setup-prerequisites)
3. [Redis Installation on Ubuntu](#redis-installation-on-ubuntu)
    - [Step 1: Update System Packages](#step-1-update-system-packages)
    - [Step 2: Install Redis](#step-2-install-redis)
    - [Step 3: Start Redis Service](#step-3-start-redis-service)
    - [Step 4: Check Redis Service Status](#step-4-check-redis-service-status)
    - [Step 5: Stop Redis Service](#step-5-stop-redis-service)
    - [Step 6: Configure Redis](#step-6-configure-redis)
        - [1. Open the Redis Configuration File](#1-open-the-redis-configuration-file)
        - [2. Set a Password](#2-set-a-password)
        - [3. (Optional) Configure a Username](#3-optional-configure-a-username)
        - [4. Save and Close the File](#4-save-and-close-the-file)
        - [5. Restart Redis](#5-restart-redis)
        - [6. Connect to Redis with Username and Password](#6-connect-to-redis-with-username-and-password)
        - [7. Verify the Connection](#7-verify-the-connection)
4. [Contact Information](#contact-information)
5. [References](#references)


## REDIS

The purpose of this POC is to evaluate Redis as a caching solution for the application, testing its performance, scalability, and integration capabilities.

## Hardware Pre-requisites

| **Requirement**        | **Details**                  |
|------------------------|------------------------------|
| **OS**                 | Ubuntu or other Linux-based OS |
| **RAM**                | 2 GB minimum                 |
| **Disk Space**         | 100 MB or more               |
| **Processor**          | Dual-core recommended        |
| **Network**            | Port 6379 open               |
| **Redis Version**      | 6.x or higher recommended    |

## Redis Installation on Ubuntu

This guide provides the steps to install and configure Redis on Ubuntu.

## Prerequisites

- Ubuntu 20.04 or later
- A user with `sudo` privileges

## Installation Steps

### Step 1: Update System Packages

Before starting the installation, ensure your system packages are up-to-date.

``` bash
sudo apt update
```
### Step 2: Install Redis

To install Redis, use the apt package manager

``` bash
sudo apt install redis-server -y
```
![Screenshot 2024-11-12 080435](https://github.com/user-attachments/assets/711e4bfe-df01-443e-97d8-2a9b52678f6f)

### Step 3: Start Redis Service
Run the following command to start the Redis service:

``` bash
sudo systemctl start redis-server
sudo systemctl enable redis-server
```
### Step 4: Check Redis Service Status
To confirm that Redis has started successfully, use the following command:

``` bash
sudo systemctl status redis-server
```
![Screenshot 2024-11-12 080608](https://github.com/user-attachments/assets/44b35826-c133-466b-a9c4-d7837b35012e)

### 5. Stop Redis Service
To stop the Redis service, run:

``` bash
sudo systemctl stop redis-server
```
### Step 6: Configure Redis
To set up a password and username for Redis, follow these steps:
#### 1. Open the Redis configuration file:

``` bash
sudo vi /etc/redis/redis.conf
```
#### 2. Set a Password:
Find the line with # requirepass foobared and replace it with:

``` bash
requirepass <your_password_here>
```

#### 3.(Optional) Configure a Username:
For Redis 6.x and above, you can set up a username with Access Control Lists (ACLs). Add this to the redis.conf file:

``` bash
user <user_name> on ><your_password> ~* +@all
```
- *<user_name> is the username* 
- *<your_password> is the password*
- *~* allows access to all keys*
- *+@all grants full command permissions to this user*

#### 4. Save and Close the file.

 #### 5.Restart Redis
To apply these changes, restart the Redis service:

``` bash
sudo systemctl restart redis
```
![Screenshot 2024-11-12 080913](https://github.com/user-attachments/assets/6b42f8fb-36c4-4074-8df8-3f99b2806581)

#### 6. Connect to Redis with Username and Password
Now, you can authenticate to Redis using both a username and password.

Start the Redis CLI:

``` bash
redis-cli
AUTH <user_name> <your_password>
```
![Screenshot 2024-11-12 081120](https://github.com/user-attachments/assets/384944e8-bbba-488b-ab4a-c583fe6c33f9)


#### 7. Verify the Connection: 
After authenticating, you can test the connection by running a simple command PING:

``` bash
PING
```
If you see PONG, it means authentication was successful.
![Screenshot 2024-11-12 081219](https://github.com/user-attachments/assets/ffffcdcd-7f95-4f15-b7e0-ea175aa57b72)


### Contact Information

| **Name** | **Email address**            |
|----------|-------------------------------|
| Anugra .W. Lepcha    |  wangchuklepcha801@gmail.com           |

 
### References

| Link                                                                                                           | Description                                               |
|---------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------|
| [Redis Documentation - Linux Installation](https://redis.io/docs/latest/operate/oss_and_stack/install/install-redis/) | Document format followed from this link.                 |
| [Introduction vs. Overview](https://backendless.com/redis-what-it-is-what-it-does-and-why-you-should-care/) | This link explains the difference between Overview & Introduction. |
| [Redis Documentation - GitHub](https://github.com/avengers-p11/Documentation/tree/main/OT%20MS%20Understanding/Redis/Redis%20Documentation) | Link to Redis documentation on GitHub.                    |
