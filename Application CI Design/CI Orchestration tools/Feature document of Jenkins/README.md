![image](https://github.com/user-attachments/assets/2c25eb7a-e64c-4949-a83a-67b2508fe521)

# Feature Document of Jenkins

| **Author** | **Created on** | **Version** | **Last edited on** | **L0 Reviewer** |**Reviwer L1** |**Reviwer L2** |
|------------|----------------|-------------------|---------------------|----------|---------------|---------------|
| Anjali Dhiman  | 25-11-24      | V1  | 26-11-24           |  | | |

## Table of Contents
- [Introduction](#introduction)
- [why Jenkins](#why-jenkins)
- [Pre-requisites](#pre-requisites)
- [System Requirements](#system-requirements)
- [Dependencies and Important Ports](#dependencies-and-important-ports)
- [Features of Jenkins](#features-of-jenkins)
- [Advanced Features](#advanced-features)
- [Core Components](#core-components)
- [Conclusion](#conclusion)
- [Contact Information](#contact-information)
- [References](#references)

## Introduction
Continuous Integration (CI) orchestration tools are essential for modern software development. Jenkins is one of the most popular CI orchestration tools. It helps teams automate building, testing, and deploying code. This document provides an overview of Jenkins, including its key features, setup, and configuration.

---
## why Jenkins
We chose GitHub for our OT microservices project because it’s simple, reliable, and packed with useful features. It acts as a central place to store all our code, making it easy for the team to collaborate. With GitHub, we can track every change, work on different features using branches, and merge everything smoothly without messing up the main code. GitHub’s issue tracking helps us manage tasks and bugs, while its security features ensure our code stays safe. This is why it’s the best choice for our project.

---
## Pre-requisites
Before setting up Jenkins, ensure your hardware, software, and security requirements are met.

## System Requirements
| Hardware Specifications | Minimum Recommendation |
|-------------------------|------------------------|
| Processor               | Dual-core              |
| RAM                     | 4GB                    |
| Disk                    | 20GB                   |
| OS                      | Ubuntu 22.04           |

## Dependencies and Important Ports
| Dependency/Port | Version | Description           |
|-----------------|---------|-----------------------|
| Java            | 11      | Needed to run Jenkins |
| Port 8080       | N/A     | Jenkins web interface |


![image](https://github.com/user-attachments/assets/0dea6b5f-3b24-47eb-b0be-d64902221f88)
### This image represents the Jenkins CI/CD pipeline. Developers commit code to a Git repository, triggering Jenkins to run automated tasks like build, test, stage, and deploy. Jenkins orchestrates these steps in a continuous integration and delivery process, ensuring the code is properly tested and deployed to production. 
## Features of Jenkins

| **Feature**                | **Description**                                                                                           |
|----------------------------|-----------------------------------------------------------------------------------------------------------|
| **Continuous Integration (CI)** | Automates the process of building, testing, and integrating code changes into a shared repository. Ensures software is always in a deployable state. |
| **Pipeline as Code**        | Allows the creation of complex CI/CD pipelines using declarative or scripted syntax, which can be versioned in source control. |
| **Plugins**                 | Jenkins has a vast ecosystem of plugins (over 1,500), supporting integration with various tools and technologies like Docker, Git, AWS, and Maven. |
| **Distributed Builds**      | Supports running builds on multiple machines (Jenkins agents) for scalability, speeding up CI/CD processes. |
| **Automated Testing**       | Enables automated execution of tests (unit, integration, etc.) ensuring code changes don’t break functionality. Integrates with frameworks like JUnit, Selenium, TestNG. |
| **Freestyle Projects**      | Simple jobs for straightforward CI/CD tasks without the need for complex scripting. Ideal for smaller projects. |
| **Declarative Pipelines**   | Provides an easy-to-read, structured way to define CI/CD pipelines, making it accessible for users without advanced scripting knowledge. |
| **Version Control Integration** | Integrates with various version control systems like Git, SVN, and Mercurial. Supports webhooks to trigger jobs automatically on code changes. |
| **Monitoring and Reporting** | Provides real-time feedback on build and deployment statuses with detailed logs, test results, and build history accessible via the web interface. |
| **Security**                | Supports role-based access control (RBAC) to manage user permissions. Integrates with LDAP and Active Directory for user authentication. |
| **Integration with Other Tools** | Seamlessly integrates with tools like Docker, Kubernetes, AWS, and Azure for scalable deployments and containerized builds. |
| **Extensible API**          | Exposes a REST API to manage Jenkins jobs programmatically and integrate with other systems. |
| **Pipeline Visualization**  | Provides graphical visualizations of pipelines to track task flows in real-time and identify issues quickly. |
| **Build Triggers**          | Trigger builds based on events like code commits, pull requests, scheduled times, or manually via the UI. |
| **Build and Artifact Management** | Stores built artifacts (JARs, WARs, Docker images) and integrates with artifact repositories like Nexus or Artifactory for versioning and sharing. |

These features make Jenkins an essential tool for automating the software development lifecycle, particularly in CI/CD workflows.



## Core Components

| Component           | Description                                                                                 |
|---------------------|---------------------------------------------------------------------------------------------|
| **Jenkins Master**  | The central server that manages the overall Jenkins environment, scheduling jobs, and collecting results. It runs the web interface and orchestrates the CI/CD process. |
| **Jenkins Agent**   | Machines that perform the actual build tasks assigned by the Jenkins Master. They can run on various platforms and can be added or removed dynamically based on load. |
| **Jobs and Builds** | - **Job**: A defined task, such as building a project or running tests. <br>- **Build**: An execution instance of a job, with logs and results. |
| **Pipelines**       | - **Declarative Pipeline**: Easy-to-read syntax for defining CI/CD workflows. <br>- **Scripted Pipeline**: Flexible, Groovy-based syntax for more complex workflows. <br>- **Jenkinsfile**: A file in the source control repository that defines the pipeline. |
| **Credentials**     | Securely store and manage passwords, tokens, and other sensitive data used in jobs and pipelines. |
| **Views & Dashboards** | Create custom views to organize and monitor jobs. Real-time dashboards display job statuses and metrics. |
| **SCM Integration** | Integrate with source code management tools like Git, SVN, and Mercurial. Supports triggering jobs based on code changes. |
| **Notifications & Reporting** | - **Notifications**: Send alerts via email, Slack, and other channels upon job completion or failure. <br>- **Reports**: Generate and view reports on test results, code coverage, and more. |


## Conclusion
Jenkins stands out as a robust CI/CD orchestration tool due to its extensive plugin ecosystem, scalability through distributed builds, strong community support, and powerful Pipeline as Code capabilities. Despite its learning curve, Jenkins excels in automating complex software development workflows, making it a top choice for enhancing productivity and streamlining deployment processes effectively.



## Contacts

| Name| Email Address      |
|-----|--------------------------|
| Anjali Dhiman | anjali.dhiman.snaatak@mygurukulam.co |

| GitHub | URL |
|----------|---------|
|  Anjaliopstree  |  https://github.com/Anjaliopstree  |

## References
| Reference Source          | Description                                      | URL                                          |
|---------------------------|--------------------------------------------------|----------------------------------------------|
| Jenkins Official Website  | Comprehensive information about Jenkins.         | [Jenkins.io](https://jenkins.io)             |
| Jenkins Documentation     | Detailed guides and tutorials for using Jenkins. | [Jenkins Documentation](https://jenkins.io/doc/) |
