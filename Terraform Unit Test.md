# Terraform Unit Test

![image](https://github.com/user-attachments/assets/fad9161b-d309-45c7-9c2d-a8fa22910b62)


| Created     |    Version   | Author | Comment | Reviewer | Date |
|:------------------:|:-------------:|:-------------:|:-------------:|:------------------:|:--------:|
| 17-01-2025   | V1   | Mohit Saini | L0 | | |

## **Table of Contents**

- [**Introduction**](#introduction)
- [**What is Alert Manager**](#what-is-alert-manager)
- [**Why Alertmanager?**](#why-alertmanager)
- [**Types of Alertmanager**](#related-resources-of-grafana-alert-manager-types)
- [**Grafana Alert Workflow**](#grafana-alert-workflow)
- [**Key Features**](#key-features)
- [**Monitoring Parameters for App Performance and Alerts**](#monitoring-parameters-for-app-performance-and-alerts)
- [**Steps to Create an Alert Rule in Grafana**](#steps-to-create-an-alert-rule-in-grafana)
- [**Conclusion**](#conclusion)
- [**Contacts**](#contacts)
- [**References**](#references)


What is Unit testing in Terraform
Testing is the process of checking the functionality of the application whether it fulfills the requirement or not. Unit tests in Terraform are used to validate the behavior of individual resources or modules, ensuring that they function as expected when given specific input, thereby contributing to the robustness and reliability of the infrastructure as code.

Why
| **Benefit**              | **Description**                                                                                                 |
|--------------------------|-----------------------------------------------------------------------------------------------------------------|
| **Early Bug Detection**   | Unit tests identify and isolate issues early in the development cycle. This prevents costly and time-consuming debugging later in the process, especially when dealing with complex infrastructure. |
| **Improved Code Quality** | Encourages writing more modular, maintainable, and testable Terraform code. Promotes better design practices and reduces the risk of introducing regressions with code changes. |
| **Increased Confidence**  | Provides confidence that your infrastructure code is reliable and predictable. Reduces the fear of unintended consequences when making changes to your infrastructure. |
| **Faster Development**    | Streamlines the debugging process by quickly identifying and isolating the root cause of issues. Enables faster development iterations with reduced risk. |
| **Reduced Risk**          | Minimizes the risk of downtime and service disruptions caused by infrastructure failures. Helps prevent costly errors in production environments. |
| **Improved Collaboration**| Provides a shared understanding of the expected behavior of Terraform modules among team members. Facilitates better communication and collaboration within development teams. |



# Tools for Parameter checklist 

| **Parameter**                     | **Checkov** | **tfsec** | **Terratest** | **OPA/Conftest** | **Infracost** | **GitLeaks** | **Sentinel** | **Terrascan** | **tflint** | **Kitchen-Terraform** |
|------------------------------------|-------------|-----------|---------------|------------------|---------------|--------------|--------------|----------------|------------|----------------------|
| **Hard-coded credentials**         | ✔️          | ✔️        | ❌            | ✔️               | ❌            | ✔️           | ✔️           | ✔️             | ✔️         | ✔️                   |
| **Encryption for sensitive data**  | ✔️          | ✔️        | ❌            | ✔️               | ❌            | ❌           | ✔️           | ✔️             | ✔️         | ✔️                   |
| **Overly permissive IAM policies** | ✔️          | ✔️        | ❌            | ✔️               | ❌            | ❌           | ✔️           | ✔️             | ✔️         | ✔️                   |
| **Open ports and unrestricted CIDR** | ✔️         | ✔️        | ❌            | ✔️               | ❌            | ❌           | ✔️           | ✔️             | ✔️         | ✔️                   |
| **Tagging enforcement**            | ✔️          | ❌        | ❌            | ✔️               | ❌            | ❌           | ✔️           | ❌             | ❌         | ✔️                   |
| **Naming conventions**             | ✔️          | ❌        | ❌            | ✔️               | ❌            | ❌           | ✔️           | ❌             | ❌         | ✔️                   |
| **Approved AMIs and instance types** | ✔️         | ✔️        | ❌            | ✔️               | ❌            | ❌           | ✔️           | ✔️             | ✔️         | ✔️                   |
| **Subnet CIDR blocks**             | ✔️          | ✔️        | ❌            | ✔️               | ❌            | ❌           | ✔️           | ✔️             | ✔️         | ✔️                   |
| **Route table configurations**     | ✔️          | ✔️        | ❌            | ✔️               | ❌            | ❌           | ✔️           | ✔️             | ✔️         | ✔️                   |
| **Load balancer health checks**    | ❌          | ❌        | ✔️            | ❌               | ❌            | ❌           | ❌           | ❌             | ❌         | ✔️                   |
| **DNS records correctness**        | ❌          | ❌        | ✔️            | ❌               | ❌            | ❌           | ❌           | ❌             | ❌         | ✔️                   |
| **Resource creation correctness**  | ❌          | ❌        | ✔️            | ❌               | ❌            | ❌           | ❌           | ❌             | ❌         | ✔️                   |
| **Scaling policies**               | ❌          | ❌        | ✔️            | ❌               | ❌            | ❌           | ❌           | ❌             | ❌         | ✔️                   |
| **Cost estimation**                | ❌          | ❌        | ❌            | ❌               | ✔️            | ❌           | ❌           | ❌             | ❌         | ❌                   |
| **Secrets accidentally committed** | ❌          | ❌        | ❌            | ❌               | ❌            | ✔️           | ❌           | ❌             | ❌         | ❌                   |
| **Failed apply simulation**        | ❌          | ❌        | ✔️            | ❌               | ❌            | ❌           | ❌           | ❌             | ❌         | ✔️                   |
| **State file locking mechanism**   | ❌          | ❌        | ✔️            | ❌               | ❌            | ❌           | ❌           | ❌             | ❌         | ✔️                   |
| **Expensive instance types**       | ❌          | ❌        | ❌            | ❌               | ✔️            | ❌           | ❌           | ❌             | ❌         | ❌                   |
| **Unused resources**               | ✔️          | ✔️        | ❌            | ✔️               | ❌            | ❌           | ✔️           | ✔️             | ✔️         | ✔️                   |
| **Backup configuration**           | ✔️          | ✔️        | ❌            | ✔️               | ❌            | ❌           | ✔️           | ✔️             | ✔️         | ✔️                   |

