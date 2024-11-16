
# Salary-api

| **Author** | **Created on** | **Last updated by** | **Last edited on** | **Reviwer L0** |**Reviwer L1** |**Reviwer L2** |
|------------|----------------|----------------------|---------------------|---------------|---------------|---------------|
| Pravesh Kumar      | 11-11-24      | Pravesh Kumar             | 15-11-24           | Khushi | | |

## Table of Contents
- Pre-Requisites
- System Requirements
- Architecture
- Step-by-step installation of [application]
- Clone the salary-api repo in your instance
- Installation of prerequisites required for salary-api
- Scylladb Installation and configuration
- Redis Installation and Configuration
- Install Maven & Java depndancy
- Installation of swagger
- Create the service file for salary-api service
- Install migration tool
- Run the clean package inside the salary-api directory
- Run the migration command
- Run the java runtime command
- Output
- Error
- Conclusion
- Contact Information
- References
  

## Pre-Requisites

The Salary API application have some database, cache manager and package dependencies. Some of the dependencies are optional and some are mandatory. To compile the application, we only need maven as build tool, but for running the application following things are required:-

- [ScyllaDB](https://www.scylladb.com/)

- [Redis](https://redis.io/)

- [Migrate](https://github.com/golang-migrate/migrate)

- [Maven](https://maven.apache.org/)

Maven will be used as package manager to down# Step1: Installation of software Dependenciesload specific version of dependencies to run the Salary API.

## System Requirements

| **Requirement**        | **Details**                  |
|------------------------|------------------------------|
| **OS**                 | Ubuntu or other Linux-based OS |
| **RAM**                | 4 GB minimum                 |
| **Disk Space**         | 20 GB               |
| **Processor**          | Dual-core recommended        | 
| **Instance_Type**    | t2.medium | 


## Architecture

![Screenshot 2024-11-12 at 12 31 28 AM](https://github.com/user-attachments/assets/5e165de8-db61-4c61-a23d-c67027a0988e)

# Step-by-step installation of [application]

``` bash
sudo apt update
```
### Clone the salary-api repo in your instance
``` bash
git clone https://github.com/OT-MICROSERVICES/salary-api.git
```
![Screenshot 2024-11-11 at 10 31 42 PM](https://github.com/user-attachments/assets/37c08836-cf5d-4dc3-bf9f-99f5b2abe207)

# Installation of prerequisites required for salary-api

## Scylladb Installation and configuration

### Install a repo file and add the ScyllaDB APT repository to your system:
``` bash
sudo mkdir -p /etc/apt/keyrings
```
- /etc/apt/keyrings: This is the directory where trusted GPG keys for package sources will be stored. ScyllaDB’s key will be saved here to verify the authenticity of the packages.
  
``` bash
sudo gpg --homedir /tmp --no-default-keyring --keyring /etc/apt/keyrings/scylladb.gpg --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys A43E06657BAC99E3
```
- This command retrieves and adds ScyllaDB’s public GPG key to a keyring at /etc/apt/keyrings/scylladb.gpg. The key is fetched from Ubuntu's key server, allowing APT to verify the authenticity of packages from the ScyllaDB repository.
  
``` bash
sudo wget -O /etc/apt/sources.list.d/scylla.list http://downloads.scylladb.com/deb/debian/scylla-6.2.list
```
- the wget command downloads the ScyllaDB repository configuration file (scylla-6.2.list) and saves it to /etc/apt/sources.list.d/. This file contains the necessary information for APT to locate and access ScyllaDB packages for installation and updates, enabling secure downloads directly from ScyllaDB’s repository.
  
![Screenshot 2024-11-11 at 10 32 02 PM](https://github.com/user-attachments/assets/3a882821-e761-47e4-bfba-851539d93080)

### Install ScyllaDB packages.
``` bash
sudo apt-get update

sudo apt-get install -y scylla
```
![Screenshot 2024-11-11 at 10 32 57 PM](https://github.com/user-attachments/assets/7226ce40-aabc-4f48-a682-878988c8ebed)

### Configure I/O settings for ScyllaDB on your VM
``` bash
sudo /opt/scylladb/scripts/scylla_io_setup
```
- The command configures I/O settings on the system to optimize ScyllaDB performance based on the hardware.

![Screenshot 2024-11-11 at 10 33 25 PM](https://github.com/user-attachments/assets/c495a23a-fcf1-447f-a605-18957ceda9d9)

### Update configuration file of scylla
``` bash
sudo vi /etc/scylla/scylla.yaml
```
#### Added the below lines in the config file:
``` bash
authenticator: PasswordAuthenticator

authorizer: CassandraAuthorizer
```
- These settings enable password authentication and role-based access control in ScyllaDB or Cassandra.
  
#### Updated the rpc_address with server's private IP:

rpc_address: <private_IP>

- The setting rpc_address: <private_IP> configures ScyllaDB or Cassandra to listen for client requests on the specified private IP address, limiting access to internal or private network traffic.

### Restart the scylla-server service and check the status
``` bash
sudo systemctl restart scylla-server.service
```
``` bash
sudo systemctl status scylla-server
```
![Screenshot 2024-11-11 at 10 45 27 PM](https://github.com/user-attachments/assets/516b67a6-c2eb-4ca9-94e9-c24d7fb1d7b5)

### Used below command to get into scylladb
``` bash
cqlsh <private_IP> 9042 -u cassandra -p cassandra
```
- The command connects to a Cassandra or ScyllaDB instance at <private_IP> on port 9042 using the cqlsh tool, with the username and password set to cassandra.

#### Created user ‘scylladb’ with password as ‘password
``` bash
CREATE USER scylladb WITH PASSWORD 'password' SUPERUSER;
```
- The command CREATE USER scylladb WITH PASSWORD 'password' SUPERUSER; creates a new user named scylladb in ScyllaDB or Cassandra with the password password and grants them superuser privileges, allowing full access to all database functions.
  
#### Created keyspace employee_db
``` bash
CREATE KEYSPACE employee_db WITH REPLICATION = { 'class': 'SimpleStrategy', 'replication_factor': 1 };
```
- The command creates a keyspace employee_db with a SimpleStrategy replication strategy and a replication factor of 1, meaning one replica of the data will be stored.
  
#### Verify the employee_db
``` bash
DESCRIBE KEYSPACES;
```
![Screenshot 2024-11-11 at 10 45 42 PM](https://github.com/user-attachments/assets/21686683-9817-40e8-9b24-117bb7f26ede)

## Redis Installation and Configuration
``` bash
sudo apt update
sudo apt install redis-server -y
```
![Screenshot 2024-11-11 at 11 10 37 PM](https://github.com/user-attachments/assets/4dba6c46-3416-4015-941f-e24468f128c0)

## Configuration of redis : Enter into redis
``` bash
redis-cli
```
- The command redis-cli opens the Redis command-line interface to interact with a Redis server.
  
#### Configure user permissions and authentication settings in redis
``` bash
ACL SETUSER scylla on >password ~* +@all
```
- User Enabled (on): Activates scylla so it can connect to Redis.

- Password (>password): Sets password as the required password for scylla to authenticate.

- Key Access (~*): Allows scylla access to all keys in Redis (* as wildcard).

- Command Permissions (+@all): Grants scylla access to all Redis commands by allowing all command categories.
  

#### List the acl
``` bash
ACL LIST
```
- The command ACL LIST in Redis displays the list of all Access Control Lists (ACLs) and their associated rules, showing which users have which permissions for various Redis commands and keys.

### Update the redis config file
``` bash
sudo vi /etc/redis/redis.conf
```
#### update with private IP "bind 127.0.0.1 <private_IP>"
``` bash
sudo systemctl restart redis
```
``` bash
redis-cli -h <private_IP> -p 6379 ping
```
- The command connects to a Redis server at the specified IP and port, sending a PING to check if the server is responsive.

## Install Maven & Java depndancy
``` bash
sudo apt install openjdk-17-jre

sudo apt install maven -y
```
![Screenshot 2024-11-11 at 11 16 34 PM](https://github.com/user-attachments/assets/b6d0eba1-636a-48a2-9104-2ede131c7f97)

## Installation of swagger
``` bash
sudo apt  install jq -y
```
- The command installs the jq tool for processing JSON data using APT, automatically confirming the installation with -y.
  
![Screenshot 2024-11-11 at 11 40 58 PM](https://github.com/user-attachments/assets/c1321697-f6c8-48ed-b982-4a67fbc35bd4)
``` bash
download_url=$(curl -s https://api.github.com/repos/go-swagger/go-swagger/releases/latest | \jq -r '.assets[] | select(.name | contains("'"$(uname | tr '[:upper:]' '[:lower:]')"'_amd64")) | .browser_download_url')
```
- The command retrieves the latest release URL for go-swagger from GitHub, filters the assets based on the system's architecture (e.g., linux_amd64), and stores the download URL in the download_url variable.
  
``` bash
sudo curl -o /usr/local/bin/swagger -L'#' "$download_url"
```
- The command downloads the file from the URL stored in the download_url variable and saves it as /usr/local/bin/swagger, using curl with the -L option to follow redirects. This command requires superuser privileges to save the file in the specified directory.
  
``` bash
sudo chmod +x /usr/local/bin/swagger
```
- The command makes the swagger file executable by granting it the necessary permissions.
  
![Screenshot 2024-11-11 at 11 41 22 PM](https://github.com/user-attachments/assets/65bc8d96-40d0-4904-a4d6-cce0100d19ac)

## Enter into salary-api directory
``` bash
cd salary-api/
```
### Update the contact-points & host in application.yaml to your private ip address from below paths
``` bash
sudo vi src/main/resources/application.yml

sudo vi src/test/resources/application.yml
```
### Create the service file for salary-api service
``` bash
sudo vi /etc/systemd/system/salary-api.service
```
### Content of salary-api service:
``` bash

[Unit]

Description=salary api

After=network.target


[Service]

Type=simple

User=ubuntu

Group=ubuntu

WorkingDirectory=/home/ubuntu/salary-api/

ExecStart=java -jar /home/ubuntu/salary-api/target/salary-0.1.0-RELEASE.jar --server.port=8081

Restart=on-failure

RestartSec=5

StandardOutput=journal

StandardError=journal


[Install]

WantedBy=multi-user.target

```

### Enable and start the salary-api service
``` bash
sudo systemctl enable salary-api.service
sudo systemctl start salary-api.service
```
### Restart the salary-api service
``` bash
sudo systemctl restart salary-api.service
```
## Install migration tool

### Download the zip file of the migration tool(migrate)
``` bash
curl -L https://github.com/golang-migrate/migrate/releases/download/v4.15.2/migrate.linux-amd64.tar.gz | tar xvz
```
- The command downloads and extracts the migrate tool for Linux (v4.15.2) from GitHub, using curl to fetch the .tar.gz archive and tar to extract it.
  
![Screenshot 2024-11-11 at 11 41 47 PM](https://github.com/user-attachments/assets/7820ab8d-81cd-4592-a814-1eef79804cc3)

### Move the file to below location
``` bash
sudo mv migrate /usr/local/bin/migrate
```
- The command moves the migrate binary to /usr/local/bin/, making it accessible system-wide for execution. This requires superuser privileges.
  
### Check the version of migrate
``` bash
migrate --version
```
### Update below config files with public IP:
``` bash
cd /salary-api

sudo vi src/main/java/com/opstree/microservice/salary/config/OpenAPIConfig.java 
```

//
devServer.setUrl("http://18.212.99.151:8080");
//
``` bash
sudo vi src/test/java/com/opstree/microservice/salary/config/OpenAPIConfigTests.java 
```
//
assertEquals("http://18.212.99.151:8080", server.getUrl());
//

## Update the migration.json with private IP
``` bash
sudo vi migration.json
```
## run the clean package inside the salary-api directory
``` bash
mvn clean package
```
- The command mvn clean package cleans previous build artifacts and packages the project into its final artifact (e.g., .jar or .war).
  
![Screenshot 2024-11-11 at 11 45 01 PM](https://github.com/user-attachments/assets/c35b4369-96c8-4658-b3ba-0ff202da5c01)
![Screenshot 2024-11-11 at 11 45 12 PM](https://github.com/user-attachments/assets/200cd88b-f05f-4fa5-b62b-ee652faf1de7)


### Install make command
``` bash
sudo apt install make
```
- The command installs the make utility, which automates the build process, using APT with superuser privileges.
  
## Run the migration command
``` bash
make run-migrations
```
- The command runs database migrations as defined in the Makefile under the run-migrations target.
  
## Run the java runtime command
``` bash
java -jar target/salary-0.1.0-RELEASE.jar
```
- The command runs the Java application packaged in the salary-0.1.0-RELEASE.jar file.
  
## Output

![Screenshot 2024-11-11 at 11 52 13 PM](https://github.com/user-attachments/assets/a990c12e-2c05-4765-b7c3-86900693e22e)

## Error ##

### Port is already is in use
``` bash
sudo lsof -i :8080

sudo kill -9 <pid>

Run the command again "java -jar target/salary-0.1.0-RELEASE.jar"
```

![Screenshot 2024-11-15 at 2 18 43 PM](https://github.com/user-attachments/assets/b2e7061f-bd2d-45e4-bf46-b8c4faaa5c78)

## Conclusion

The Salary API is an essential service in the OT-Microservices system, designed for efficient management of salary transactions. Using ScyllaDB for scalable storage, Redis for caching, Migrate for database version control, Swagger for interactive documentation, and Maven for streamlined builds, it offers high performance and reliability. The API integrates seamlessly with other microservices, supporting fast data access and scalability, which enhances user experience and supports continuous deployment in an enterprise environment.


# Contact Information

| **Name** | **Email address**            | **Github ID**
|----------|-------------------------------|-------------------|
| Pravesh Kumar    |  pravesh.kumar611@gmail.com           | Pravesh899 |

# References

| **Link** | **Description**            |
|----------|-------------------------------|
| [What is Redis and How Does it Work? - Medium](https://medium.com/@ayushsaxena823/what-is-redis-and-how-does-it-work-cfe2853eb9a9)   |  Overview of Redis' structure and functions.          |
| [ScyllaDB Installation Guide](https://opensource.docs.scylladb.com/stable/getting-started/install-scylla/install-on-linux.html)   | Comprehensive guide for installing ScyllaDB on Linux. |
| [Swagger](https://swagger.io/docs/specification/v2_0/what-is-swagger/)   | Swagger Docs |
| [Maven](https://maven.apache.org/what-is-maven.html)   | Maven Introduction |

