# POC Document for Frontend
### This document provides Proof-of-Concept (POC) of frontend in detail.


| **Author**            | **Created on** | **Version** | **Last updated by**       | **Last edited on** | **Reviewer**      |
|-----------------------|----------------|-------------|----------------------------|---------------------|-------------------|
| Kshamata      | 11-11-24       | Version 1.1  | Raman Tripathi           | 24-11-24           | Khushi Malhotra    |

## Table of Contents
1. [Introduction](#introduction)
2. [Purpose](#purpose)
3. [System Requirements](#system-requirements)
4. [Architecture](#architecture)
5. [Installation Steps](#installation-steps)
6. [Conclusion](#conclusion)
7. [Contact Information](#contact-information)
8. [References](#references)


## Introduction
In [OT-Microservices](https://github.com/OT-MICROSERVICES) stack, the Frontend API built on ReactJS which integrates with other APIs of the application.

## Purpose
The frontend web is a REACTJS based application serving as user interface of [OT-Microservices](https://github.com/OT-MICROSERVICES) stack. This application supports cross-platform and can be executed on multiple OS as long as a JavaScript runtime environment is available. 
A ReactJS based web framework for the complete web page based operations.
Test case integration for application functionality verification.

## System Requirements
| System Requirement | Minimum Requirement | 
|----------|----------|
| **OS**  | Ubuntu or other Linux-based OS | 
| **Disk space**|  20 GB | 
| **RAM**  |  4 GB|
| **Processor**  |  Dual-core recommended|
| **Instance Type**  |  t2.small|

 
## Pre-requisites

| Dependencies | Details| 
|----------|----------|
| **REST APIs**  | The frontend application have dependencies on other REST API of OT-Microservices like Employee, Attendance and Salary APIs which need to be configured. | 
| **Node.js**|  Provides the runtime environment for executing JavaScript on the server-side and building and packaging React code | 
| **NPM (Node Package Manager)**  |  Used to install, manage and run dependencies(java script libraries and tools) that the application depends upon. NPM helps manage these dependencies by adding them to a package.json file, which lists all the libraries our application depends on.|


## Architecture

![image](https://github.com/user-attachments/assets/3fe57c96-3e8b-4407-afc3-1beb61163959)

## Installation Steps
For the Frontend PoC, follow the steps mentioned below:

![image](https://github.com/user-attachments/assets/ba5684a9-bb4e-4e52-a8c8-14d0c8749d5f)

1. **Update Packages**
First step is to update the packages (instance type t2.small, volume 20GB)
```sh 
    sudo apt update
    sudo apt list --upgradable
```

2. **Clone the Repository:**
    ```sh
    git clone https://github.com/OT-MICROSERVICES/frontend.git
    cd frontend
    ```
![image](https://github.com/user-attachments/assets/8c1ec38c-be8d-41c7-bbb4-9cfa59847c37)

 
3. **Install nodejs:**

```sh 
    sudo apt update
    sudo apt install nodejs -y
    nodejs -v
```

![image](https://github.com/user-attachments/assets/aec1ec30-bc74-4839-ad11-e411a996a290)

4. **Install npm:**

```sh 
    sudo apt install npm
    npm -v
```
5. **Create directory name `public`** into frontend directory and create `index.html` file Where we have add following content.

```
html<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>React Frontend App</title>
</head>

<body>
  <div id="root"></div>
  <h1>Welcome to Frontend Web Page</h1>
</body>
</html>
```
![image](https://github.com/user-attachments/assets/fe5588ac-b25b-45cd-a300-847bf0846c1b)

![image](https://github.com/user-attachments/assets/81787afe-aceb-4950-bd2f-5ab4c989796e)


6. **Edit the package.json file:**
In the `package.json` change the ip address with the public ip address in the proxy with specified port.


7. **Build the application:**
For building the application. we can use make command from the Makefile.

```sh
    make build
```
![image](https://github.com/user-attachments/assets/18aa9306-b390-437b-a8ea-ff5df5657a02)
To resolve this error, run the following command
export NODE_OPTIONS=--openssl-legacy-provider

![image](https://github.com/user-attachments/assets/49d33a2a-3d18-4841-ab22-93e83278e701)

8. **Run the application:**
The command to run the application is as follows

```sh
    npm start
```
![image](https://github.com/user-attachments/assets/8c37e206-52c4-402c-8bea-7d7ace279251)


8. **Output:**
Finally we get the output by hitting the public ip of the VM:

![image](https://github.com/user-attachments/assets/f58df287-7f41-4734-b3a1-35a85c137746)

## Conclusion
The Frontend API is a robust microservice designed to manage the user interface within the OT-Microservices architecture. The API is dynamic and interactive as it is based on ReactJS, which is a high-performance JavaScript library.

[Please click here for a detailed documentation of Frontend API of OT-Microservices](https://github.com/kshamatap/OT-Microservices/blob/main/FrontendPoC_V1.md)  

## Contact
| Name          | Email Address       |
|---------------|---------------------|
| Kshamata |  kshamata.prasad.snaatak@mygurukulam.co|



##  Reference Links
| Links | Description      |
|-----  |--------------------------|
| https://nodejs.org/en/download/package-manager/all | For nodejs Installation | 
| https://www.geeksforgeeks.org/how-to-install-node-js-and-npm-on-ubuntu/  | For NPM Installation |
