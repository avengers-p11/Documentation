# Documentation of Deployment Strategies | Rolling Deployment Strategy
![image](https://github.com/user-attachments/assets/91b64144-f1cc-4e36-a15e-7eaa91ef3124)


| Created | Version | Author        | Comment | Reviewer     |
|---------|---------|---------------|---------|--------------|
| 14-01-2025 | V1 | Anjali Dhiman |         | Khushi Malhotra |

## **Table of Contents**
1. [Introduction](#introduction)
2. [What are Deployment Strategies?](#what-are-deployment-strategies)
3. [Types of Deployment Strategies](#types-of-deployment-strategies)
4. [Rolling Deployment Strategy](#rolling-deployment-strategy)
5. [Why Rolling Deployments Strategy?](#why-rolling-deployments-strategy?)
6. [Working Process](#working-process)
7. [Pros of Rolling Deployments](#pros-of-rolling-deployments)
8. [Cons of Rolling Deployments](#cons-of-rolling-deployments)
9. [Best Practices](#best-practices)
10. [Contacts](#contacts)
11. [References](#references)


## Introduction
This document provides a detailed explanation of the rolling deployment strategy.

## What are Deployment Strategies?
Deployment strategies are techniques used to roll out changes to an application or system while minimizing downtime and risk.

## Types of Deployment Strategies
- Recreate Deployment
- Rolling Deployment
- Blue-Green Deployment
- Canary Deployment

![Screenshot 2025-01-12 171801](https://github.com/user-attachments/assets/02216102-28ee-4be8-9975-20b8c12b179b)


## Rolling Deployment Strategy
A rolling deployment is a strategy where the previous version of an application is gradually replaced with a new version, updating infrastructure and services incrementally.

![image](https://github.com/user-attachments/assets/c19d0a43-30c1-46b4-b1d2-cb278e6f1f14)

## Why Rolling Deployments Strategy

| **Reasons**                      | **Description**                                                                                                                                                    |
|-----------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Zero Downtime**                 | Users can continue to access the application without interruptions, ensuring no service disruption during the update process.                                       |
| **Safer Updates**                 | Problems with the new version can be quickly identified, and the rollout can be paused or reversed if necessary, minimizing risk.                                   |
| **Smoother on Resources**         | Rolling deployments avoid the need to duplicate the entire production environment, reducing the overall resource load during deployment.                           |
| **Incremental Rollout**           | Updating a small subset of instances at a time allows for a controlled and gradual introduction of the new version, making it easier to identify and resolve issues. |
| **Easy Monitoring and Troubleshooting** | The incremental nature simplifies monitoring and troubleshooting, allowing for early detection of issues and quick corrective actions.                          |

## Rolling Deployment Process

| **Step**               | **Description**                                                                                                                                                    |
|------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Preparation**         | The new version of the application is prepared and validated in a staging environment to ensure it is ready for production.                                         |
| **Incremental Update**  | The deployment starts by updating a small subset of instances, usually one or a few at a time. These instances are removed from the load balancer pool during the update. |
| **Health Checks**       | After updating the subset, health checks are performed to ensure the instances are functioning correctly, including monitoring metrics or running automated tests.    |
| **Update Load Balancer**| Once the updated instances pass health checks, they’re added back to the load balancer pool, making them available for traffic.                                      |
| **Repeat**              | The process repeats for the next subset of instances until the new version is running on all instances.                                                           |

## Pros of Rolling Deployments

| **Pros**                        | **Description**                                                                                                                                                               |
|----------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Reduced Downtime**             | Rolling deployments ensure that at least some instances of the application are always running, minimizing downtime and maintaining availability for users.                     |
| **Incremental Rollout**         | By updating a few instances at a time, rolling deployments allow for a gradual introduction of the new version, making it easier to identify and resolve issues.                |
| **Easy Monitoring**             | The incremental nature simplifies monitoring and troubleshooting, enabling early detection of problems and taking corrective actions before impacting more instances.            |
| **Continuous Deployment**       | Supports continuous deployment practices, allowing for frequent, smaller updates in line with agile methodologies and DevOps principles.                                       |
| **Resource Optimization**       | Makes efficient use of existing infrastructure, avoiding the need to duplicate environments as in blue/green deployments.                                                      |

## Cons of Rolling Deployments

| **Cons**                         | **Description**                                                                                                                                                               |
|----------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Complex Rollback**            | Rolling back changes can be more complex, requiring updates to be reverted on individual instances, potentially leading to inconsistencies if not managed carefully.             |
| **Longer Deployment Time**      | Since updates happen incrementally, the deployment process may take longer compared to strategies like blue/green deployments, which switch versions instantly.                 |
| **Potential for Inconsistent States** | Different instances may run different versions of the application, causing inconsistent behavior, especially with significant version changes.                              |
| **Load Balancer Configuration** | Constant updates to load balancer configurations can create complexity and potential points of failure, particularly in large-scale environments.                              |
| **Higher Operational Overhead** | Requires constant monitoring, health checks, and incremental updates, increasing the operational burden on the deployment team and necessitating robust automation tools.         |

## Best Practices
| **Best Practice**                                              | **Description**                                                                                           |
|---------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------|
| **Use automation tools**                                      | Automate deployment processes to monitor and manage deployments, reducing human error.                    |
| **Implement rollback mechanisms**                             | Set up robust rollback mechanisms to address issues quickly and efficiently in case of deployment failures.|
| **Integrate CI/CD**                                           | Use Continuous Integration and Continuous Delivery (CI/CD) to streamline and automate rolling deployments. |
| **Test thoroughly in staging**                                | Perform extensive testing in staging environments to ensure the application functions properly in production.|


## Contacts

| Name| Email Address      |
|-----|--------------------------|
| Anjali Dhiman | anjali.dhiman.snaatak@mygurukulam.co |

| GitHub | URL |
|----------|---------|
|  Anjaliopstree  |  https://github.com/Anjaliopstree  |

## References
- [Rolling Deployment](https://www.geteppo.com/blog/what-are-rolling-deployments)
- [Deployment Strategy](https://medium.com/@navya.cloudops/devops-zero-to-hero-day-20-deployment-strategies-e6712b4801e4)
