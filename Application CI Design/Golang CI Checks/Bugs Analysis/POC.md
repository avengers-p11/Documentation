# Proof of Concept | Bug Analysis
![image](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTCUw8YTFHb305eWBPpibrvVTOSijntvbRZQA&s)

| **Author** | **Created on** | **Version** | **Last edited on** | **Reviewer** |
|------------|----------------|-------------------|---------------------|----------|
| Raman Tripathi  | 16-11-24      | V1.1  | 16-11-24           |  |

## Table of Contents

- [Prerequisites](#prerequisites)
- [Step-by-Step Installation Guide](#step-by-step-installation-guide)
- [Contact Information](#contact-information)
- [References](#refrences)
***
## Prerequisites
| Component         | Requirements                 | 
| ------------- |:--------------------------------------:|
| Go Environment   |  Ensure Go is installed on your system. You can download and install it from the official Go website.|
|  Go Project |  Have a Go project set up with the necessary project structure and modules.  |
| Sufficient system resources  | Ensure your system has at least 2GB of RAM. |
***

## Step-by-Step Installation Guide

**1. Clone the GoLang Project**
- First, clone your GoLang project from the Git repository.

```sh
git clone https://github.com/OT-MICROSERVICES/employee-api.git
```


**2. Install GoLang-lint**


```sh
sudo apt update
curl -sSfL https://raw.githubusercontent.com/golangci/golangci-lint/master/install.sh | sh -s latest

```

**3. Install Staticcheck**

```sh

go install honnef.co/go/tools/cmd/staticcheck@latest

```

**4. Run GolangCI-Lint**


```sh
golangci-lint run ./...

```
<img width="608" alt="image" src="https://github.com/user-attachments/assets/ac9c38e3-a24e-4874-8ab9-5b46ab63dc64" />


## Contact Information

| Name| Email Address      |
|-----|--------------------------|
| Raman Tripathi | raman.tripathi.snaatak@mygurukulam.co |

| GitHub | URL |
|----------|---------|
|  Raman-tripathi07  |  https://github.com/Raman-tripathi07  |

## References 

|     Links      |       Discription              | 
| ------------- |:--------------------------------------:|
| https://github.com/golangci/awesome-go-linters | for reference   |


***
