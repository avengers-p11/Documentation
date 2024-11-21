

# **Documentation of Micro repo**

| **Author** | **Created on** | **Version** | **Last updated by** | **Comment** | **Reviewer L0** |
|------------|-------------|-----------|--------------|-------------|-----------|
| Mohit Saini | 19-11-24 | Version 1.1 | Mohit Saini |  |  |

![image](https://github.com/user-attachments/assets/42114c80-1200-4b0c-81d5-ed0872a474b5)

# **Table of Contents**

1.  [Introduction](#introduction)

2.  [Micro Repo](#micro-repo)

3.  [Why Micro Repo?](#why-micro-repo)

4.  [Features](#features)

5.  [Advantages](#advantages)

6.  [Disadvantages](#disadvantages)

7.  [Best Practices](#best-practices)

8.  [Conclusion](#best-practices)

9.  [Contact Information](#contact-information)

10. [References](#references)




# Introduction

A repository is a central place where code, files, and data are stored,
shared, and managed. It plays a critical role in software development
for tasks like code sharing, ownership management, and merging.
Repositories are essential for deploying code to servers for public use.

# Micro Repo

A microrepo is a version control approach where each service, component,
or project within a larger software system is stored in its own separate
repository. This contrasts with a monorepo, where all services or
components are stored together in one large repository.

![image](https://github.com/user-attachments/assets/95407199-ac24-4cce-b423-48e0e2819481)


# Why Micro Repo?

| **Reasons** | **Descriptions** |
|-----------------------|-------------------------------------------------|
| Isolation | Each repository is independent, reducing the chance of unwanted interactions between parts of the system. |
| Scalability | Microrepos can scale easily as each repository has its own build and test times, enabling individual services to scale independently. |
| Autonomy | Different teams have more control over their own codebases, allowing for faster decision-making and iteration. |
| Clear Ownership | Each repository has a clear owner, making it easier to assign responsibility and accountability for specific components or services. |

# Features

| **Feature** | **Descriptions** |
|-----------------------|-------------------------------------------------|
| Supports decentralized teams | Microrepos are suited to teams working on independent projects. |
| Enables independent release cycles | Microrepos allow for independent release cycles for different projects. |

![image](https://github.com/user-attachments/assets/15e5440b-c232-464a-9473-1d6621a135e1)


# Advantages

| **Advantages** | **Descriptions** |
|-----------------------|-------------------------------------------------|
| Fast Development | Faster pace as updates don’t rely on other teams. Releases and management are easier. |
| Flexibility | Dedicated repositories for individual services allow choosing preferred frameworks, libraries, or modules. |
| Version Control Choice | Freedom to select version control tools like Git, SVN, or Mercurial; Git remains the most commonly used. |
| Simplified CI/CD Pipelines | Each microrepo can have its own CI/CD pipeline, making build and deployment faster and more efficient without affecting other services. |

# Disadvantages

| **Disadvantages** | **Descriptions** |
|-----------------------|-------------------------------------------------|
| Increased Overhead | Maintaining multiple repositories requires extra focus and juggling between different codes. |
| Duplication of Code | Violates the DRY (Don't Repeat Yourself) principle, as similar code may exist in multiple places. |

# Best Practices

| **Practice** | **Descriptions** |
|-------------------------|-----------------------------------------------|
| Monitoring and Logging | Use centralized solutions to collect and analyze data from all services for quick issue resolution. |
| Automating Token and Key Rotation | Automate the rotation of SSH tokens and keys to save time and maintain consistency. |
| Continuous Integration/Delivery | Align operations and developers through CI/CD, improving stability and automating rollbacks. |
| Create a README File | Include a README.md to explain the project's purpose, installation, and usage for new developers. |
| Use Git Ignore | Manage Git repos effectively by ignoring unnecessary files like metadata and artifacts. |
| Add a SECURITY.md File | Include a SECURITY.md file to define and enforce a repository’s security policy. |
| Choose Communication Protocol Wisely | Select a protocol that suits independent services to ensure efficient application performance. |

# Conclusion

Repositories store and manage code in one place, making them key in software development. Microrepos mean each part of a project has its own repository, allowing teams to work independently and release updates easily. While managing many repositories can be challenging, tools like automation and good documentation help teams use microrepos effectively.

# Contact Information

| **Name**    | **Email address**       |
|-------------|-------------------------|
| Mohit Saini | it.mohitsaini@gmail.com |

# References

| **Links** | **Descriptions** |
|---------------------------------------------------------|---------------|
| [Micro Repo](https://apoorv-tomar.medium.com/a-better-understanding-of-micro-rep-vs-mono-repo-a9f31f1e20fe#:~:text=The%20micro%20repository%20enables%20fast,Code%20Reusability.) | This link explains the Micro repo |
| [Advantages and Disadvantages](https://www.linkedin.com/pulse/navigating-codebase-management-monorepo-vs-microrepo-rajeev-barnwal-u318f) | Advantages and disadvantages |
