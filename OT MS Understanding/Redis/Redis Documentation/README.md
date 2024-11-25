# Redis Documentation

| **Author**            | **Created on** | **Version** | **Last updated by**       | **Last edited on** | **Reviewer**      |
|-----------------------|----------------|-------------|----------------------------|---------------------|-------------------|
| Anugra W. Lepcha      | 12-11-24       | Version 1.1  | Anugra W. Lepcha           | 14-11-24           | Shreya Jaiswal    |

## Table of Contents
1. [Redis: Remote Dictionary Server](#redis-remote-dictionary-server)
2. [Why we choose redis](why-we-choose-redis)
3. [Why Use an In-Memory Database?](#why-use-an-in-memory-database)
4. [What is Caching?](#what-is-caching)
5. [How Does Caching in Redis Work?](#how-does-caching-in-redis-work)
6. [Redis Persistence](#redis-persistence)
7. [What are Key-Value Pairs?](#what-are-key-value-pairs)
8. [Rich Data Structures](#rich-data-structures)
9. [Benefits of Redis](#benefits-of-redis)
10. [Best Practices of Redis](#best-practices-of-redis)
11. [Conclusion](#conclusion)
12. [Contact Information](#contact-information)
13. [References](#references)

---

![8533bf77-bf19-4feb-b744-c4c29bd38592_1616x892](https://github.com/user-attachments/assets/b43592e8-ab23-4b23-92eb-0186eda72370)


## Redis: Remote Dictionary Server

Redis, short for **Remote Dictionary Server**, is an open-source, in-memory data store developed by **Salvatore Sanfilippo** in 2009 while addressing real-time log management challenges at the Italian startup **Loggly**. Redis stores data directly in memory, which enables exceptionally fast data retrieval, making it ideal for use cases requiring high-speed access, like caching, session management, real-time analytics, and message brokering. Initially designed for handling basic key-value pairs, Redis has since evolved to support more complex data structures such as lists, sets, sorted sets, and hashes. This versatility allows Redis to function effectively as a cache, message broker, and even a primary database for applications needing efficient data access and atomic operations.

---
## Why we choose Redis
In the OT-Microservices application, all three APIs (Employee, Attendance, Salary) use a single Redis instance to speed up performance. Even though the front-end doesn’t connect to Redis directly, the APIs store frequently accessed data in Redis because it’s much faster than ScyllaDB for read-heavy tasks. This reduces the load on the database and helps the APIs respond quickly without querying the database every time. Redis also lets the APIs share data, so they don’t need to make the same calls over and over. It keeps the data updated in real-time, improving efficiency and reducing delays in the system.

---
## Why Use an In-Memory Database?

Redis operates as an **in-memory database** by storing data in **RAM**, which allows for much faster data access than disk-based storage. This optimization for speed is beneficial in applications requiring real-time data handling. Example use cases include:

| **Use Case**            | **Description**                                                                                           |
|-------------------------|-----------------------------------------------------------------------------------------------------------|
| **Real-Time Analytics** | Financial systems and IoT applications that require instant data processing.                              |
| **Online Gaming**       | Real-time player statistics, leaderboards, and matchmaking.                                               |
| **E-commerce**          | Managing shopping carts, caching product information, and handling high-traffic sales.                    |
| **Social Media**        | Quick retrieval of user feeds and notifications.                                                          |

---

## What is Caching?

**Caching** is a technique for storing frequently accessed data temporarily in a "cache" for fast retrieval. Redis is ideal for caching due to its in-memory nature and high-speed data processing, reducing the load on primary databases by serving cached data.

---
![Screenshot 2024-11-13 145137](https://github.com/user-attachments/assets/e89ceb02-235a-4142-b2ca-490374f2dd87)

## How Does Caching in Redis Work?

| **Step**               | **Description**                                                                                      |
|------------------------|------------------------------------------------------------------------------------------------------|
| **Cache Miss**         | If requested data isn't in memory, Redis retrieves it from the main database.                        |
| **Cache Hit**          | If the data is already in memory, Redis returns it instantly.                                        |
| **Cache Update**       | New or updated data is stored in memory for future access.                                           |
| **Cache Invalidation** | When underlying database data changes, Redis updates or removes the cached data to maintain consistency. |

---
![0_eEt4kTo6zQurjVCu (1)](https://github.com/user-attachments/assets/7ba3bc3c-8fe1-4910-96bb-1b6ab0dd6cc7)


## Redis Persistence

Redis offers **persistence** features to store data on disk for recovery after a crash or shutdown. Redis persistence can be configured in different ways:

- **Snapshotting**: Periodically saves the entire dataset to disk. It’s fast but may lead to data loss if Redis crashes between snapshots.
- **Append-Only File (AOF)**: Logs each write operation to a file, allowing for full recovery in case of a crash, though it is more resource-intensive.

---

![durable-redis-2-1200x650](https://github.com/user-attachments/assets/aff373dd-47fd-4d9b-a4cd-bd84ba2d0773)

## What are Key-Value Pairs?

In Redis, a **key-value pair** is the fundamental data structure, where a unique key identifies the data stored as the value. Redis supports various data types for both keys and values, such as strings, hashes, lists, sets, and sorted sets. These data types enable developers to store and manipulate different types of data, including text, numbers, and more complex structures.

Redis offers a range of commands to work with key-value pairs, including:
- **Strings**: `SET`, `GET`, `DEL`
- **Hashes**: `HSET`, `HGET`, `HDEL`
- **Lists**: `LPUSH`, `LPOP`, `LRANGE`

---

## Rich Data Structures

Redis provides diverse **data structures** to optimize data organization and access. Each structure has a unique set of operations that enhance data management and retrieval:

| **Data Structure**      | **Description**                                                              |
|-------------------------|------------------------------------------------------------------------------|
| **Strings**             | Store and manipulate text or binary data.                                    |
| **Hashes**              | Store complex data structures with field-value pairs.                        |
| **Lists**               | Useful for ordered collections of strings.                                   |
| **Sets**                | Hold unique elements without a specific order.                               |
| **Sorted Sets**         | Like sets but maintain a specific order based on scores.                     |

These data structures allow efficient and flexible data manipulation within Redis.

---

## Benefits of Redis

Redis offers several advantages:

| **Advantage**            | **Description**                                                                                           |
|--------------------------|-----------------------------------------------------------------------------------------------------------|
| **High-Speed Access**     | Can handle millions of operations per second.                                                            |
| **Atomic Transactions**   | Supports atomic commands, enabling applications to perform multiple operations safely.                    |
| **Pub/Sub Messaging**     | Allows fast data sharing between applications.                                                           |
| **Scalability**           | Redis can be deployed across multiple machines, supporting distributed systems and high-availability configurations. |
| **Advanced Features**     | Includes unique tools like **pub/sub** messaging, **transactions**, and **Lua scripting** for powerful application scenarios. |

---

## Best Practices of Redis

| **Best Practice**               | **Description**                                                   |
|----------------------------------|-------------------------------------------------------------------|
| **Use Redis for Caching Only**   | Use Redis as a cache to speed up access to frequently used data, not as a primary database.               |
| **Set Expiry Times on Cached Data** | Set expiration times (`TTL`) for cached data to prevent memory overload.                                  |
| **Avoid Large Keys**            | Avoid storing large data objects in Redis to improve performance and reduce memory usage.                  |
| **Use Redis Data Structures Efficiently** | Pick the right data structure for your needs, like sets for unique items or lists for ordered data.     |
| **Monitor Redis Performance**   | Regularly check Redis' performance to ensure it runs efficiently and doesn't consume too many resources.    |
| **Use Redis Persistence Wisely** | Use persistence settings (RDB or AOF) based on your need for durability, but balance it with performance.    |
| **Sharding and Replication**    | Use sharding and replication to scale Redis and keep it fault-tolerant across multiple servers.             |
| **Optimize Memory Usage**       | Use memory management tools like eviction policies (e.g., LRU) to optimize Redis memory usage.             |
| **Secure Redis**                | Protect Redis with passwords, encryption, and by limiting access to trusted IPs.                          |
| **Avoid Blocking Operations**   | Avoid commands like `BLPOP` or `BRPOP` that can block Redis, especially in high-traffic scenarios.         |

---

## Conclusion

Redis is a high-performance, in-memory data store suited for use cases requiring quick data access, like caching, real-time analytics, and session management. It supports rich data structures, atomic operations, and provides persistence options (snapshotting and AOF) for data durability. Redis's flexibility and speed make it an ideal solution for developers seeking to optimize application performance and scalability.

---

## Contact Information

| **Name**            | **Email address**                  |
|---------------------|------------------------------------|
| Anugra W. Lepcha    | wangchuklepcha801@gmail.com        |

---

## References

| Link                                                                                                          | Description                                               |
|---------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------|
| [What is Redis and How Does it Work? - Medium](https://medium.com/@ayushsaxena823/what-is-redis-and-how-does-it-work-cfe2853eb9a9) | Overview of Redis' structure and functions.               |
| [Redis: What It Is, What It Does, and Why You Should Care - Backendless](https://backendless.com/redis-what-it-is-what-it-does-and-why-you-should-care/) | Explanation of Redis' importance and common use cases.    |
| [Redis Architecture Notes](https://architecturenotes.co/p/redis)                                              | Detailed architectural insights into Redis operations.    |

