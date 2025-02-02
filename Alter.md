# Documentation of Alerting Rules and Process for Infra Monitoring Using Alert Manager
![image](https://github.com/user-attachments/assets/835d169f-dd69-4bd0-9613-4c4d851959fe)

| Created | Version | Author        | Comment | Reviewer     |
|---------|---------|---------------|---------|--------------|
| 14-01-2025 | V1 | Anjali Dhiman |         | Khushi Malhotra |

## **Table of Contents**
1. [Introduction](#introduction)
2. [What is Alert Manager](#what-is-alert-manager)
3. [Why Alert Manager](#why-alert-manager)
4. [Alert Manager Types](#alert-manager-types)
5. [Grafana Alertmanager](#grafana-alertmanager)
6. [Alerting Rules and Process for Infra Monitoring](#alerting-rules-and-process-for-infra-monitoring)
7. [Alert Rules](#alert-rules)
8. [Types of Alert Rules](#types-of-alert-rules)
9. [Steps for Creating Alert Rule](#steps-for-creating-alert-rule)
10. [Alertmanager Working](#alertmanager-working)
11. [Monitoring Using Alert Manager](#monitoring-using-alert-manager)
12. [Notification Policies](#notification-policies)
13. [Send Notification](#send-notification)
14. [Conclusion](#conclusion)
15. [Contacts](#contacts)
16. [References](#references)


## Introduction 
The document covers the structure of alerting rules, how to configure and manage them within Alert Manager, and the best practices for setting up alert thresholds to ensure timely and accurate notifications. 

## What is Alert Manager?
An alert is a notification that an issue has been detected, and an alert manager is a tool that manages those alerts. Alert managers collect, group, and send alerts to the right people or systems.

## Why alert manager?

| **Benefit**                         | **Description**                                                                 |
|-------------------------------------|---------------------------------------------------------------------------------|
| **Detect Issues Early**             | Helps identify anomalies or changes in your system before they become serious problems. |
| **Reduce Manual Monitoring**        | Eliminates the need for manual monitoring by automatically sending alerts when issues are detected. |
| **Improve System Reliability**      | Improves system reliability by providing timely insights into issues. |
| **Create Alerts from Multiple Data Sources** | Allows creating alerts based on data from different monitoring systems. |

## **Alert Manager Types**

| **Alertmanager Type**         | **Description**                                                                 |
|------------------------------|---------------------------------------------------------------------------------|
| **Grafana Alertmanager**      | An open-source tool integrated with Grafana for managing and sending alerts based on defined rules. |
| **Prometheus Alertmanager**   | A tool to handle alerts generated by Prometheus. It manages the alerts, routes them to the right receivers, and silences them as necessary. |
| **Thanos Alertmanager**       | A highly scalable alert manager that works with **Prometheus** to provide long-term storage and high availability for alerts. |
| **Mimir Alertmanager**        | A distributed alert manager that handles alerts for large-scale monitoring systems, often integrated with **Mimir** for time-series data storage. |
| **Loki Alertmanager**         | A system integrated with **Loki** for handling log-based alerts, specifically designed for monitoring logs in large distributed systems. |

# Grafana Alertmanager
Grafana Alertmanager is a component of the Grafana ecosystem that helps you manage alerts, ensuring that critical issues are identified and addressed in real-time. It is commonly used alongside Grafana for visualizing metrics, logs, and other data sources

# Alerting Rules and Process for Infra Monitoring
Grafana Alertmanager is an essential tool for managing and alerting on infrastructure monitoring. It allows you to define and manage alert rules based on data gathered from different sources.


## Alert Rules
Alert rules are used to specify when an alert should be triggered. For example, if we want to be alerted when the memory usage of our Java service exceeds 90%, but not during garbage collection, we can set an alert rule. This rule would trigger only if the memory usage stays above 90% for a certain period, ensuring it isn't triggered just before garbage collection.

## Types of Alert Rules

![image](https://github.com/user-attachments/assets/b7041c89-ee67-4503-b100-f50811b709a7)

## Grafana-managed rules
Grafana-managed alert rules are a powerful feature of Grafana that allow you to define, manage, and organize alerting directly within the Grafana interface, without having to rely on external tools or systems for alert management. These alert rules enable users to automate the process of monitoring the health and performance of their infrastructure, applications, and services by sending notifications based on specific conditions or thresholds.

![image](https://github.com/user-attachments/assets/26a48997-0b1d-4b79-afc4-b70b62dd9d9c)

---
## Data source-managed alert rules
Data source-managed alert rules are alerts that are defined and evaluated within the context of a specific data source. Instead of relying solely on Grafana’s internal alerting engine, the alerting is handled by the data source itself, making it more tightly coupled with the data from that particular source. These rules allow Grafana to leverage the native alerting features and mechanisms provided by the data source (for example, Prometheus Alertmanager or InfluxDB’s query-based triggers) while still providing Grafana users the convenience of creating and managing the alerts within the Grafana interface.

![image](https://github.com/user-attachments/assets/1ca26f5d-9dfb-42d9-afbe-60b6726f516b)


## Steps for creating Alert rule.

| Link         | Description                                                    |
|--------------|---------------------------------------------------------------|
| [Garafana](https://github.com/MyGurukulam-p11/Documentation/blob/main/Design%20Monitoring/Design%20App%20Monitoring/Documentation%20/Alerting%20rules%20and%20process%20for%20App%20monitoring.md#steps-to-create-an-alert-rule-in-grafana) | Link to Grafana Alert rule |


## Alertmanager Working

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
Grafana Alertmanager for infrastructure monitoring helps detect issues early, reduce manual monitoring, and enhance the reliability of your systems. By defining clear alert rules, grouping and deduplicating alerts, and properly routing notifications, you can ensure timely responses to critical system issues.

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
| Garfana    | [Link](https://medium.com/@MetricFire/what-is-grafana-8de44d241765)          |
| Garfana alert manager   | [Link](https://grafana.com/docs/grafana/latest/alerting/fundamentals/alert-rules/#:~:text=Grafana%2Dmanaged%20alert%20rules,-Grafana%2Dmanaged%20alert&text=They%20allow%20you%20to%20create,in%20a%20single%20alert%20rule.&text=Alert%20rules%20are%20created%20and,or%20more%20supported%20data%20sources.) | 
