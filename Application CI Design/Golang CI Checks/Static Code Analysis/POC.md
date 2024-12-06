
# POC Static Code Analysis with GolangCI-Lint

| Author      | Created on  | Version    | Last updated by | Last edited on |
|-------------|-------------|------------|-----------------|----------------|
|Raman Tripathi| 6-12-24    | Version 1  | Raman Tripathi   | 6-12-24       |

## Table fo content
- [Introduction](#introduction)
- [Prerequisites](#pre-requisites)
- [System Requirements](#system-requirements)
- [Dependencies](#dependencies)
- [Getting Started](#getting-started)
- [Best Practices](#best-practices)
- [Recommendation](#recommendation)
- [Conclusion](#conclusion)
- [Contact Information](#contact-information)
- [References](#references)

## Introduction
GolangCI-Lint integrates multiple linters into a single, fast tool that can detect issues early in the development process. The purpose of GolangCI-Lint is to automate code quality checks, ensuring that the code adheres to best practices and standards, and to catch potential errors before they reach production.

## Pre-requisites

### System Requirements

| Hardware Specifications | Minimum Recommendation |
|-------------------------|-------------------------|
| CPU                     | 1 GHz                   |
| RAM                     | 512 MB                  |
| Disk Space              | 100 MB                  |

### Dependencies

#### Build Time Dependency
- Go  (version 1.17 or higher)

## Getting Started 

### Step 1 Install Go
Ensure that Go is installed on your system. If not, download and install it from the [official Go website](https://golang.org/dl/).
go install github.com/golangci/golangci-lint@latest.
Verify the installation
```
go version
```


### Step 2 Install GolangCI-Lint
Install GolangCI-Lint using the following command:
```
wget https://go.dev/dl/go1.22.4.linux-amd64.tar.gz
```
Verify the installation:
```
golangci-lint --version
```



### Step 3 Clone the project repository
We have a projcet which is based on go language 
```
git clone https://github.com/OT-MICROSERVICES/employee-api.git
```


### Step 4 Run GolangCI-Lint
```
cd /OT-MICROSERVICES/employee-api

golangci-lint run 
```



## Conclusion
Using GolangCI-Lint for static code analysis in Go projects is highly recommended due to its speed, flexibility, and ease of integration. It helps maintain high code quality and ensures that potential issues are detected early in the development cycle. For projects requiring more extensive analysis and multi-language support. With the help of GolangCI-Lint we can easily found errors and vulnerability . hence we are using this tool for further project.

## Contact Information

For more information, feedback, or assistance, feel free to contact:
| Name         | Email address                       |
|--------------|-------------------------------------|
| Raman Tripahi | raman.tripathi.snaatak@mygurukulam.co  |

## References 

| Links          | Description                          | 
| ------------- |:--------------------------------------:|
|   https://analysis-tools.dev/tag/go  | For Information pupose|
|   https://github.com/golangci/golangci-lint/discussions/3785  | Commands |
