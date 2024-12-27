# POC for Code Compilation

| Created     |    Version   | Author | Comment | Reviewer | Date |
|:------------------:|:-------------:|:-------------:|:-------------:|:------------------:|:--------:|
| 20-12-2024   | V1   | Raman Tripathi | Internal Review |   | |
|   |    | Raman Tripathi | L0 |  | 
|  |  | Raman Tripathi | L1  |  |
| |  |  Raman Tripathi | L2  |  |

## Table of Contents

- [Introduction](#introduction)
- [Prerequisites](#prerequisites)
- [Steps for Golang Based Code Compilation](#steps-for-go-lang-based-code-compilation)
- [Final Output](#final-output)
- [Contacts](#contacts)

## Introduction


This Proof of Concept (POC) demonstrates how to perform Golang based code compilation using **Go Build** as a compilation tool, and in this POC we are going use employee-api repository which is written in Golang.

## Prerequisites

**Golang** - [Installing Golang on Linux](https://www.cyberciti.biz/faq/how-to-install-gol-ang-on-ubuntu-linux/)

## Steps for Golang Based Code Compilation

**1. Clone the GoLang Project**
- First, clone your GoLang project from the Git repository.

```sh
git clone https://github.com/OT-MICROSERVICES/employee-api.git
```

**2. Run GolangCI-Lint**


```sh
go build main.go

```

## Final Output
Once the build is completed it will create an executable file for Employee-Api as shows in the below screenshot.

<img width="766" alt="image" src="https://github.com/user-attachments/assets/c97208ae-c022-4c20-a6a0-e3835053ef0a" />

## Contacts

For more information, feedback, or assistance, feel free to contact:
| Name         | Email address                       |
|--------------|-------------------------------------|
| Raman Tripahi | raman.tripathi.snaatak@mygurukulam.co  |


