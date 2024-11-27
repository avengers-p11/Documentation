# Git Flow Documentation

| **Author** | **Created on** | **Last updated by** | **Last edited on** | **Reviewer L0** |**Reviewer L1** |**Reviewer L2** |
|------------|----------------|----------------------|---------------------|---------------|---------------|---------------|
| Neelesh kumar      | 15-11-24      | Neelesh  Kumar             | 27-11-24           | Shikha Tripathi | | |

## Table of Contents
1. [Introduction](#introduction)
2. [Why Use Git Flow](#why-use-git-flow)
3. [Git Flow Workflow](#git-flow-workflow)
4. [Key Features](#Key-features)
5. [Advantages](#advantages)
6. [Disadvantages](#disadvantages)
7. [Conclusion](#conclusion)
8. [Contacts](#contacts)
9. [References](#references)
---

## Introduction
**Git Flow** is a robust branching model for Git, designed to support projects with release cycles. It introduces defined roles for different branches and provides a structured way to handle feature development, hotfixes, and releases.

---

## Why Use Git Flow
Git Flow is ideal for projects requiring:
- Well-defined versioning and release management.
- A stable production branch while accommodating ongoing development.
- Parallel workstreams for features, bug fixes, and releases.

---

## Git Flow Workflow

![Screenshot from 2024-11-23 13-45-55](https://github.com/user-attachments/assets/7ae85a0b-5602-45de-8e33-4f4f80de405a)

---

| **Branch**       | **Purpose**                                                                                  | **Origin**         | **Merge Into**         |
|-------------------|----------------------------------------------------------------------------------------------|--------------------|------------------------|
| **`main`**       | The production-ready branch that always contains the stable release.                        | ----                | ----                    |
| **`develop`**    | The integration branch where all features are merged.                                        | `main`             | ----                 |
| **`feature/*`**  | Branches for developing individual features or tasks.                                        | `develop`          | `develop`              |
| **`release/*`**  | Branches for preparing a release (e.g., final bug fixes, documentation updates).             | `develop`          | `main`, `develop`      |
| **`hotfix/*`**   | Branches for quick fixes to production (e.g., critical bug fixes).                           | `main`             | `main`, `develop`      |
| **`support/*`**  | Optional branches for maintaining older versions of the software.                            | Specific tag on `main` | ---                |

---

### Key features 
1. Dedicated Branches for Different Purposes
2. Structured Workflow for Releases   
3. Parallel Development
4. Support for Continuous Delivery
5. Clear Code History
6. Rollback and Version Control
7. Collaboration-Friendly
8. Flexibility for Hotfixes
9. Compatibility with Versioning
10. Enhanced Stability    




## PR (Pull Request) in GitFlow

A Pull Request is a mechanism used in Git platforms like GitHub, GitLab, or Bitbucket to propose, review, and merge code changes from one branch to another. In GitFlow, PRs are primarily used for collaboration and code quality assurance.

 ## Versioning in GitFlow

Versioning in GitFlow refers to tagging specific commits in the repository with version numbers (e.g., v1.0.0) to identify and track releases.

## Advantages and Disadvantages

## Advantages
| **Advantage**                         | **Description**                                                                  |
|---------------------------------------|----------------------------------------------------------------------------------|
| Clear branch structure                | Defined roles for each branch improve organization and clarity.                  |
| Supports parallel development         | Allows simultaneous work on features, releases, and bug fixes.                  |
| Stable production branch              | Ensures the `main` branch always contains production-ready code.                 |
| Simplifies versioning                 | Release and hotfix branches help with semantic versioning and changelogs.       |
| Enhances collaboration                | Well-defined workflows enable team members to work independently without clashes.|

## Disadvantages
| **Disadvantage**                      | **Description**                                                                  |
|---------------------------------------|----------------------------------------------------------------------------------|
| Complex for small projects            | Overhead might be unnecessary for simple or small-scale projects.                |
| Increased merge frequency             | Frequent merging between branches increases effort and potential conflicts.      |
| Dependency on tools                   | May require additional tooling or scripts (e.g., `git-flow` command-line tool).  |
| Steeper learning curve                | Requires understanding of multiple branch types and workflows.                   |


## Conclusion
Git Flow is an excellent choice for projects that require structured development and reliable release cycles. While it may introduce complexity for small teams, its benefits in managing larger projects outweigh the challenges, ensuring stability and flexibility in software development.

---

## Contacts

| Name| Email Address      |
|-----|--------------------------|
| Neelesh kumar | nilesh.rajput.snaatak@mygurukulam.co || GitHub | URL |
|--------------|---------------|
|  devneelesh921  |  https://github.com/devneelesh921  |

## References
| **Reference**                                    | **Description**                                                                  |
|--------------------------------------------------|----------------------------------------------------------------------------------|
| [Git Flow - Atlassian](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow) | Comprehensive guide to Git Flow by Atlassian.                                   |
| [Pro Git Book](https://git-scm.com/book/en/v2)   | In-depth Git concepts and workflows explained in the Pro Git book.              |
| [Git Documentation](https://git-scm.com/doc)    | Official Git documentation for commands, features, and best practices.          |
