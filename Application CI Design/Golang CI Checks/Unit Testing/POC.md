# Golang CI Check | Unit Testing | POC

---

  | Author        | Created on | Version | Last updated by | Last edited on |
  |-------------|---------|-------------|-------------|---------|
  | Raman Tripathi | 20-12-24 | version 1 | Raman Tripathi | 26-11-24 |

---
 ## Table of Contents
 
- [Introduction](#Introduction)
- [Pre-requisite](#Pre-requisite)
- [Performing Unit Testing](#Performing-Unit-Testing)
- [Conclusion](#Conclusion)
- [Contact](#Contact)
- [Refrence](#Refrence)

---

## Introduction

In this Document we are creating the POC of unit testing for the GoLang based API, to get the errors by performing the unit testing.


## Pre-requisite


## Run Time Dependency

| **Name** | **Version** | **Description** |
|------|---------|-------------|
| **go** | Greater then 1.21 | Application is built on this version only |


---

## Performing Unit Testing
 After cloning the repo to the system we run the below command 

 ```bash
go test $(go list ./... | grep -v docs | grep -v model | grep -v main.go) -coverprofile cover.out
```
This command will start executing unit tests.

<img width="959" alt="image" src="https://github.com/user-attachments/assets/4faf55f1-8ae5-40fc-87e2-44c73a17dc98" />


---

## Conclusion
We can say that Unit testing in GoLang ensures code correctness, identifies bugs early, improves code reliability, and promotes efficient debugging and maintenance. We are using Gotest tool to do unit testing in our project.

---

 ## Contact

| Name         | Email address                       |
|--------------|-------------------------------------|
| Raman Tripahi | raman.tripathi.snaatak@mygurukulam.co  |
 
 ---

 ## Refrence

 | Link|Description|
  |:---:|:---:|
  |[Link](https://github.com/avengers-p11/Documentation/blob/main/Application%20CI%20Design/Golang%20CI%20Checks/Unit%20Testing/README.md?plain=1)|Document for the GoLang |

