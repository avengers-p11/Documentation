# Documentation of Alerting Rules and Process for Infra Monitoring Using Alert Manager
![image](https://github.com/user-attachments/assets/835d169f-dd69-4bd0-9613-4c4d851959fe)

| Created | Version | Author        | Comment | Reviewer     |
|---------|---------|---------------|---------|--------------|
| 14-01-2025 | V1 | Anjali Dhiman |         | Khushi Malhotra |

## **Table of Contents**
1. [Introduction](#introduction)
2. [What is Alert Manager](#what-is-alert-manager)
3. [Alert Manager Types](#alert-manager-types)
4. [Alert Rules](#alert-rules)
5. [Types of Alert Rules](#types-of-alert-rules)
6. [Alert Working](#alert-working)
7. [Monitoring Using Alert Manager](#monitoring-using-alert-manager)
8. [Notification Policies](#notification-policies)
9. [Send Notification](#send-notification)
10. [Conclusion](#conclusion)
11. [Contacts](#contacts)
12. [References](#references)

## Introduction 
The document covers the structure of alerting rules, how to configure and manage them within Alert Manager, and the best practices for setting up alert thresholds to ensure timely and accurate notifications. 

## What is Alert Manager
An alert is a notification that an issue has been detected, and an alert manager is a tool that manages those alerts. Alert managers collect, group, and send alerts to the right people or systems.

## **Alert Manager Types**

| **Alert Manager Type**   | **Description**                                                                                                                                                   | **Available In**                         | **Handles Alerts From**                                    |
|-------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------|------------------------------------------------------------|
| **Grafana Alert Manager** | Built-in Alert Manager that extends Prometheus Alert Manager. It handles only **Grafana-managed alerts**.                                                            | Grafana (default setup)                  | Only Grafana-managed alerts.                               |
| **Cloud Alert Manager**   | Preconfigured Alert Manager instance (`grafanacloud-STACK_NAME-ngalertmanager`) running in Grafana Cloud, integrated with Mimir (Prometheus) for cloud environments. | Grafana Cloud                           | Handles both **Grafana-managed** and **data source-managed** alerts. |
| **Other Alert Managers**  | Supports integration with other external Alert Managers, like Prometheus Alert Manager, for hybrid environments.                                                    | External integrations (e.g., Prometheus)  | Handles both **Grafana-managed** and **data source-managed** alerts. |

## Alert Rules
Alert rules are used to specify when an alert should be triggered. For example, if we want to be alerted when the memory usage of our Java service exceeds 90%, but not during garbage collection, we can set an alert rule. This rule would trigger only if the memory usage stays above 90% for a certain period, ensuring it isn't triggered just before garbage collection.

## Types of Alert Rules

![image](https://github.com/user-attachments/assets/b7041c89-ee67-4503-b100-f50811b709a7)

**Grafana-managed rules** Grafana-managed rules are flexible and can pull data from multiple sources in one alert. You can use them to process data, set alert conditions, and include images in notifications.

![image](https://github.com/user-attachments/assets/26a48997-0b1d-4b79-afc4-b70b62dd9d9c)

-
**Data source-managed alert rules** Data source-managed alert rules work only with Prometheus-based sources like Prometheus, Grafana Mimir, or Grafana Loki. They are stored in the data source and can scale to handle high availability.


## Alert Working

![image](https://github.com/user-attachments/assets/dcaf769a-5c91-4013-91b3-262237e40c25)

## Monitoring Using Alert Manager

Infrastructure monitoring is the continuous tracking of the health, performance, and availability of an organization's IT infrastructure.

![image](https://github.com/user-attachments/assets/c15a6ca4-e164-42f1-8beb-8221ffdde9f2)

Each alert rule can produce multiple alert instances (also known as alerts) - one alert instance for each time series. This is exceptionally powerful as it allows you to observe multiple series in a single expression.

![image](https://github.com/user-attachments/assets/486f5684-3beb-4082-9f6d-9e46a1bbf764)

## Notification Policies

![image](https://github.com/user-attachments/assets/9979233d-b786-4cf7-97f0-67fdad6d371f)

## Send Notification 

![image](https://github.com/user-attachments/assets/2b5e29f1-e091-4065-b3f0-a29d518e1135)

## Conclusion
Rolling deployments offer a balanced approach to software updates, providing a gradual transition to the new version while minimizing downtime and maintaining service availability. This strategy is particularly useful for large-scale applications where downtime can have significant consequences.

## Contacts

| Name| Email Address      |
|-----|--------------------------|
| Anjali Dhiman | anjali.dhiman.snaatak@mygurukulam.co |

| GitHub | URL |
|----------|---------|
|  Anjaliopstree  |  https://github.com/Anjaliopstree  |

## References

| **Title**            | **Link**                                                                                  |
|-----------------------|------------------------------------------------------------------------------------------|
| Rolling Deployment    | [Rolling Deployment](https://www.geteppo.com/blog/what-are-rolling-deployments)          |
| Deployment Strategy   | [Deployment Strategy](https://medium.com/@navya.cloudops/devops-zero-to-hero-day-20-deployment-strategies-e6712b4801e4) | 
