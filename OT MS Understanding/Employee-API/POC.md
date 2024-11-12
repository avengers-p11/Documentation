# README.md 
| **Author** | **Created on** | **Last updated by** | **Last edited on** |
|------------|----------------|----------------------|-------------------|
|Anjali Dhiman  | 12-11-24    | Anjali Dhiman      | 12-11-24           |

# PURPOSE
Employee API is a Go-based microservice designed to manage all employee-related data and transactions within the OT-Microservices stack. It provides a centralized backend service for storing and accessing employee information and can run across multiple operating systems, as it is platform-independent. The application requires the Go runtime for execution.
### Supported Features of the Employee API:
- GO: A fast, lightweight web framework. It provides routing, middleware handling, and API request management.
- ScyllaDB: Utilized as the primary database for storing all employee data. ScyllaDB is a high-performance NoSQL database compatible with Cassandra, ensuring scalability and fast data access.
- Redis (Optional): Used as a cache layer for storing frequently accessed employee data, reducing database load and improving response times.
- Swagger/OpenAPI: Integrated for API documentation, making it easier to interact with and understand the available endpoints and data structures, and for testing the API.
- Database Migrations: Managed using the migrate tool to handle database schema changes and ensure consistency across environments.
# Pre-requisites 
- GO
- Scylladb
- Redis
- Migrate
- Make command
# System Requirements
| **Requirements** | **Details** |
|---------|---------|
| OS |  Ubuntu 22.4 |
| Vm type | t2 medium |
| Disk space | 20 GB |

