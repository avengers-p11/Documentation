
# Salary API Documentation

| **Author** | **Created on** | **Last updated by** | **Last edited on** | **Reviwer L0** |**Reviwer L1** |**Reviwer L2** |
|------------|----------------|----------------------|---------------------|---------------|---------------|---------------|
| Pravesh Kumar      | 12-11-24      | Pravesh Kumar             | 15-11-24           | Khushi  | | |

## Table of Contents
- Salary-API overview
- Purpose of the Salary API
    - The primary purpose of the Salary API
    - Supported features of the Salary API
    - Components of the Salary API
- Architecture
- ScyllaDB
    - Why ScyllaDB
    - Use Cases
- Redis
    - Why Redis
    - Use Cases
- Migrate
    - Why Migrate
    - Use Cases
- Maven
    - Why Maven
    - Use Cases
- Swagger
    - Key Benefits
    - Core Components
    - Common Use Cases
- Conclusion
- Contact Information
- References

  
## Salary-API overview

The Salary API is a core component of the OT-Microservices project, providing functionality to handle employee salary-related transactions and information. It operates as a standalone microservice within a distributed system, allowing seamless integration with other services like Employee and Attendance APIs. Designed to meet high-performance, reliability, and scalability requirements, the Salary API is optimized for cloud environments and uses modern development and deployment practices.

## Purpose of the Salary API

### The primary purpose of the Salary API:

- Manage and process salary records for employees.

- Integrate easily with other microservices within the OT-Microservices ecosystem.
  
- Support efficient data storage, retrieval, and calculation related to employee compensation.
  
- It is essential in automating payroll processes, enhancing accuracy in employee compensation records, and simplifying the financial operations within the organization.

### Supported features of the Salary API:-

- Spring boot based web framework, which uses tomcat as webserver.
- ScyllaDB is used as primary database for storing all the salary data.
- Redis as cache manager to store the cache response.
- Prometheus and Open-telemetry metrics support for monitoring and observability
- Swagger integration for the API documentation of endpoints and payloads.
- Database migration using the tool called migrate.

### Components of the Salary API

