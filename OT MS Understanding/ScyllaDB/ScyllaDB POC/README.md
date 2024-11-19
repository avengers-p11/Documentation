![image](https://github.com/user-attachments/assets/31897406-2fe7-449a-9df7-6dc55cd9ec5e)


# ScyllaDB POC

## Author

| Created/Modified | Version | Author               | Comment         | L0 Reviewer      |
|-------------------|---------|----------------------|-----------------|------------------|
| 18-11-2024        | V1     | Anjali Dhiman | L0    |  Khushi Malhotra |

## Table Of Content

- [Introduction](#introduction)
- [Pre-requisites](#pre-requisites)
- [System Requirements](#system-requirements)
- [Scylladb Installation and configuration](#scylladb-installation-and-configuration)
- [Official Support](#official-support)
- [Contacts](#contacts)
- [References](#references)


## Introduction
This documentation provides an overview of how to set up ScyllaDB locally. ScyllaDB is a high-performance, open-source distributed NoSQL database designed for ultra-low-latency and high-throughput applications. It supports the same protocol as Apache Cassandra, which allows for seamless integration and migration from Cassandra to ScyllaDB. In addition to setup instructions, this documentation also covers monitoring techniques for ScyllaDB, ensuring you can maintain optimal performance and health of your database cluster. Key monitoring commands, such as nodetool status, will be discussed to help you effectively manage and troubleshoot your ScyllaDB deployment.

## Pre-requisites

Before diving into the Installation of scyllaDB, let’s ensure the following pre-requisites meets as its requirements.

## Software Overview
|                  |         |
|:----------------:|:-------:|
| **Software Name:**| ScyllaDB|
|**Version:**| 6.2 |

## System Requirements
| **Requirements** | **Details** |
|---------|---------|
| OS |  Ubuntu 22.4 |
| Vm type | t2 medium |
| Disk space | 20 GB |



# Scylladb Installation and configuration
### Two Methods to Install ScyllaDB on a Linux Machine
![Screenshot 2024-11-18 170054](https://github.com/user-attachments/assets/25da80d4-4f36-41c4-bc0a-0a8374e91ff3)


# Method 1. Using the Installation Script
### The quickest way to install ScyllaDB is by using the provided script.

## 1. Run the installation script:
```
curl -sSf https://get.scylladb.com/server | sudo bash
sudo scylla_io_setup
```
![Screenshot 2024-11-18 161722](https://github.com/user-attachments/assets/3be1e5c9-76dc-42a1-85ba-27e17721ed84)


## 2. Start the ScyllaDB server and check its status:
```
sudo systemctl start scylla-server
sudo systemctl status scylla-server
```
![Screenshot 2024-11-18 161831](https://github.com/user-attachments/assets/9c6a0d24-22a6-44d9-ae19-79b1757f9dd7)

## 3. Access ScyllaDB using cqlsh:
```
cqlsh
```
![Screenshot 2024-11-18 161912](https://github.com/user-attachments/assets/3654db11-4887-4fce-895b-45d8211ac164)

# Method 2. Step-by-Step Installation on Ubuntu
## Follow these detailed steps to install ScyllaDB manually on Ubuntu.

## 1. Install a repo file and add the ScyllaDB APT repository to your system:

```bash
sudo mkdir -p /etc/apt/keyrings

sudo gpg --homedir /tmp --no-default-keyring --keyring /etc/apt/keyrings/scylladb.gpg --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys A43E06657BAC99E3
```

## 2. Add ScyllaDB repository:
  
```bash
sudo wget -O /etc/apt/sources.list.d/scylla.list http://downloads.scylladb.com/deb/debian/scylla-6.2.list
```

![Screenshot 2024-11-12 141116](https://github.com/user-attachments/assets/ab1d7faf-e3ef-41e9-8d84-9a830bd85777)

### 3. Install ScyllaDB packages.

```bash
sudo apt-get update`

sudo apt-get install -y scylla
```

## **Start ScyllaDB**:

### 1. Check if ScyllaDB is running:

```bash 
sudo systemctl status scylla-server
```

### 2. If ScyllaDB is not running, update the configuration file:

```bash
sudo vi /etc/scylla/scylla.yaml
```

### 3. Update configuration file of scylla
```bash
 Add these configurations:

rpc_address <private-ip>`
  
authenticator: PasswordAuthenticator
authorizer: CassandraAuthorizer
```

### 4. Configure I/O settings for ScyllaDB on your VM

```bash
sudo /opt/scylladb/scripts/scylla_io_setup
```

![Screenshot 2024-11-12 175205](https://github.com/user-attachments/assets/c6e9883b-1e08-4159-a7b5-a486db9fe076)



### 5. Restart ScyllaDB

```bash 
sudo systemctl start scylla-server
```

### 6. Verify ScyllaDB status:

```bash
sudo systemctl status scylla-server
```

![Screenshot 2024-11-12 142659](https://github.com/user-attachments/assets/11a54d9e-9783-466f-831f-260cdc9e0e3f)

## Conclusion

ScyllaDB is a high-performance, scalable NoSQL database that offers low-latency operations and efficient resource utilization, making it an ideal choice for modern microservices like the Employee API. Its distributed architecture ensures high availability and fault tolerance, while its compatibility with Cassandra enables seamless integration with existing tools and drivers. In the Employee API, ScyllaDB is used to manage large datasets efficiently, ensuring fast query performance and scalability to handle growing user demands. Its ability to support horizontal scaling and tunable consistency guarantees reliability, making it a robust backend for managing employee data.


## Official Support

|                |                                       |
|:--------------:|:-------------------------------------:|
|[Support](https://www.scylladb.com/product/support/)|Reach out to ScyllaDB support for any issues or questions|
|[Community](https://forum.scylladb.com/)|Join the ScyllaDB community forums for discussions and help from other users|


## Contacts

| Name| Email Address      | GitHub | URL |
|-----|--------------------------|----------|---------|
| Anjali Dhiman | anjali.dhiman.snaatak@mygurukulam.co |  Anjaliopstree  |  https://github.com/Anjaliopstree  |

## References

[Documentation](https://github.com/avengers-p11/Documentation/blob/main/OT%20MS%20Understanding/ScyllaDB/ScyllaDB%20Documentation/README.md)

[ScyllaDB Installation Guide](https://opensource.docs.scylladb.com/stable/getting-started/install-scylla/index.html)
