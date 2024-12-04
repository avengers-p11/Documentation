# Feature Document of Jenkins
### Description of this documentation
This documentation provides an overview of Jenkins, a powerful CI/CD orchestration tool. It covers the prerequisites and system requirements for setting up Jenkins, including necessary hardware, software, and dependencies like Java 17. Key features such as Continuous Integration, Pipeline as Code, plugin support, security, and monitoring are detailed, along with an explanation of its core components like the master, agents, jobs, and pipelines. The document highlights why Jenkins is essential for automating software development workflows and concludes with references and contact information for further assistance.

![image](https://github.com/user-attachments/assets/2c25eb7a-e64c-4949-a83a-67b2508fe521)

| **Author** | **Created on** | **Version** | **Last edited on** | **L0 Reviewer** |**Reviwer L1** |**Reviwer L2** |
|------------|----------------|-------------------|---------------------|----------|---------------|---------------|
| Anjali Dhiman  | 25-11-24      | V1  | 28-11-24           | Khushi malhotra  | | |

## Table of Contents
- [Introduction](#introduction)
- [Pre-requisites](#pre-requisites)
- [Challenges Before and After Jenkins](#challenges-before-and-after-jenkins)
- [System Requirements](#system-requirements)
- [Dependencies and Important Ports](#dependencies-and-important-ports)
- [Features of Jenkins](#features-of-jenkins)
- [Core Components](#core-components)
- [Conclusion](#conclusion)
- [Contacts](#contacts)
- [References](#references)

## Introduction
Continuous Integration (CI) orchestration tools play a critical role in modern software development by streamlining the processes of building, testing, and deploying code. Among the most widely used CI tools is Jenkins, an open-source platform that empowers teams to automate and manage their development pipelines efficiently. This document explores Jenkins, highlighting its key features, setup process, and configuration to help teams optimize their CI/CD workflows.

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
| Java            | 17     | Needed to run Jenkins |
| Port 8080       | N/A     | Jenkins web interface |

---

# Challenges Before and After Jenkins

| **Challenges Before Jenkins**                          | **How Jenkins Resolves Them**                                           |
|--------------------------------------------------------|-------------------------------------------------------------------------|
| **Manual code integration** leading to frequent errors.    | **Automates code integration** with CI pipelines.                          |
| **Delayed feedback** on build and test results.            | Provides **real-time feedback** on builds and tests.                       |
| **Time-consuming deployments** with manual processes.      | **Automates deployment** with CD pipelines.                                |
| **Lack of standardization** in build and release processes.| **Ensures consistency** with defined pipelines and scripts.                |
| Difficulty in **integrating with multiple tools**.         | **Offers a large plugin** ecosystem for seamless tool integrations.        |
| **Scalability issues** for distributed builds.             | Supports **master-agent architecture** for distributed builds.             |
| **Lack of visibility** into build and deployment status.   | **Provides dashboards and logs** for monitoring and troubleshooting.       |

---

![image](https://github.com/user-attachments/assets/0dea6b5f-3b24-47eb-b0be-d64902221f88)
**This image represents the Jenkins CI/CD pipeline. Developers commit code to a Git repository, triggering Jenkins to run automated tasks like build, test, stage, and deploy. Jenkins orchestrates these steps in a continuous integration and delivery process, ensuring the code is properly tested and deployed to production.**

## Features of Jenkins

| **Feature**                | **Description**                                                                                           |
|----------------------------|-----------------------------------------------------------------------------------------------------------|
| **Continuous Integration (CI)** | Automates code building, testing, and integration to ensure the software is always deployable. |
| **Pipeline as Code**        | Defines CI/CD pipelines using code, versioned in source control for consistency. |
| **Plugins**                 | Offers over 1,500 plugins to integrate with tools like Docker, Git, and AWS. |
| **Distributed Builds**      | Runs builds on multiple machines for faster and scalable processes. |
| **Automated Testing**       | Executes tests automatically to ensure code changes don’t break functionality. |
| **Freestyle Projects**      | Simple jobs for straightforward CI/CD tasks without complex scripting. |
| **Declarative Pipelines**   | Structured, easy-to-read pipelines for users with minimal scripting knowledge. |
| **Version Control Integration** | Integrates with systems like Git and SVN, triggering jobs on code changes. |
| **Monitoring and Reporting** | Provides real-time feedback, logs, and build history via a web interface. |
| **Security**                | Supports role-based access and integrates with LDAP/Active Directory for authentication. |
| **Integration with Other Tools** | Works with Docker, Kubernetes, AWS, and more for scalable deployments. |
| **Pipeline Visualization**  | Displays graphical views of pipelines for tracking and troubleshooting. |
| **Build Triggers**          | Automates builds on events like commits, pull requests, or schedules. |
| **Build and Artifact Management** | Manages built artifacts and integrates with repositories like Nexus or Artifactory. |

---

## Core Components

| **Component**           | **Description**                                                                                 |
|--------------------------|-------------------------------------------------------------------------------------------------|
| **Jenkins Master**       | Central server managing jobs, scheduling tasks, and running the web interface for CI/CD.       |
| **Jenkins Agent**        | Machines performing build tasks assigned by the master, scalable based on workload.            |
| **Jobs and Builds**      | - **Job**: Defined task like building or testing. <br> - **Build**: A job's execution instance. |
| **Pipelines**            | - **Declarative**: Simple, structured pipeline syntax. <br> - **Scripted**: Flexible, Groovy-based syntax. <br> - **Jenkinsfile**: Pipeline definition stored in source control. |
| **Credentials**          | Secure storage for passwords, tokens, and sensitive data used in jobs.                        |
| **Views & Dashboards**   | Custom views to organize jobs and dashboards to monitor job statuses and metrics.              |
| **SCM Integration**      | Integrates with Git, SVN, etc., to trigger jobs on code changes.                               |
| **Notifications & Reporting** | Send alerts via email/Slack and generate reports on test results or code coverage.        |

---
# Advantages and Disadvantages of Jenkins

| **Advantages**                 | **Disadvantages**                              |
|--------------------------------|-----------------------------------------------|
| Open-source and free to use.   | Steep learning curve for beginners.           |
| Large plugin ecosystem.        | High resource usage for complex pipelines.    |
| Cross-platform compatibility.  | Requires frequent updates and maintenance.    |
| Customizable pipelines.        | Outdated user interface.                      |
| Scalable with distributed builds. | Security risks with third-party plugins.      |

---

## Conclusion
GitHub is the preferred platform for our OT Microservices project because it is simple, reliable, and feature-rich. It provides a central repository for collaboration, enabling version control, branch management, and smooth code merging. Its built-in tools, such as issue tracking and GitHub Actions for CI/CD, streamline workflows while ensuring security and task management. Our team's expertise in GitHub and its seamless integration with our existing tools effectively meets our project needs without the complexities or migration challenges associated with alternatives like GitLab.

---

## Contacts

| Name| Email Address      |
|-----|--------------------------|
| Anjali Dhiman | anjali.dhiman.snaatak@mygurukulam.co |

| GitHub | URL |
|----------|---------|
|  Anjaliopstree  |  https://github.com/Anjaliopstree  |

---
## References
| Reference Source          | Description                                      | URL                                          |
|---------------------------|--------------------------------------------------|----------------------------------------------|
| Jenkins Official Website  | Comprehensive information about Jenkins.         | [Jenkins.io](https://jenkins.io)             |
| Jenkins Documentation     | Detailed guides and tutorials for using Jenkins. | [Jenkins Documentation](https://jenkins.io/doc/) |