- [ScyllaDB](https://www.scylladb.com/)

- [Redis](https://redis.io/)

- [Migrate](https://github.com/golang-migrate/migrate)

- [Maven](https://maven.apache.org/)

## Architecture

![Screenshot 2024-11-13 at 11 47 43 PM](https://github.com/user-attachments/assets/4b74d22c-97f8-4d12-8636-e75c9c04d350)

## ScyllaDB

ScyllaDB is a high-performance NoSQL database designed as a drop-in replacement for Apache Cassandra. It offers low-latency and high-throughput data storage, optimized for distributed applications needing scalability and minimal latency. Written in C++, ScyllaDB is engineered to maximize hardware efficiency, leveraging the full power of modern multi-core CPUs.

### Why ScyllaDB:

- High Performance: ScyllaDB achieves extremely high throughput with very low latency, which makes it suitable for applications requiring real-time data processing.
- Cassandra Compatibility: It uses the same query language (CQL) and data model as Cassandra, making it easier for organizations to migrate existing Cassandra workloads.
- Auto-Sharding: ScyllaDB automatically shards data across nodes, ensuring balanced distribution without manual intervention.
- Minimal Tuning: ScyllaDB automates many database management functions, which reduces the need for manual tuning.

### Use Cases:

- Iot Applications: Collecting and storing data from millions of devices in real time.
- Financial Services: Handling large amounts of transaction data with low latency for fraud detection and analytics.
  
![ScyllaDB-Manager](https://github.com/user-attachments/assets/4d7403a8-d947-4390-bf26-d1d032302498)

## Redis

Redis (Remote Dictionary Server) is an open-source, in-memory data structure store often used as a distributed cache, session store, and message broker. It supports data structures like strings, lists, sets, hashes, and sorted sets, making it very versatile. Due to its in-memory nature, Redis can offer extremely fast read and write performance.

### Why Redis:

- Caching: Frequently accessed data can be stored in Redis to reduce load on databases and enhance application performance.
- Session Management: Used as a session store, Redis can handle user sessions for applications where quick retrieval is necessary.
- Pub/Sub Messaging: Redis’s Publish/Subscribe feature is helpful in building real-time messaging and notification systems.
- Data Persistence: While primarily an in-memory store, Redis can persist data to disk, allowing it to recover data after a restart.

### Use Cases:

- Web Caching: Storing computed or frequently accessed data to improve response times.
- Leaderboard Systems: Using sorted sets for ranking systems in gaming or social media platforms.
- Real-Time Analytics: Aggregating or analyzing event data in real-time, for instance, in monitoring or ad tech applications.

![9c501ae0-6878-464e-bb4c-f61b40c6f8be](https://github.com/user-attachments/assets/0c103a35-b906-4df0-84ce-00bc03f7d3c6)

## Migrate

Database migration tools like migrate (or Flyway, Liquibase, etc.) are essential for managing and tracking changes in the database schema as an application evolves. migrate is particularly popular in Go-based environments, where it helps maintain version-controlled schema files, ensuring database consistency across different environments.

### Why Migrate:

- Schema Versioning: Tracks changes over time, providing a versioned history of modifications, making it easy to move between versions if needed.
- Consistency Across Environments: Ensures the database schema in production is identical to development, preventing issues related to inconsistent schemas.
- Reversible Changes: Many migration tools allow for rolling back changes, enabling safe deployment of schema modifications.

### Use Cases:

- Database Schema Evolution: Modifying schemas over time without requiring manual SQL scripts.
- CI/CD Integration: Automating database migrations as part of the continuous deployment pipeline.
- Multi-Tenant Applications: Managing separate databases or schemas for each tenant with ease, using a versioned migration tool.

## Maven

Maven is a build automation and dependency management tool primarily for Java applications. It simplifies project builds, dependency resolution, and project setup using a declarative configuration file, pom.xml (Project Object Model). Maven is an integral part of Java development due to its streamlined process for managing dependencies and building complex project hierarchies.

### Why Maven:

- Dependency Management: Automatically downloads and manages Java libraries, reducing manual management of JAR files.
- Build Consistency: Ensures that builds are reproducible and consistent across different environments.
- Project Structure: Encourages a standardized project structure, which helps teams to collaborate more effectively.
- Plugins: Extensive plugin support for various tasks, such as testing, packaging, and deploying applications.

### Use Cases:

- Java Project Builds: Compiling code, running tests, and creating deployable artifacts (e.g., JARs or WARs).
- Dependency Resolution: Automatically fetching required libraries and managing their versions.
- Multi-Module Projects: Managing large applications composed of multiple modules or libraries in a single workspace.
- Continuous Integration: Integrates well with CI tools like Jenkins to automate the build and testing process, especially for Java applications.
![maven-architecture-1024x250](https://github.com/user-attachments/assets/33814d03-39b7-4e99-bb55-e5173eb61dfe)

## Swagger

Swagger is an open-source toolset for designing, building, documenting, and testing RESTful APIs. It leverages the OpenAPI Specification (OAS) to standardize API definitions and provide interactive documentation.

### Key Benefits:

- Interactive Documentation: Swagger UI provides a user-friendly, interactive interface for viewing and testing API endpoints.
- Standardized API Definition: Uses OpenAPI Specification, ensuring consistency and clarity in API documentation.
- Client SDK Generation: Automatically generates client libraries in various languages for easier API integration.
- Enhanced Collaboration: Helps frontend and backend teams work together effectively by offering a clear, shared API reference.
  
### Core Components:

- Swagger UI: An interactive, web-based API documentation viewer and testing tool.
- Swagger Editor: A tool for creating and editing OpenAPI specifications.
- Swagger Codegen: Generates client SDKs and server stubs based on OpenAPI specs.
- OpenAPI Specification (OAS): A standardized format for defining and documenting REST APIs.

### Common Use Cases:

- API Documentation: Creates comprehensive, interactive API documentation for developers and users.
- Testing and Debugging: Allows developers to test API endpoints directly in the documentation.
- Client SDK Generation: Streamlines API integration by providing pre-built SDKs.
- Team Collaboration: Acts as a bridge between development teams by providing a single source of truth for API specifications.

## Conclusion

The Salary API is an essential service in the OT-Microservices system, designed for efficient management of salary transactions. Using ScyllaDB for scalable storage, Redis for caching, Migrate for database version control, Swagger for interactive documentation, and Maven for streamlined builds, it offers high performance and reliability. The API integrates seamlessly with other microservices, supporting fast data access and scalability, which enhances user experience and supports continuous deployment in an enterprise environment.


# Contact Information

| **Name** | **Email address**            | **Github ID**
|----------|-------------------------------|-------------------|
| Pravesh Kumar    |  pravesh.kumar611@gmail.com           | Pravesh899 |

# References

| **Link** | **Description**            |
|----------|-------------------------------|
| [What is Redis and How Does it Work? - Medium](https://medium.com/@ayushsaxena823/what-is-redis-and-how-does-it-work-cfe2853eb9a9)   |  Overview of Redis' structure and functions.          |
| [ScyllaDB Installation Guide](https://opensource.docs.scylladb.com/stable/getting-started/install-scylla/install-on-linux.html)   | Comprehensive guide for installing ScyllaDB on Linux. |
| [Swagger](https://swagger.io/docs/specification/v2_0/what-is-swagger/)   | Swagger Docs |
| [Maven](https://maven.apache.org/what-is-maven.html)   | Maven Introduction |


