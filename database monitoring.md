# Documentation on Alerting Rules and Process for Database Monitoring
<img src="https://github.com/user-attachments/assets/1a8b02c8-7ff4-43a5-98fe-a5956fefd6ca" width="300" />

| Created | Version | Author        | Comment | Reviewer     |
|---------|---------|---------------|---------|--------------|
| 14-01-2025 | V1 | Anjali Dhiman |         | Khushi Malhotra |

## **Table of Contents**
1. [Introduction](#introduction)
2. [What is Database Monitoring](#what-is-database-monitoring)
3. [Why Database Monitoring](#why-database-monitoring)
4. [Monitoring Parameters for DB](#monitoring-parameters-for-db)
5. [Alerting Rules](#alerting-rules)
6. [Steps for Creating Alert Rule](#steps-for-creating-alert-rule)
7. [Alert Severity Levels](#alert-severity-levels)
8. [Alerting Process](#alerting-process)
9. [Conclusion](#conclusion)
10. [Contacts](#contacts)
11. [References](#references)

# Introduction
This document outlines the key alerting rules for database monitoring and provides a structured process for configuring and responding to these alerts. By implementing these rules, you can ensure that your database systems remain operational, secure, and performant, minimizing risks and improving system reliability.

## What is Database Monitoring
Database monitoring refers to the tasks associated with checking the operational status of a database to ensure it functions properly. It's critical for maintaining the health and performance of your database management system.

## Why Database Monitoring

| Reason                     | Description                                                                                  |
|----------------------------|----------------------------------------------------------------------------------------------|
| **Performance Optimization** | Helps identify and resolve slow queries, high latency, or bottlenecks that affect database performance. |
| **Availability and Uptime**  | Ensures the database is always accessible, reducing downtime and improving reliability.     |
| **Resource Management**      | Tracks CPU, memory, storage, and I/O usage to optimize resource allocation and reduce costs. |
| **Error Detection and Prevention** | Identifies issues like failed connections, deadlocks, or transaction conflicts before they escalate. |
| **Scalability**              | Provides insights to scale resources as the workload grows.                  |
| **Security**                 | Monitors for unauthorized access, abnormal activity, or potential breaches.                   |
| **Compliance**               | Ensures databases meet regulatory requirements by maintaining logs and monitoring access. |
| **User Experience**          | Improves overall application performance, leading to better user experience.         |

## Monitoring Parameters for DB
 ![image](https://github.com/user-attachments/assets/e0f27331-01de-417f-847d-9ac372eb6bc1)


| Category                      | Metrics                                             | Alerting Thresholds                                                                 |
|-------------------------------|-----------------------------------------------------|-------------------------------------------------------------------------------------|
| **Query Performance**         |  Query execution time                              |  Query execution time exceeds 2 seconds                                           |
|                               |  Query queue length                                |  Query failure rate exceeds 5% over 10 minutes                                    |
|                               |  Query errors                                      |                                                                                     |
| **Database Connections**      |  Number of active connections                      |  Active connections exceed 90% of the maximum allowed                             |
|                               |  Connection pool usage                             |  Connection pool usage exceeds 85%                                                |
| **Replication Lag**           |  Replication delay in seconds                     |  Replication lag exceeds 100ms for primary-secondary setups                       |
|                               |  Replication errors                                |  Replication errors persist for more than 2 minutes                               |
| **Disk I/O and Resource Usage** |  Disk read/write latency                          |  Disk latency exceeds 10ms for reads/writes                                       |
|                               |  IOPS                                             |  Disk usage exceeds 85% capacity                                                  |
|                               |  Disk space usage                                 |                                                                                     |
| **Backup and Restore**        |  Backup job success/failure                       |  Backup fails or takes longer than scheduled time (e.g., 2 hours)                 |
|                               |  Backup duration                                  |  Backup job has not run within the defined interval (e.g., daily/weekly)          |
|                               |  Restore validation                               |                                                                                     |
| **Error Logs and Transaction Failures** |  Number of transaction errors              |  More than 5% of transactions fail within 10 minutes                              |
|                               |  Error log size                                   |  Critical error codes appear in logs (e.g., deadlocks, data corruption)           |
|                               |  Specific error patterns                          |                                                                                     |
| **Resource Utilization**      |  CPU usage                                        |  CPU usage exceeds 90% for 5 minutes                                              |
|                               |  Memory usage                                     |  Buffer pool usage exceeds 90%                                                    |
|                               |  Buffer pool usage                                |                                                                                     |

## Alerting Rules

Alerting rules for database monitoring are criteria that trigger alerts when certain conditions are met. These rules compare metric values to threshold values over a time period.

| **Alert Type**                    | **Threshold**                                                       | **Duration**  | **Reason**                                                     |
|------------------------------------|---------------------------------------------------------------------|---------------|---------------------------------------------------------------|
| **High CPU Usage**                 | > **85%** CPU usage                                                 | **5 minutes** | High CPU usage can indicate overloading or performance issues. |
| **High Memory Usage**              | > **80%** memory usage                                              | **5 minutes** | High memory usage could lead to swapping or out-of-memory errors. |
| **Slow Queries**                   | > **100** slow queries                                              | **10 minutes**| High slow queries indicate inefficient operations. |
| **Database Connection Limit**      | > **90%** of max allowed connections                                 | **5 minutes** | High connection limit may prevent new connections.  |
| **Disk Space Usage**               | > **80%** disk space usage on root filesystem                       | **10 minutes**| Running out of disk space may cause crashes. |
| **Replication Lag**                | > **60 seconds** replication lag                                    | **5 minutes** | Replication lag affects data consistency between systems. |
| **Database Query Error Rate**      | > **1000 errors** per minute                                        | **1 minute**  | High error rates indicate potential issues or misconfigurations. |
| **Database Unavailable**           | Database is unreachable (`up = 0`)                                  | **5 minutes** | The database being down can lead to failures. |

## Steps for Creating Alert Rule

| Link         | Description                                                    |
|--------------|---------------------------------------------------------------|
| [Grafana](https://github.com/avengers-p11/Documentation/blob/main/Alter.md#types-of-alert-rules) | Link to Grafana Alert Rule |


**Example of Prometheus Alerting Rules and Integration**

![image](https://github.com/user-attachments/assets/461f9bd9-2818-441a-a4f6-51f9131aeca0)


## Alert Severity Levels
![image](https://github.com/user-attachments/assets/9a04a316-8099-4723-a88c-bdf2bdd673f9)

| **Severity Level** | **Description**                                                                                              | **Examples**                                                                                         | **Action**                                                               |
|--------------------|--------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------|
| **Critical**        | Immediate attention required. These issues can lead to system failures or significant downtime.               | - Database is down <br> - Replication lag > 60 seconds <br> - High CPU usage > 85%                   | - Investigate immediately <br> - Resolve issue or escalate if necessary  |
| **High**            | Major problems that could cause disruptions or performance degradation.                                      | - High memory usage > 80% <br> - Slow queries > 100 <br> - Database connection limit exceeded        | - Address urgently <br> - Perform investigation and take corrective actions |
| **Medium**          | Issues that may affect the system but are not immediately urgent.                                             | - Disk space usage > 75% <br> - Minor query errors <br> - Moderate replication lag                    | - Investigate <br> - Plan resolution before escalation                   |
| **Low**             | Non-critical issues that won't cause immediate harm but could affect performance over time.                  | - Database query count spikes <br> - Minor configuration changes <br> - Normal query execution time  | - Monitor over time <br> - Fix if the issue persists or worsens          |
| **Informational**   | General system status updates or routine actions, providing visibility without indicating problems.          | - Backup completed successfully <br> - Health check reports <br> - System performance in normal range | - No immediate action required <br> - Monitor trends and record info    |
| **Warning**         | Potential problems that could escalate into critical issues but are not urgent.                              | - Disk usage > 80% <br> - High CPU usage approaching 85% <br> - Minor replication lag (< 60 seconds)   | - Monitor and prepare for possible escalation <br> - Mitigate risks      |
| **Notice**          | Informational alerts documenting normal activities, scheduled tasks, or maintenance.                         | - Server reboot completed <br> - Routine maintenance updates <br> - Routine data consistency checks  | - Record the event <br> - Ensure successful completion                   |
| **Clear**           | Alerts indicating that a previous issue is resolved or no longer active.                                      | - Issue resolved after restart <br> - Critical alert cleared <br> - Resource utilization returned to normal | - Ensure system stability <br> - Confirm the issue is fully resolved   |

## Alerting Process

| Step                   | Description                                                                                           |
|------------------------|-------------------------------------------------------------------------------------------------------|
| **Monitor Database Metrics** | Use monitoring tools (e.g., Prometheus, Zabbix, Datadog) to track metrics.                   |
| **Define Thresholds**        | Establish thresholds based on database performance and best practices.                             |
| **Alert Configuration**      | Set up alerts using the monitoring tool and define escalation paths based on alert severity.       |
| **Alert Acknowledgement**    | When an alert triggers, the relevant team acknowledges it and investigates the issue.              |
| **Action and Resolution**    | Resolve the root cause of the alert (e.g., optimize slow queries, increase resources).             |
| **Post-Alert Review**        | After resolving the issue, perform a post-mortem analysis to understand the cause and improve future prevention. |


## Conclusion
Database monitoring is important to keep your database running smoothly. By tracking key metrics, setting up alerts, and defining rules for different levels of issues, you can catch problems early and fix them before they become big problems. When an alert goes off, the team checks it, takes action to solve the issue, and reviews what happened to avoid it in the future. This process helps ensure your database stays healthy and performs well.

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
| Alert Moinitoring    | [Link](https://medium.com/trendyol-tech/alert-and-monitoring-with-grafana-b659c433bb51)          |
| DB Monitoring  | [Link](https://learn.microsoft.com/en-us/azure/azure-monitor/alerts/alerts-processing-rules?tabs=portal) |
