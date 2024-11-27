# Comparison: GitLab, Jenkins, and BuildPiper  
## Description of what we did in this documentation

In this documentation, we compared GitLab, Jenkins, and BuildPiper to help decide which tool is best suited for our OT Microservices project. We discussed the features, advantages, and disadvantages of each tool. The documentation helps us understand which tool fits our needs based on our project requirements and team size.

---

## Table of Contents  
1. [Introduction](#introduction)
2. [Why we need ci/cd in our OT Microservice project](#why-we-need-ci/cd-in-our-ot-microservice-project)
3. [Features Comparison](#features-comparison)  
4. [Advantages](#advantages)  
5. [Disadvantages](#disadvantages)  
6. [Conclusion Table](#conclusion-table)
7. [Contacts](#contacts)
8. [References](#references)

---

## Introduction  
This document compares **GitLab**, **Jenkins**, and **BuildPiper** — three key tools in the DevOps ecosystem. Each offers unique functionalities for CI/CD, deployment, and orchestration, but their suitability depends on specific project needs and team expertise.

---
## Why we need ci/cd in our OT Microservice project

For our OT Microservices, we have three APIs: Employee API, Attendance API, and Salary API. The Employee API is a RESTful service built with Golang and Gin, integrating with ScyllaDB for the database. The Attendance API is developed in Python and uses PostgreSQL for data storage. The Salary API is Java and uses Golang and ScyllaDB for efficient data handling. With CI/CD in place for each API, we automate the workflow from code integration to testing and deployment. This ensures that every code change is automatically tested, validated, and deployed to the appropriate environment, significantly improving the speed, quality, and reliability of our development process.

## Features Comparison  

# DevOps Tool Comparison: GitLab, Jenkins, and BuildPiper  

| **Feature**               | **GitLab**                          | **Jenkins**                      | **BuildPiper**                    |
|---------------------------|--------------------------------------|-----------------------------------|------------------------------------|
| **Version Control**       | ✅ Built-in Git repository          | ❌ Requires external integration | ❌ Requires external integration  |
| **CI/CD**                 | ✅ GitLab CI/CD                     | ✅ Pipeline support via plugins  | ✅ Built-in CI/CD                 |
| **Self-hosted Option**    | ✅ (GitLab CE/EE)                   | ✅ Jenkins server                | ✅ Self-hosted or managed         |
| **Plugins/Extensions**    | ✅ Native integrations              | ✅ 1,500+ plugins                | ❌ Limited integrations           |
| **Container Registry**    | ✅ Built-in                        | ❌ Requires external tools       | ✅ Built-in registry              |
| **Kubernetes Support**    | ✅ Native                          | ✅ Supported via plugins         | ✅ Integrated Kubernetes support  |
| **Ease of Use**           | ✅ User-friendly UI                | ❌ Requires manual configuration | ✅ Simplified workflows           |
| **Security Scanning**     | ✅ Dependency and SAST             | ❌ Requires plugins              | ✅ Integrated security features   |
| **Monitoring**            | ✅ Built-in                        | ❌ Requires external tools       | ✅ Built-in monitoring            |
| **Marketplace/Ecosystem** | ✅ GitLab Integrations             | ✅ Jenkins Plugin Marketplace    | ❌ Limited marketplace options    |
| **Automation**            | ✅ Integrated automation           | ✅ Highly customizable           | ✅ Pre-built automation features  |
| **User Limit**            | ✅ Free tier with 5 users          | ✅ Unlimited                    | ❌ Licensing required             |
| **Unique Selling Point**  | ✅ Complete DevOps platform         | ✅ Highly extensible via plugins | ✅ Streamlined Kubernetes and CI/CD workflows |


---

## Advantages  

### GitLab  
- All-in-one DevOps platform with CI/CD, version control, and security.  
- Simplifies DevOps workflows by combining multiple functionalities.  
- Supports multi-cloud and on-premises deployments.  

### Jenkins  
- Open-source with a vast ecosystem of plugins.  
- Flexible and supports any CI/CD pipeline configuration.  
- Community-driven with frequent updates and new integrations.  

### BuildPiper  
- Optimized for Kubernetes and microservices management.  
- End-to-end containerized application lifecycle support.  
- Simplifies complex Kubernetes workflows.  

---

## Disadvantages  

### GitLab  
- Steep learning curve for beginners.  
- Costly premium features for advanced use cases.  
- Can feel bloated for smaller teams needing only basic CI/CD.  

### Jenkins  
- Requires manual setup and plugin management.  
- Lacks native Kubernetes focus without third-party plugins.  
- The steeper learning curve for advanced configurations.  

### BuildPiper  
- Narrow use case; not ideal for non-Kubernetes projects.  
- Requires Kubernetes expertise and infrastructure.  
- Limited to microservices-focused workflows.  

---

## Conclusion Table  

| **Tool**        | **When to Use**                                                                                    | **When to Avoid**                                                                                   |
|------------------|---------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------|
| **GitLab**       | - For end-to-end DevOps workflows. <br> - Teams needing robust CI/CD, version control, and security.| - For small teams needing only basic CI/CD.<br> - When cost is a concern.                          |
| **Jenkins**      | - For highly customizable CI/CD workflows. <br> - Open-source enthusiasts needing plugin flexibility.| - When simplicity and native Kubernetes support are priorities.                                    |
| **BuildPiper**   | - For Kubernetes-centric and microservices-based applications. <br> - Teams with Kubernetes expertise.| - For projects not involving Kubernetes.<br> - Teams unfamiliar with containerized deployments.   |

Jenkins is a great choice because it offers a lot of customization, can integrate with many tools, and can grow with your needs. Even though it can be tricky to learn at first, there's a big community and many plugins to help you. Jenkins lets you create detailed CI/CD pipelines that fit your specific needs, making it a strong and flexible option for many different types of projects.

---

## Contacts

| Name| Email Address      | GitHub | URL |
|-----|--------------------------|----------|---------|
| Anjali Dhiman | anjali.dhiman.snaatak@mygurukulam.co |  Anjaliopstree  |  https://github.com/Anjaliopstree  |

---

## References

|    Name       |       |          Links And Description                                   |
|-------------|--------|---------------------------------------------|
|BuildPiper | Official | [BuildPiper](https://buildpiper.io/) |  
|           |Documentation | [DOC](https://github.com/avengers-p11/Documentation/blob/main/Application%20CI%20Design/CI%20Orchestration%20tools/Feature%20document%20of%20Buildpiper/README.md)                          |
|GitLab CI | Official | [GitLab](https://about.gitlab.com/stages-devops-lifecycle/continuous-integration/) |
|          | Documaentation | [DOC](https://github.com/avengers-p11/Documentation/blob/main/Application%20CI%20Design/CI%20Orchestration%20tools/Feature%20document%20of%20GitLab/README.md)                               |
|Jenkins | Official | [Jenkins](https://www.jenkins.io/) |
|          | Documentation | [DOC](https://github.com/avengers-p11/Documentation/blob/main/Application%20CI%20Design/CI%20Orchestration%20tools/Feature%20document%20of%20Jenkins/README.md) |
