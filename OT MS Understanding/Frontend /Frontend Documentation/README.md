# Frontend  Detailed Document

| Author      | Created on  | Version    | Last updated by | Last edited on |
|-------------|-------------|------------|-----------------|----------------|
|Raman Tripathi| 24-11-24    | Version 1  | Raman Tripathi   | 24-11-24       |


## Purpose
This document provides an overview of the OT-Microservices stack, focusing on the ReactJS-based frontend and its integration with backend services such as Employee, Salary, and Attendance APIs. The architecture is built for scalability, performance, and maintainability, leveraging Redis for caching, ScyllaDB for NoSQL, and PostgreSQL for relational data.

## Table of Contents
1. [Frontend Web](#frontend-web)
2. [Employee API](#employee-api)
3. [Salary API](#salary-api)
4. [Attendance API](#attendance-api)
5. [Redis](#redis)
6. [ScyllaDB](#scylladb)
7. [PostgreSQL](#postgressql)
8. [Conclusion](#conclusion)
9. [Contact Information](#contact-information)
10. [References](#references)



### Architecture
<img width="656" alt="image" src="https://github.com/user-attachments/assets/0a2f0273-2903-497f-ba46-a29d69faac2c">

### Frontend Web:
The Frontend Web is the primary user interface for the OT-Microservices stack. It is a ReactJS-based application that allows users to interact with the system through a web browser. Built using the ReactJS framework, it provides a fast, responsive, and dynamic UI that can handle complex user interactions with minimal loading times.

| **Component**       | **Description**                                                                                                                                                                                   |
|---------------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
| **ReactJS**         | A popular JavaScript library for building user interfaces, known for its component-based architecture and efficiency in rendering. React enables developers to build reusable components, enhancing both maintainability and scalability. |
| **Cross-platform**  | The frontend is designed to run on any platform that supports modern browsers, ensuring compatibility across multiple operating systems and devices.                                                |
| **Dependencies**    | The frontend depends on several backend services (APIs) to fetch and display data in real time. These APIs include the Employee API, Salary API, and Attendance API.                               |
| **Build process**   | The frontend is compiled and optimized for production using npm commands and a Makefile. After building, static files are served through a web server, and the bundled application is deployed.     |
| **Rendering Logic** | React's root element, defined in the index.html file, is where the React components are rendered. The entire app runs within this div, with backend data dynamically injected into the UI via API calls. |

### Employee API:
The Employee API is responsible for managing all employee-related data and operations within the system. It is one of the critical microservices in the OT-Microservices stack, providing endpoints for creating, reading, updating, and deleting (CRUD) employee records.

| **Aspect**     | **Description**                                                                                                                |
|----------------|--------------------------------------------------------------------------------------------------------------------------------|
| **Functionality** | This API handles operations such as employee registration, updating employee information, retrieving employee profiles, and more. Each endpoint corresponds to a specific function, such as `/api/v1/employee/{id}` for fetching employee details. |
| **Caching**    | The Employee API utilizes Redis for caching frequently requested employee data to reduce database queries and improve performance. If the data is cached, it is served directly from Redis; otherwise, it is fetched from the primary database, ScyllaDB. |
| **Database**   | All employee-related data is stored in ScyllaDB, a NoSQL database optimized for handling large datasets with low-latency read and write operations. |

### Salary API:
The Salary API manages all salary-related operations, including salary calculations, pay slips, and adjustments. It serves as another independent microservice in the stack and is tightly integrated with both the frontend and the other APIs.

| **Aspect**     | **Description**                                                                                                                |
|----------------|--------------------------------------------------------------------------------------------------------------------------------|
| **Functionality** | This API provides endpoints for fetching salary details for employees, calculating deductions and bonuses, and updating salary records. For example, `/api/v1/salary/{employeeId}` retrieves the salary details of a particular employee. |
| **Caching**    | Like the Employee API, the Salary API also leverages Redis for caching frequently accessed salary data, improving query speed and reducing the load on the database. |
| **Database**   | The salary data is stored in ScyllaDB, ensuring that large amounts of salary data can be efficiently managed and retrieved with minimal latency. |

### Attendance API:
The Attendance API handles all aspects of employee attendance tracking and management. This includes logging attendance, monitoring work hours, and tracking leaves or absences.

| **Aspect**     | **Description**                                                                                                                |
|----------------|--------------------------------------------------------------------------------------------------------------------------------|
| **Functionality** | Key functionalities include endpoints for logging attendance (`/api/v1/attendance/log`), viewing attendance history (`/api/v1/attendance/history/{employeeId}`), and calculating hours worked in a given period. The Attendance API ensures that attendance records are accurately logged and retrieved. |
| **Caching**    | Unlike the Employee and Salary APIs, the Attendance API does not rely heavily on Redis for caching, as attendance data may be more frequently updated and requires real-time accuracy. |
| **Database**   | The Attendance API uses PostgreSQL, a powerful, open-source relational database, for storing attendance records. PostgreSQL is known for its ACID compliance (Atomicity, Consistency, Isolation, Durability), making it ideal for handling time-sensitive and accurate transactional data like attendance. |

### Redis:
Redis is an in-memory data store used primarily for caching in the OT-Microservices stack. It serves as a high-speed caching layer to store frequently accessed data, reducing the load on the backend databases and improving response times for the APIs.

| **Aspect**         | **Description**                                                                                                                |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------|
| **Purpose**        | Redis is utilized by the Employee and Salary APIs to cache data that is frequently requested, such as employee profiles and salary details. This significantly reduces the number of direct database queries, enhancing the application's performance. |
| **Mechanism**      | When a request is made to fetch employee or salary data, the respective API first checks Redis to see if the data is available in the cache. If not, it retrieves the data from the database and stores it in Redis for future use. |
| **Cache Invalidation** | To ensure that the data in Redis is up-to-date, cache invalidation strategies are employed. For example, when an employee's data is updated, the corresponding cache entry is invalidated or updated to reflect the new data. |

### ScyllaDB:
ScyllaDB is the primary NoSQL database used in the OT-Microservices stack to store employee and salary data. It is a highly scalable, low-latency database that is optimized for large-scale applications.

| **Aspect**            | **Description**                                                                                                                |
|-----------------------|--------------------------------------------------------------------------------------------------------------------------------|
| **NoSQL Database**    | ScyllaDB is a NoSQL database, meaning it does not rely on the traditional relational model of tables and joins. Instead, it uses a column-family structure similar to Apache Cassandra, which allows for highly efficient data retrieval and storage. |
| **High Performance**  | ScyllaDB is designed for high throughput and low latency, making it ideal for applications that need to handle large amounts of data with minimal delays. This is crucial for the Employee and Salary APIs, where data needs to be accessed quickly and consistently. |
| **Distributed Architecture** | ScyllaDB supports distributed data storage across multiple nodes, ensuring that the system can scale horizontally and remain available even in case of hardware failures. |

### PostgreSQL:
PostgreSQL is the relational database used for storing attendance records in the OT-Microservices stack. It is known for its reliability, strong ACID properties, and support for complex queries and transactions.

| **Aspect**             | **Description**                                                                                                                |
|------------------------|--------------------------------------------------------------------------------------------------------------------------------|
| **Relational Database** | Unlike ScyllaDB, PostgreSQL is a relational database, which means it uses tables, rows, and relationships between tables. This makes it suitable for managing structured data with predefined relationships, such as employee attendance records. |
| **ACID Compliance**    | PostgreSQL ensures data integrity through its ACID properties. This means that attendance data is reliably stored, ensuring that each transaction (like logging attendance) is processed in a consistent and isolated manner, even in the event of system failures. |
| **Transactional Data** | PostgreSQL’s transactional capabilities make it ideal for tracking attendance, as every record needs to be stored accurately without data loss or corruption. Complex queries and reporting can also be efficiently handled, making it easier to generate attendance reports for analysis. |

### Conclusion
The OT-Microservices stack combines a ReactJS frontend with backend services using Redis for caching, ScyllaDB for NoSQL, and PostgreSQL for relational data. This ensures scalability, performance, and easy maintenance. The Employee, Salary, and Attendance APIs manage data efficiently, with Redis boosting response times. ScyllaDB and PostgreSQL ensure reliable data storage and retrieval. Together, they provide a high-performing system for managing employee operations seamlessly.

### Contact Information

For more information, feedback, or assistance, feel free to contact:
| Name         | Email address                       |
|--------------|-------------------------------------|
| Raman Tripahi | raman.tripathi.snaatak@mygurukulam.co  |

### References
| Links | Descriptions|
|-------|--------------|
|https://github.com/OT-MICROSERVICES|Opstree OT-Microservices|


