
# Conclusion Documentation of **Monorepo vs Micro Repo**

| Author        | Created on | Version | Last updated by | L0 Reviewer |
  |-------------|---------|-------------|-------------|---------|
  | Mohit Saini | 21-11-24 | version 1 | Mohit Saini | Khushi |


## Table of Contents
- [Purpose](#purpose)
- [Introduction](#introduction)
- [Comparison: Monorepo vs Micro Repo](#comparison-monorepo-vs-micro-repo)
- [Conclusion](#conclusion)
- [Contact Information](#contact-information)
- [References](#references)


## **Purpose**
This document explains two ways to manage code in software development: Monorepo and Micro Repo. It introduces both methods, compares them, and gives advice on which one to choose based on what a team needs. The goal is to help teams decide the best way to organize their code.


## **Introduction**



### **Monorepo**
A **Monorepo** (short for **monolithic repository**) is a way to manage multiple projects or services in one single place. It makes it easier for teams to work together, share code, and handle dependencies. Big companies like Google, Microsoft, and Facebook use Monorepos to make working on large software projects simpler.

#### Related Resources
**Please refer to the reference link mentioned below**
| Link         | Description         |
|--------------|------------------------|
| [Mono repo ](https://github.com/avengers-p11/Documentation/tree/main/VCS%20Design%20%2B%20POC/Mono-Micro%20Repo/Mono%20repo%20features) | Mono repo Features| 

#
### **Micro Repo**
A **Micro Repo** is when each project or part of a project is kept in its own separate place. This works well for small, independent projects that don't need to share a lot of code. It lets teams work on their own without dealing with a big shared codebase.

#### Related Resources
**Please refer to the reference link mentioned below**
| Link         | Description         |
|--------------|------------------------|
| [Micro repo ](https://github.com/avengers-p11/Documentation/blob/main/VCS%20Design%20%2B%20POC/Mono-Micro%20Repo/Micro%20repo%20features/README.md) | Micro repo Features|
#
 
## **Comparison: Monorepo vs Micro Repo**

![image](https://github.com/user-attachments/assets/8192f784-f789-4cf2-b0ad-318b91c05d70)


| **Aspect**                  | **Monorepo** (When it's Better)                                                                         | **Micro Repo** (When it's Better)                                                                 |
|-----------------------------|---------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------|
| **Team Collaboration**       | Best for closely-knit teams where shared knowledge and collaboration are essential.                    | Ideal for independent teams focusing on isolated projects without much overlap.                 |
| **Code Sharing**             | Excellent when projects or services share a lot of common code, libraries, or tools.                   | Better when projects have little to no shared code and are entirely independent.                |
| **Dependency Management**    | Good for managing dependencies centrally and avoiding duplication.                                     | Good when teams prefer independent dependency management without centralized control.           |
| **Scalability**              | Works well for small to medium-sized projects but becomes harder to manage as the repo grows.          | Better for scaling large organizations with many independent projects.                          |
| **Testing and CI/CD**        | Centralized pipelines simplify testing for all projects.                                              | Isolated pipelines are better for projects with unique testing and deployment needs.            |
| **Version Control**          | Good for synchronized releases and managing consistent versioning across services.                    | Suitable for independent versioning and asynchronous releases of services.                      |
| **Refactoring**              | Best when frequent changes to shared code are required, ensuring updates across all projects.          | Preferred if changes to shared code are rare or nonexistent.                                    |
| **Permissions**              | Suitable if everyone needs access to most of the codebase.                                            | Better for controlling access to specific projects or limiting exposure to sensitive code.       |
| **Build Time**               | Acceptable for smaller repositories; becomes an issue as size increases.                              | Faster build times due to smaller repositories and fewer interdependencies.                     |
| **Consistency**              | Best for enforcing consistent standards, libraries, and tools across projects.                        | Works better when individual teams want freedom to adopt their own standards and tooling.        |
| **Complexity**               | Good for maintaining a single repository but harder to manage as size and teams grow.                 | Better when managing simpler, smaller repositories with fewer interactions between them.         |


## **Conclusion**
We're using a **micro-repository** architecture to streamline development. This approach lets our teams work on individual projects without relying on each other. This makes development faster and more efficient. This approach fosters greater agility, collaboration, and adaptability to evolving project needs. This modular structure also simplifies maintenance and reduces the risk of cascading failures.


## Contact Information 
| Name         | Email Address                              |
|:------------:|:------------------------------------------:|
| Mohit Saini  | Mohit.Saini.snaatak@mygurukulam.co         |

## References 
| Links                                                                                                                      | Description |
|----------------------------------------------------------------------------------------------------------------------------|-------------|
| https://www.linkedin.com/posts/alexxubyte_systemdesign-coding-interviewtips-activity-7103760747175768065-2GR6 |  Mono Vs Micro   |