#  Architecture 
![image](https://github.com/user-attachments/assets/a10136d5-2733-4460-9615-4ac2af64dbee)

# Step by Step Guidance 
This guide explains how to set up a virtual machine (VM), install dependencies, configure the database and caching services, and run the `employee-api` application. Follow each step carefully to ensure the application is correctly installed and functioning.

# Create a Virtual Machine
-	**VM Size**: t2.large
-	**Disk Size**: Up to 20GB
-	**Operating System**: Ubuntu 22.04

# 2. Access the VM
### SSH into the VM using your public key:
```bash
$ ssh -i <your-key.pem> ubuntu@<your-public-ip>
```

# Clone the Repository
### 1. Clone the employee-api repository from GitHub:
```bash 
$ git clone https://github.com/OT-MICROSERVICES/employee-api.git
```

### 2. Change to the project directory:

```bash 
$ cd employee-api/
 ```

![Screenshot 2024-11-12 140451](https://github.com/user-attachments/assets/ca899c62-1e71-4703-87f5-7a8494a410e1)


# Installation of prerequisites required for employee-api
## Before you can run the Employee API, ensure that the following software and services are installed:

# Install Go (Golang)
### 1. Update the package list:

```bash
$ sudo apt update
```

### 2. Install Go with this command:

```bash
$ sudo apt install golang-go
```

### 3. Verify installation:
  
```bash
$ go version
```

# Install Make

### 1. Update package list:
 
```bash
$ sudo apt update
```

### 2. Install Make:
  
```bash
$ sudo apt install make
```

![Screenshot 2024-11-12 145352](https://github.com/user-attachments/assets/c452cfd7-a1d2-4b82-9d45-67d4f7488dd3)


# Install jq
### 1. If we encounter errors related to jq while running the make command example:
![Screenshot 2024-11-12 145455](https://github.com/user-attachments/assets/a8015482-c36f-4350-a979-0f1fe348cf54)


### 2. we can install jq with the following commands:

```bash
$ sudo apt update
```

```bash 
$ sudo apt install -y jq
```


# Scylladb Installation and configuration
### 1. Install a repo file and add the ScyllaDB APT repository to your system:

```bash
$ sudo mkdir -p /etc/apt/keyrings

$ sudo gpg --homedir /tmp --no-default-keyring --keyring /etc/apt/keyrings/scylladb.gpg --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys A43E06657BAC99E3
```

### 2. Add ScyllaDB repository:
  
```bash
$ sudo wget -O /etc/apt/sources.list.d/scylla.list http://downloads.scylladb.com/deb/debian/scylla-6.2.list
```

![Screenshot 2024-11-12 141116](https://github.com/user-attachments/assets/ab1d7faf-e3ef-41e9-8d84-9a830bd85777)

### 3. Install ScyllaDB packages.

```bash
$ sudo apt-get update`

$ sudo apt-get install -y scylla
```

## **Start ScyllaDB**:

### 1. Check if ScyllaDB is running:

```bash 
$ sudo systemctl status scylla-server
```

### 2. If ScyllaDB is not running, update the configuration file:

```bash
$ sudo vi /etc/scylla/scylla.yaml
```


### 3. Configure I/O settings for ScyllaDB on your VM

```bash
$ sudo /opt/scylladb/scripts/scylla_io_setup
```

![Screenshot 2024-11-12 175205](https://github.com/user-attachments/assets/c6e9883b-1e08-4159-a7b5-a486db9fe076)

### 4. Update configuration file of scylla
```bash
 Add these configurations:

rpc_address <private-ip>`
  
authenticator: PasswordAuthenticator
authorizer: CassandraAuthorizer
```

### 5. Restart ScyllaDB

```bash 
$ sudo systemctl start scylla-server
```

### 6. Verify ScyllaDB status:

```bash
$ sudo systemctl status scylla-server
```

![Screenshot 2024-11-12 142659](https://github.com/user-attachments/assets/11a54d9e-9783-466f-831f-260cdc9e0e3f)

### 7. Command to connect to ScyllaDB

```bash
$ cqlsh 192.168.0.96 9042 -u cassandra -p cassandra
```

### 8. Created user ‘scylladb’ with password as ‘password

```bash
$ CREATE USER scylladb WITH PASSWORD 'password' SUPERUSER;
```

### 9.  Created keyspace employee_db

```bash
$ CREATE KEYSPACE employee_db WITH REPLICATION = { 'class': 'SimpleStrategy', 'replication_factor': 1 };
```

### 10. Verify the empolyee_db
```bash
$ DESCRIBE KEYSPACES;
```

![Screenshot 2024-11-12 143047](https://github.com/user-attachments/assets/6e497b04-ba6c-4ce5-b3bf-1577e6d4b423)


# Install Redis (Cache)
### 1. For installing Redis:

```bash
$ sudo apt update

$ sudo apt install redis-server -y
```

![Screenshot 2024-11-12 145307](https://github.com/user-attachments/assets/bab93488-5ead-4a66-bae3-ade088fc0cfb)

### 2. Verify Installation

```bash
$ redis-server --version
```

# Access Redis CLI
### 3. To begin configuring Redis, you will need to access the Redis command-line interface (CLI):

```bash
$ redis-cli
```

### 4. Configure User Permissions and Authentication
This step ensures that only authorized users can access and perform actions in Redis.

```bash
$ ACL SETUSER scylla on >password ~* +@all
```

### 5. List the existing ACL rules

```bash
$ ACL LIST
```

# Update Redis Configuration File
### 1. To ensure Redis listens on the correct IP addresses, you need to update the Redis configuration file "redis.conf"

```bash
$ sudo vi /etc/redis/redis.conf
```

### 2. Add your server’s private IP (e.g., 192.168.0.101) to the bind directive, which will allow Redis to listen on both localhost and the specified IP address.

```bash
$ bind 127.0.0.1 <private IP>
```

### 3. Start Redis Server

After installation, you can start Redis by running:

```bash
$ sudo systemctl start redis-server

$ sudo systemctl enable redis-server
```

### 4.  To verify Redis is running, you can check its status:

```bash
$ sudo systemctl status redis-server
```

# Install migrate Tool
### This step to install migrate tool:

```bash
$ go install -tags 'postgres' github.com/golang-migrate/migrate/v4/cmd/migrate@latest
```

### Add the $GOPATH/bin directory to our $PATH so that the migrate command can be used:

```bash
$ export PATH=$PATH:$(go env GOPATH)/bin
```

![Screenshot 2024-11-12 150430](https://github.com/user-attachments/assets/04258322-b96a-4155-9a67-32a91603bde8)


# Run Database Migrations

### 1. Run the migration commands from the Makefile:

```bash
$ make run-migrations
```

If migration is successful, continue to the next step. If you encounter errors, ensure ScyllaDB settings are correctly configured.

# Testing the Application

### 1. **Run Unit Tests**:
Execute unit tests to check code quality and coverage:

```bash
$ go test $(go list ./... | grep -v docs | grep -v model | grep -v main.go) -coverprofile cover.out
```

### 2. **Generate Test Coverage Report**:
For an HTML coverage report:
     
```bash
$ go tool cover -html=cover.out
```

### 4. Run the ./employee-api executable on the server, then proceed with the next steps

### 5. Access the Application

1. Open your browser and visit:
   
```bash
$ http://<public-ip-of-your-server>:8080/swagger/index.html
```

This should display the Swagger API documentation interface for the `employee-api`.

![Screenshot 2024-11-12 150626](https://github.com/user-attachments/assets/c3c008e5-df6c-412c-8d45-c3d48767279a)






















