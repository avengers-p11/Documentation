
# Conclusion Documentation of **Monorepo vs Micro Repo**

| Author        | Created on | Version | Last updated by | L0 Reviewer |
  |-------------|---------|-------------|-------------|---------|
  | Mohit Saini | 21-11-24 | version 1 | Mohit Saini |  |


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


| **Aspect**                  | **Monorepo**                                                                                              | **Micro Repo**                                                                                      |
|-----------------------------|-----------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------|
| **Definition**               | A single storage place for many projects, services, or parts of a project.                               | Many separate storage places, each for one project or service.                                      |
| **Codebase Size**            | One big codebase with lots of projects in it.                                                             | Smaller codebases, each focusing on one project or service.                                          |
| **Collaboration**            | Easier for teams to work together because everything is in one place.                                      | Teams work alone on separate projects, which gives them more freedom.                               |
| **Dependency Management**    | Manages shared code and libraries inside the same place, making it easy to track them.                     | Each project has its own code and dependencies, which can make it harder to manage.                |
| **Version Control**          | One version for everything, so it’s easier to plan releases.                                               | Each project has its own version, which can be harder to keep in sync.                             |
| **Scalability**              | Harder to grow and maintain as the codebase gets bigger.                                                  | Easier to grow because each repo is small and simpler to handle.                                    |
| **Refactoring**              | Easier to change shared code because it’s all in one place.                                                | Harder to change code across repos because you need to work with many repos at once.                |
| **Testing and CI/CD**        | Centralized testing for all projects; easy to set up testing tools for all.                                | Independent testing for each project; good for separate development, but harder to set up.         |
| **Tooling Requirements**     | Needs special tools to handle big repositories.                                                           | Needs fewer tools, but you may need simple automation to manage lots of small repos.               |
| **Permissions Management**   | Hard to control who can access what in a big repo.                                                        | Easier to control permissions, because each repo has fewer people with specific needs.              |
| **Merge Conflicts**          | More chance of conflicts when different teams work in the same repo.                                       | Fewer conflicts since teams work in separate repos with little overlap.                             |
| **Consistency**              | Easier to keep coding standards, libraries, and tools the same across all projects.                       | Harder to keep everything consistent across many separate repos.                                    |
| **Build Time**               | Takes longer to build because the repo is so big and complex.                                             | Builds faster because each repo is smaller and simpler.                                             |
| **Complexity**               | More complex as the repo gets bigger, requiring special tools to manage.                                  | Easier to manage each repo, but working across multiple repos can make things more complicated.      |


## **Conclusion**
When choosing between a **Monorepo** and a **Micro Repo** strategy, teams must consider the **size**, **complexity**, and **collaboration needs** of their projects.

- Monorepo is best for big companies where many different projects need to work together in one place. It helps teams work together and manage shared code better, but it can be harder to grow and manage because it needs special tools.
  
- Micro Repo is good for teams that want independence for each project, have small projects that don’t depend on each other, and need faster development. But having lots of separate repositories can cause issues with dependencies and keeping things consistent across projects.

## Contact Information 
| Name         | Email Address                              |
|:------------:|:------------------------------------------:|
| Mohit Saini  | Mohit.Saini.snaatak@mygurukulam.co         |

## References 
| Links                                                                                                                      | Description |
|----------------------------------------------------------------------------------------------------------------------------|-------------|
| https://www.linkedin.com/posts/alexxubyte_systemdesign-coding-interviewtips-activity-7103760747175768065-2GR6 |  Mono Vs Micro   |







