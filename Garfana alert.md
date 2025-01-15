# Documentation on Alerting rules and process for App monitoring using Alert Manager


| Created     |    Version   | Author | Comment | Reviewer | Date |
|:------------------:|:-------------:|:-------------:|:-------------:|:------------------:|:--------:|
| 15-01-2025   | V1   | Mohit Saini | L0 | | |

## **Table of Contents**

- [**Introduction**](#introduction)
- [**What is Alert Manager**](#what-is-alert-manager)
- [**Why Alertmanager?**](#why-alertmanager)
- [**Types of Alertmanager**](#types-of-alertmanager)
- [**Grafana Alert Workflow**](#grafana-alert-workflow)
- [**Key Features**](#key-features)
- [**Monitoring Parameters for App Performance and Alerts**](#monitoring-parameters-for-app-performance-and-alerts)
- [**Grafana-managed Alert Rule Steps**](#grafana-managed-alert-rule-steps)
- [[**Steps to Create an Alert Rule in Grafana**](#steps-to-create-an-alert-rule-in-grafana)
- [**Conclusion**](#conclusion)
- [**Contacts**](#contacts)
- [**References**](#references)

## Introduction
The document covers the structure of alerting rules, how to configure and manage them within Alert Manager, and the best practices for setting up alert thresholds to ensure timely and accurate notifications.

## What is Alert Manager?
An alert is a notification that an issue has been detected, and an alert manager is a tool that manages those alerts. Alert managers collect, group, and send alerts to the right people or systems.  
Grafana alerting lets you set up alerts to watch your data and notify you when something important happens.
- You can create rules to check your metrics, query results, or data sources.  
- If a condition or limit you set is reached, Grafana sends you a notification.  
- It helps you stay informed and act quickly.

## Why Alertmanager?

| **Feature**                 | **Benefit**                                                                               | **Explanation**                                                                                                                        |
|-----------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------|
| **Reduces alert noise**     | Groups and deduplicates alerts                                                            | Helps teams focus on critical issues by combining similar alerts into a single notification.                                           |
| **Prioritizes alerts**      | Suppresses less critical alerts                                                           | Avoids overwhelming teams by suppressing notifications for lower-priority alerts when higher-priority ones are already firing.         |
| **Routes alerts to receivers** | Flexible notification options                                                           | Sends alerts to multiple destinations, such as email, Slack, PagerDuty, or custom webhooks, based on configuration.                    |
| **Simplifies architecture** | Direct integration with Prometheus                                                        | Eliminates the need for a separate tool to fetch alerts, as Alertmanager directly receives and processes alerts pushed from Prometheus. |
| **Mitigates issues**        | Enables timely actions                                                                    | Provides robust notification management to ensure teams are informed promptly, allowing quicker response to mitigate and resolve issues effectively. |

### Related Resources
**For detailed information of Grafana Alert Manager Types**
| Link         | Description                                                    |
|--------------|---------------------------------------------------------------|
| [Attendance API](https://github.com/avengers-p11/Documentation/blob/main/Alter.md#types-of-alert-rules) | Detailed overview of alert manager types. |

## Grafana Alert Workflow

| **Step**                | **Description**                                                                                         | **Example**                                     |
|--------------------------|---------------------------------------------------------------------------------------------------------|------------------------------------------------|
| **Define Alert Rules**   | Set conditions or thresholds to monitor metrics or data sources.                                       | Alert if CPU usage goes above 80%.             |
| **Evaluate Data**        | Grafana checks the data at regular intervals and compares it against the defined rules.                | Regularly check CPU usage metrics.             |
| **Trigger Alerts**       | Alerts are triggered when the set condition or threshold is met.                                       | Alert triggers when CPU usage exceeds 80%.     |
| **Send Notifications**   | Notifications are sent to configured channels like email, Slack, PagerDuty, or webhooks.               | Team receives alert notification on Slack.     |
| **Acknowledge and Act**  | The team receives the alert and takes necessary action to resolve the issue.                           | Team investigates and reduces CPU usage.       |
| **Resolve Alerts**       | Alerts are resolved automatically when the condition returns to normal, and resolution notifications are sent. | CPU usage drops below 80%, and alert clears.   |

![image](https://github.com/user-attachments/assets/3eceb6ba-307c-4b52-9931-a4a7e8bee512)

### Key Features

| Feature                        | Description                                                                 |
|---------------------------------|-----------------------------------------------------------------------------|
| **Alert Rules**                 | Users set conditions to trigger an alert based on data limits, comparisons, or sums. |
| **Multiple Alert States**       | Alerts can have different statuses like OK, Pending, or Alerting to track and confirm alerts. |
| **Alert Annotations**           | Grafana adds notes to the dashboard when an alert happens to help understand the cause and fix issues. |
| **Alert Dashboards**            | Users can create special dashboards to monitor the status of alerts and their history. |
| **Alert Notifications History** | Grafana keeps a record of alerts, showing status changes and notifications sent for review. |
| **Silencing and Muting**        | Users can pause alerts for a set time to avoid notifications during maintenance or known issues. |

![image](https://github.com/user-attachments/assets/684b9cf7-43ae-46e2-a774-791f3276286b)

### Monitoring Parameters for App Performance and Alerts

| **Parameter**                | **Description**                                                              | **Alert Example**                                         |
|------------------------------|------------------------------------------------------------------------------|----------------------------------------------------------|
| **CPU Usage**                 | Measures the percentage of CPU resources used by the application or system.  | Alert if CPU usage exceeds 80% for more than 5 minutes.   |
| **Memory Usage**              | Tracks the amount of memory (RAM) consumed by the application.               | Alert if memory usage exceeds 90%.                        |
| **Disk Usage**                | Measures how much disk space is used by the application or system.           | Alert if disk usage exceeds 85%.                          |
| **Response Time / Latency**   | Measures how long it takes for the application to respond to requests.       | Alert if response time exceeds 2 seconds for 5 minutes.   |
| **Error Rate**                | Tracks the number of failed requests or errors occurring in the application. | Alert if error rate exceeds 5% of total requests.         |
| **Request Rate (Throughput)** | Measures the number of requests handled by the application per second.      | Alert if request rate drops significantly.                |
| **Uptime / Availability**     | Measures the time the application has been up and running without failure.  | Alert if uptime is less than 99.9% over the last 24 hours.|
| **Database Performance**      | Measures performance and errors related to database queries and connections. | Alert if database query time exceeds 1 second.            |
| **Cache Hit/Miss Rate**       | Tracks the effectiveness of the caching mechanism used by the application.  | Alert if cache miss rate exceeds 10%.                     |
| **Network Throughput**        | Measures the amount of data transferred in and out of the application.       | Alert if network throughput drops below a set threshold.  |
| **Queue Length (Message Queue)** | Tracks the number of messages or tasks waiting to be processed.            | Alert if the queue length exceeds a threshold.            |
| **Garbage Collection Time**   | Measures the time spent on garbage collection (reclaiming unused memory).    | Alert if GC time exceeds 5% of total application time.    |
| **Thread Count**              | Tracks the number of active threads being used by the application.          | Alert if thread count exceeds a limit.                    |
| **Service/Endpoint Status**   | Tracks whether critical services or endpoints are running.                   | Alert if any critical service is down.                    |
| **Custom Business Metrics**   | Custom metrics based on business logic, like transactions or registrations. | Alert if failed transactions exceed a set threshold.      |



## Grafana-managed Alert Rule Steps

### **Steps to Create an Alert Rule in Grafana**

#### **Step 1: Go to the dashboard. In the left-side menu, click Alerting.**
![image](https://github.com/user-attachments/assets/36b0a375-48d9-4b7a-9706-0fe35f984177)

#### **Step 2: Now click on Alert Rules.**
![image](https://github.com/user-attachments/assets/87f69486-14f3-4085-9752-6bea26b78640)

#### **Step 3: Click on Create Alert Rule. The new alert rule page opens, where the Grafana Managed Alerts option is selected by default.**
![image](https://github.com/user-attachments/assets/7b4d6074-928f-45e3-b36a-fc1213819b12)

#### **Step 4: Add a Rule Name.**
![image](https://github.com/user-attachments/assets/b5340e36-4129-4801-b5c8-c866b7737b78)

#### **Step 5: In the Rule Name field, add a descriptive name for your rule.**
![image](https://github.com/user-attachments/assets/6dfbc8c7-94ba-4c8b-b021-23b27b760ff0)

#### **Step 6: Select the Mimir or Loki Recording Rule option and choose your Loki or Prometheus data source.**
![image](https://github.com/user-attachments/assets/cb401845-2cb1-46f2-afcd-1158597f3da7)

#### **Step 7: Add the Alert Evaluation Behavior and set a valid For Duration. This defines how long the condition must be true for the alert to be triggered.**
![image](https://github.com/user-attachments/assets/0d94db8b-b781-42e0-800d-c231cc234374)

#### **Step 8: Save the rule by clicking Save.**
![image](https://github.com/user-attachments/assets/0961159d-f9d0-470a-8e44-157229b4b2e7)
![image](https://github.com/user-attachments/assets/d77b8923-57d0-4a1b-b1c1-91f0232bbd3a)

#### **Preview: Check the preview to ensure the rule is set up correctly.**
![image](https://github.com/user-attachments/assets/9ba5ef21-7070-4c14-8a00-a73c90eacca5)

#### **Step 9: Click Save to save the rule, or click Save and Exit to save the rule and return to the Alerting page.**
![image](https://github.com/user-attachments/assets/b8fe378e-b156-4947-8abb-1c381aff8107)

## Conclusion
Rolling deployments offer a balanced approach to software updates, providing a gradual transition to the new version while minimizing downtime and maintaining service availability. This strategy is particularly useful for large-scale applications where downtime can have significant consequences.

## Contacts

| Name| Email Address      |
|-----|--------------------------|
| Mohit Saini | mohit.saini.snaatak@mygurukulam.co |

## References

| **Title**            | **Link**                                                                                  |
|-----------------------|------------------------------------------------------------------------------------------|
| Garfana Alert and Manager    | [Link](https://medium.com/trendyol-tech/alert-and-monitoring-with-grafana-b659c433bb51)          |
| Alert Rules   | [Link](https://grafana.com/docs/grafana/latest/alerting/fundamentals/alert-rules/) | 
