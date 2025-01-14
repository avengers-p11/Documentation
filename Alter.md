# Documentation of on Alerting rules and process for infra monitoring using Alert Manager
![image](https://github.com/user-attachments/assets/01da6964-2de3-4b8b-b814-9f5de55fa5bb)


![image](https://github.com/user-attachments/assets/50d8c2f0-19a1-4cc3-9008-57351e48f7df)


| Created | Version | Author        | Comment | Reviewer     |
|---------|---------|---------------|---------|--------------|
| 14-01-2025 | V1 | Anjali Dhiman |         | Khushi Malhotra |

## **Table of Contents**
1. [Introduction](#introduction)
2. [What is Alert Manager](#what-are-deployment-strategies)
3. [Alertmanager Types](#types-of-deployment-strategies)
4. [Alert Rules](#rolling-deployment-strategy)
5. [Types Alert Rules](#why-rolling-deployments-strategy?)
6. [Working Process](#working-process)
7. [Pros of Rolling Deployments Strategy](#pros-of-rolling-deployments-strategy)
8. [Cons of Rolling Deployments Strategy](#cons-of-rolling-deployments-strategy)
9. [Best Practices](#best-practices)
10. [Conclusion](#Conclusion)
11. [Contacts](#contacts)
12. [References](#references)


Introduction 
The document covers the structure of alerting rules, how to configure and manage them within Alert Manager, and the best practices for setting up alert thresholds to ensure timely and accurate notifications. 

What is Alert Manager
An alert is a notification that an issue has been detected, and an alert manager is a tool that manages those alerts. Alert managers collect, group, and send alerts to the right people or systems.

# **Alertmanager Types **

| **Alertmanager Type**   | **Description**                                                                                                                                                   | **Available In**                         | **Handles Alerts From**                                    |
|-------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------|------------------------------------------------------------|
| **Grafana Alertmanager** | Built-in Alertmanager that extends Prometheus Alertmanager. It handles only **Grafana-managed alerts**.                                                            | Grafana (default setup)                  | Only Grafana-managed alerts.                               |
| **Cloud Alertmanager**   | Preconfigured Alertmanager instance (`grafanacloud-STACK_NAME-ngalertmanager`) running in Grafana Cloud, integrated with Mimir (Prometheus) for cloud environments. | Grafana Cloud                           | Handles both **Grafana-managed** and **data source-managed** alerts. |
| **Other Alertmanagers**  | Supports integration with other external Alertmanagers, like Prometheus Alertmanager, for hybrid environments.                                                    | External integrations (e.g., Prometheus)  | Handles both **Grafana-managed** and **data source-managed** alerts. |

Alert Rules
lert rules are used to specify when an alert should be triggered. For example, if we want to be alerted when the memory usage of our Java service exceeds 90%, but not during garbage collection, we can set an alert rule. This rule would trigger only if the memory usage stays above 90% for a certain period, ensuring it isn't triggered just before garbage collection.

Types of Alert Rules

![image](https://github.com/user-attachments/assets/b7041c89-ee67-4503-b100-f50811b709a7)

**Grafana-managed rules** Grafana-managed rules are flexible and can pull data from multiple sources in one alert. You can use them to process data, set alert conditions, and include images in notifications.
**Data source-managed alert rules** Data source-managed alert rules work only with Prometheus-based sources like Prometheus, Grafana Mimir, or Grafana Loki. They are stored in the data source and can scale to handle high availability.

