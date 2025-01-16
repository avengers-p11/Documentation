# Documentation on Alerting Rules and Process for Database Monitoring
![image](https://github.com/user-attachments/assets/20ddb9a3-de87-4fab-bd0a-ce3f4a8bc808)


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

# Introduation


# What is Database monitor
The term database monitoring refers to the tasks associated with examining the operational status of your database. Database monitoring is a vital activity for the maintenance of the performance and health of your database management system.

# Why?

| Reason                     | Description                                                                                  |
|----------------------------|----------------------------------------------------------------------------------------------|
| **Performance Optimization** | Helps identify and resolve slow queries, high latency, or bottlenecks that affect database performance. |
| **Availability and Uptime**  | Ensures the database is always accessible, reducing downtime and improving reliability.     |
| **Resource Management**      | Tracks usage of CPU, memory, storage, and I/O to optimize resource allocation and reduce costs. |
| **Error Detection and Prevention** | Identifies issues like failed connections, deadlocks, or transaction conflicts before they escalate. |
| **Scalability**              | Provides insights to scale resources appropriately as the workload grows.                  |
| **Security**                 | Monitors unauthorized access, abnormal activity, or potential breaches.                   |
| **Compliance**               | Ensures databases adhere to regulatory requirements by maintaining logs and monitoring access. |
| **User Experience**          | Improves the overall application performance, leading to a better user experience.         |


# Monitoring Parameters for DB

| Category                      | Metrics                                             | Alerting Thresholds                                                                 |
|-------------------------------|-----------------------------------------------------|-------------------------------------------------------------------------------------|
| **Query Performance**         | - Query execution time                              | - Query execution time exceeds 2 seconds                                           |
|                               | - Query queue length                                | - Query failure rate exceeds 5% over 10 minutes                                    |
|                               | - Query errors                                      |                                                                                     |
| **Database Connections**      | - Number of active connections                      | - Active connections exceed 90% of the maximum allowed                             |
|                               | - Connection pool usage                             | - Connection pool usage exceeds 85%                                                |
| **Replication Lag**           | - Replication delay in seconds                     | - Replication lag exceeds 100ms for primary-secondary setups                       |
|                               | - Replication errors                                | - Replication errors persist for more than 2 minutes                               |
| **Disk I/O and Resource Usage** | - Disk read/write latency                          | - Disk latency exceeds 10ms for reads/writes                                       |
|                               | - IOPS                                             | - Disk usage exceeds 85% capacity                                                  |
|                               | - Disk space usage                                 |                                                                                     |
| **Backup and Restore**        | - Backup job success/failure                       | - Backup fails or takes longer than scheduled time (e.g., 2 hours)                 |
|                               | - Backup duration                                  | - Backup job has not run within the defined interval (e.g., daily/weekly)          |
|                               | - Restore validation                               |                                                                                     |
| **Error Logs and Transaction Failures** | - Number of transaction errors              | - More than 5% of transactions fail within 10 minutes                              |
|                               | - Error log size                                   | - Critical error codes appear in logs (e.g., deadlocks, data corruption)           |
|                               | - Specific error patterns                          |                                                                                     |
| **Resource Utilization**      | - CPU usage                                        | - CPU usage exceeds 90% for 5 minutes                                              |
|                               | - Memory usage                                     | - Buffer pool usage exceeds 90%                                                    |
|                               | - Buffer pool usage                                |                                                                                     |


# Alerting rules
Alerting rules for database monitoring are a set of criteria that trigger alerts when certain conditions are met. These rules compare metric values to a threshold value over a set period of time. When an alert is triggered, the user is notified via a preferred method, such as email, SMS, or voice.


| **Alert Type**                    | **Threshold**                                                       | **Duration**  | **Reason**                                                     |
|------------------------------------|---------------------------------------------------------------------|---------------|---------------------------------------------------------------|
| **High CPU Usage**                 | > **85%** CPU usage                                                 | **5 minutes** | High CPU usage can indicate overloading or performance issues. |
| **High Memory Usage**              | > **80%** memory usage                                              | **5 minutes** | High memory usage could lead to swapping or out-of-memory errors. |
| **Slow Queries**                   | > **100** slow queries                                              | **10 minutes**| A high rate of slow queries indicates inefficient database operations. |
| **Database Connection Limit**      | > **90%** of max allowed connections                                 | **5 minutes** | Approaching the connection limit may prevent new connections.  |
| **Disk Space Usage**               | > **80%** disk space usage on root filesystem                       | **10 minutes**| Running out of disk space may cause the database to crash or become read-only. |
| **Replication Lag**                | > **60 seconds** replication lag                                    | **5 minutes** | Replication lag affects data consistency between master and replica. |
| **Database Query Error Rate**      | > **1000 errors** per minute                                        | **1 minute**  | High error rates indicate potential issues like misconfigurations or bugs. |
| **Database Unavailable**           | Database is unreachable (`up = 0`)                                  | **5 minutes** | The database being down can lead to critical failures.          |

# why alert rules


| **Reason**                          | **Explanation**                                                                                                                                                        |
|-------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Early Detection of Issues**       | Alerting rules help detect performance issues, system failures, and potential problems (such as high CPU or memory usage) before they escalate into major incidents. Early detection allows for quicker response and resolution. |
| **Automated Notifications**         | When specific thresholds are exceeded (like high CPU usage or slow queries), alerting rules automatically notify the appropriate team members. This ensures that the right people are informed in real time without the need for manual checks. |
| **Preventing System Downtime**      | By monitoring critical metrics like database availability and disk space, alerting rules help prevent system downtime. For instance, if disk usage exceeds 80%, an alert can trigger actions to prevent crashes or read-only states. |
| **Proactive Performance Management**| Monitoring and alerting for slow queries, replication lag, or high connection usage ensures the system remains optimized. Alerts on slow queries or high replication lag help in troubleshooting performance bottlenecks before they impact users. |
| **Minimizing Impact of Errors**     | By tracking error rates and providing quick alerts on anomalies like database errors or unavailable services, alerting rules help teams address issues swiftly and avoid larger failures. |

# Alerting Rules
Prometheus Alerting Rules
![image](https://github.com/user-attachments/assets/461f9bd9-2818-441a-a4f6-51f9131aeca0)

AlertManager Integration
![image](https://github.com/user-attachments/assets/fbc5b5cd-f116-4583-8521-6804ce3634aa)

# Alert Severity Levels

| **Severity Level** | **Description**                                                                                              | **Examples**                                                                                         | **Action**                                                               |
|--------------------|--------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------|
| **Critical**        | Immediate attention required. These issues can lead to system failures or significant downtime.               | - Database is down <br> - Replication lag > 60 seconds <br> - High CPU usage > 85%                   | - Investigate immediately <br> - Resolve issue or escalate if necessary  |
| **High**            | Major problems that could potentially cause significant disruptions or performance degradation.              | - High memory usage > 80% <br> - Slow queries > 100 <br> - Database connection limit exceeded        | - Address urgently <br> - Perform investigation and take corrective actions |
| **Medium**          | Issues that may affect the system if not resolved but are not immediately urgent.                             | - Disk space usage > 75% <br> - Minor query errors <br> - Moderate replication lag                    | - Investigate <br> - Plan resolution before escalation                   |
| **Low**             | Non-critical issues that are unlikely to cause immediate harm but could affect performance over time.        | - Database query count spikes <br> - Minor configuration changes <br> - Normal query execution time  | - Monitor over time <br> - Fix if the issue persists or worsens          |
| **Informational**   | General system status updates or routine actions, providing visibility without indicating problems.          | - Backup completed successfully <br> - Health check reports <br> - System performance in normal range | - No immediate action required <br> - Monitor trends and record info    |
| **Warning**         | Potential problems that could escalate into critical issues but are not urgent at the moment.                | - Disk usage > 80% <br> - High CPU usage approaching 85% <br> - Minor replication lag (< 60 seconds)   | - Monitor and prepare for possible escalation <br> - Mitigate risks      |
| **Notice**          | Informational alerts that document normal system activities, scheduled tasks, or maintenance.               | - Server reboot completed <br> - Routine maintenance updates <br> - Routine data consistency checks  | - Record the event <br> - Ensure successful completion                   |
| **Clear**           | Alerts that indicate the resolution of a previous issue or confirmation that a problem is no longer active.   | - Issue resolved after restart <br> - Critical alert cleared <br> - Resource utilization returned to normal | - Ensure system stability <br> - Confirm the issue is fully resolved   |

# Alerting Process
| Step                   | Description                                                                                           |
|------------------------|-------------------------------------------------------------------------------------------------------|
| **Monitor Database Metrics** | Use monitoring tools (e.g., Prometheus, Zabbix, Datadog, etc.) to track metrics.                   |
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
