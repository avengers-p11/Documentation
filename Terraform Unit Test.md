# Terraform Unit Test POC

![image](https://github.com/user-attachments/assets/fad9161b-d309-45c7-9c2d-a8fa22910b62)


| Created     |    Version   | Author | Comment | Reviewer | Date |
|:------------------:|:-------------:|:-------------:|:-------------:|:------------------:|:--------:|
| 20-01-2025   | V1   | Mohit Saini | L0 | | |

# Table of Contents
- [**Introduction**](#introduction)
- [**What is Unit Testing in Terraform?**](#what-is-unit-testing-in-terraform)
- [**Why Unit Testing in Terraform?**](#why-unit-testing-in-terraform)
- [**Tools for Parameter Checklist**](#tools-for-parameter-checklist)
- [**Terratest**](#terratest)
- [**Why Terratest?**](#why-terratest)
- [**Terratest Working Flow**](#terratest-working-flow)
- [**Pre-requisites**](#pre-requisites)
- [**Installation Steps for Terratest**](#installation-steps-for-terratest)
- [**Conclusion**](#conclusion)
- [ [**Contacts**](#contacts)
- [**References**](#references)

# Introduction
Testing is the process of checking the functionality of the application whether it fulfills the requirement or not. Unit tests in Terraform are used to validate the behavior of individual resources or modules, ensuring that they function as expected when given specific input, thereby contributing to the robustness and reliability of the infrastructure as code.

# What is Unit Testing in Terraform?
Unit tests in Terraform help ensure that individual resources and modules perform correctly.

# Why Unit Testing in Terraform?
| **Benefit**              | **Description**                                                                                                 |
|--------------------------|-----------------------------------------------------------------------------------------------------------------|
| **Early Bug Detection**   | Unit tests identify and isolate issues early in the development cycle.                                          |
| **Improved Code Quality** | Encourages writing more modular, maintainable, and testable Terraform code.                                      |
| **Increased Confidence**  | Provides confidence that your infrastructure code is reliable and predictable.                                  |
| **Faster Development**    | Enables faster development iterations with reduced risk.                                                       |
| **Reduced Risk**          | Minimizes the risk of downtime and service disruptions caused by infrastructure failures.                        |
| **Improved Collaboration**| Provides a shared understanding among team members for Terraform modules.                                       |
| Provides a shared understanding of the expected behavior of Terraform modules among team members. Facilitates better communication and collaboration within development teams. |



# Tools for Parameter checklist 

| **Parameter**                     | **Checkov** | **tfsec** | **Terratest** | **OPA/Conftest** | **Infracost** | **GitLeaks** | **Sentinel** | **Terrascan** | **tflint** | **Kitchen** |
|------------------------------------|-------------|-----------|---------------|------------------|---------------|--------------|--------------|----------------|------------|----------------------|
| **Hard-coded credentials**         | ✔️          | ✔️        | ❌            | ✔️               | ❌            | ✔️           | ✔️           | ✔️             | ✔️         | ✔️              |
| **Encryption for sensitive data**  | ✔️          | ✔️        | ❌            | ✔️               | ❌            | ❌           | ✔️           | ✔️             | ✔️         | ✔️              |
| **Overly permissive IAM policies** | ✔️          | ✔️        | ❌            | ✔️               | ❌            | ❌           | ✔️           | ✔️             | ✔️         | ✔️              |
| **Open ports and unrestricted CIDR** | ✔️         | ✔️        | ❌            | ✔️               | ❌            | ❌           | ✔️           | ✔️             | ✔️         | ✔️             |
| **Tagging enforcement**            | ✔️          | ❌        | ❌            | ✔️               | ❌            | ❌           | ✔️           | ❌             | ❌         | ✔️              |
| **Naming conventions**             | ✔️          | ❌        | ❌            | ✔️               | ❌            | ❌           | ✔️           | ❌             | ❌         | ✔️              |
| **Approved AMIs and instance types** | ✔️         | ✔️        | ❌            | ✔️               | ❌            | ❌           | ✔️           | ✔️             | ✔️         | ✔️             |
| **Subnet CIDR blocks**             | ✔️          | ✔️        | ❌            | ✔️               | ❌            | ❌           | ✔️           | ✔️             | ✔️         | ✔️              |
| **Route table configurations**     | ✔️          | ✔️        | ❌            | ✔️               | ❌            | ❌           | ✔️           | ✔️             | ✔️         | ✔️              |
| **Load balancer health checks**    | ❌          | ❌        | ✔️            | ❌               | ❌            | ❌           | ❌           | ❌             | ❌         | ✔️              |
| **DNS records correctness**        | ❌          | ❌        | ✔️            | ❌               | ❌            | ❌           | ❌           | ❌             | ❌         | ✔️              |
| **Resource creation correctness**  | ❌          | ❌        | ✔️            | ❌               | ❌            | ❌           | ❌           | ❌             | ❌         | ✔️              |
| **Scaling policies**               | ❌          | ❌        | ✔️            | ❌               | ❌            | ❌           | ❌           | ❌             | ❌         | ✔️              |
| **Cost estimation**                | ❌          | ❌        | ❌            | ❌               | ✔️            | ❌           | ❌           | ❌             | ❌         | ❌              |
| **Secrets accidentally committed** | ❌          | ❌        | ❌            | ❌               | ❌            | ✔️           | ❌           | ❌             | ❌         | ❌              |
| **Failed apply simulation**        | ❌          | ❌        | ✔️            | ❌               | ❌            | ❌           | ❌           | ❌             | ❌         | ✔️              |
| **State file locking mechanism**   | ❌          | ❌        | ✔️            | ❌               | ❌            | ❌           | ❌           | ❌             | ❌         | ✔️              |
| **Expensive instance types**       | ❌          | ❌        | ❌            | ❌               | ✔️            | ❌           | ❌           | ❌             | ❌         | ❌              |
| **Unused resources**               | ✔️          | ✔️        | ❌            | ✔️               | ❌            | ❌           | ✔️           | ✔️             | ✔️         | ✔️              |
| **Backup configuration**           | ✔️          | ✔️        | ❌            | ✔️               | ❌            | ❌           | ✔️           | ✔️             | ✔️         | ✔️              |



# Terratest
Terratest is a free tool used to test infrastructure created with Terraform. It helps check small parts (unit tests), connected parts (integration tests), and the entire setup (end-to-end tests) of cloud infrastructure.

![image](https://github.com/user-attachments/assets/f2bfd954-252b-4860-b9f9-299b111155cb)



# Why Terratest?
| Step                          | Description                                                                 |
|-------------------------------|-----------------------------------------------------------------------------|
| **Deploy a Terraform Configuration** | Deploy the infrastructure defined in Terraform to create cloud resources.     |
| **Write Tests in Go**              | Use Go language to write tests that validate the deployed infrastructure.      |

# Terratest Working Flow
![image](https://github.com/user-attachments/assets/711c0b32-7aca-4f62-b116-9db984deef74)

# Test infrasturece code with Terratest
![image](https://github.com/user-attachments/assets/fbbbaba5-193a-43b7-9aa6-fa7d65d5142d)


# Pre-requisites
| **Binary**  | **Description**                         | 
|-------------|-----------------------------------------|
| **Go**      | Programming language used for Terratest | 
| **Terraform** | Infrastructure as code tool            | 
| **AWS CLI** | AWS Command Line Interface (Optional)   | 
| **Terratest** | Testing framework for Terraform        | 

# Installation Steps for Terratest

Steps 1. Update your package list

```
sudo apt update
```
![image](https://github.com/user-attachments/assets/7299ea26-620c-4e5c-a4c8-bc739be9abd5)



## Steps 2. Install Go using the package manager

```
sudo apt install golang-go
```
![image](https://github.com/user-attachments/assets/e0e66265-7f3a-46c7-b7d9-7917f00fc909)


## Sets3. Verify the installation

```
go version
```
![image](https://github.com/user-attachments/assets/585ecb98-4138-444a-99ee-5c2fa9f9dd30)


## Steps 4. Terrafrom installation 

![image](https://github.com/user-attachments/assets/3be98f4e-36e7-48f2-b136-50ad59f9fd8d)

## Steps 5. create test file 

![image](https://github.com/user-attachments/assets/501ced09-049e-46c4-b57f-56fa3658bade)

## Steps 6. test file script

![image](https://github.com/user-attachments/assets/fe8a9a5a-fe19-46df-8553-fdf47725fb01)

## Steps 7.

![image](https://github.com/user-attachments/assets/a5271da2-62d5-4bd4-b38b-5aa65dc567e3)

## Conclusion
The purpose of this Proof of Concept was to evaluate Terratest as a tool for automating Infrastructure as Code (IaC) testing. It demonstrated the feasibility and effectiveness of validating Terraform configurations and ensuring infrastructure reliability before deployment.

## Contacts

| Name| Email Address      |
|-----|--------------------------|
| Mohit Saini | mohit.saini.snaatak@mygurukulam.co |

## References

| **Title**            | **Link**                                                                                  |
|-----------------------|------------------------------------------------------------------------------------------|
| Terratest    | [Link](https://medium.com/@a.warkhade98/testing-your-infrastructure-as-code-using-terratest-3b1f774336ce)          |
| Terratest working   | [Link](https://blog.nashtechglobal.com/getting-started-with-terratest/) | 
