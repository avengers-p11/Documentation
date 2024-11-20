# Recommendations of Commit Hooks 

  | Author        | Created on | Version | Last updated by | Last edited on |
  |-------------|---------|-------------|-------------|---------|
  | Raman Tripathi | 20-11-24 | version 1 | Raman Tripathi | 20-11-24 |

![image](https://github.com/user-attachments/assets/0c9ff608-1d67-4d20-9cd9-01415c68fdaa)


## Purpose 
This document aims to provide a comprehensive discussion on various types of commit hooks, highlighting their differences and recommending specific hooks based on their effectiveness and use cases. By understanding the unique purposes and functionalities of each commit hook, readers will gain insights into why certain hooks are recommended over others, ultimately aiding in the selection of the most suitable commit hooks for their development workflows.

## Table of Contents

1. [Introduction](#introduction)
2. [Types of Commit Hooks Overview](#types-of-commit-hooks-overview)
   - [Client-Side Commit Hooks](#client-side-commit-hooks)
   - [Server-Side Commit Hooks](#server-side-commit-hooks)
3. [Recommendations for Using Hooks](#recommendations-for-using-hooks)
   - [Pre-Commit Hook](#pre-commit-hook)
   - [Post-Commit Hook](#post-commit-hooks)
4. [Conclusion](#conclusion)
5. [Contact Information](#contact-information)
6. [References](#references)
   
## Introduction
Commit hooks are Git hooks triggered during the commit process to enforce code quality and standards. They check code formatting, validate commit messages, detect sensitive data, run tests, and ensure compliance. Integrating commit hooks helps catch errors early, reduces manual reviews, and maintains code integrity.

## Types of Commit Hooks Overview
![image](https://github.com/user-attachments/assets/e1cf3d43-ac2f-40ed-9410-eb905c3046b1)

### Client-Side Commit Hooks

| Hook Type           | Trigger                                              | Purpose                                                            |
|---------------------|------------------------------------------------------|--------------------------------------------------------------------|
| **Pre-commit**      | Runs before the commit is created.                  | Used for tasks like code formatting checks, linting, or running tests to ensure code quality. |
| **Prepare-commit-msg** | Runs after the pre-commit hook but before the commit message editor opens. | Automatically modifies or pre-populates the commit message (e.g., adding issue numbers or templates). |
| **Commit-msg**      | Runs after the commit message is entered but before the commit is finalized. | Validates the commit message format or content to adhere to specific guidelines or standards. |
| **Post-commit**     | Runs after the commit is successfully created.      | Used for notifications, logging, or triggering external services like CI/CD pipelines. |
| **Pre-push**        | Runs before changes are pushed to the remote repository. | Validates or performs checks (e.g., running tests) before code is pushed to the remote server. |

### Server-Side Commit Hooks

| Hook Type           | Trigger                                              | Purpose                                                            |
|---------------------|------------------------------------------------------|--------------------------------------------------------------------|
| **Pre-receive**     | Runs on the remote server before any updates are applied to the repository. | Ensures that incoming changes meet the repository's policies and standards (e.g., access controls, testing). |
| **Update**          | Runs on the remote server once for each branch that is being updated. | Used to enforce branch-specific checks and controls before accepting the changes. |
| **Post-receive**    | Runs on the remote server after the changes have been successfully received and applied. | Used for notifications, deployment scripts, or triggering further actions such as updating external systems. |

### Recommendations for Using Hooks

1. ### Pre-Commit Hook

**Purpose:** The pre-commit hook runs before the commit is created. It is designed to check the code quality before the commit is finalized.

**Why Choose Pre-commit Hook:**

A pre-commit hook ensures high code quality by running checks like **formatting, linting**, and **basic tests** before a commit. It helps **prevent errors** and **style issues**, provides **immediate feedback** to developers, and ensures that only code meeting quality standards is committed, leading to a cleaner, more reliable codebase.

**Essential pre-commit git hooks:**
| Hook Type           | Purpose                                             | Benefits                                                            |
|---------------------|------------------------------------------------------|--------------------------------------------------------------------|
| Code Formatting     | Automatically format code to adhere to style guidelines. | Ensures consistent code style, reducing formatting errors.|
| Linting         | Check for potential issues or coding errors.| Identifies and fixes potential issues before they are committed.|
|Basic Tests|Execute basic tests to verify code functionality.|Prevents committing code that fails existing tests.|
|Dependency Checks|Ensure all dependencies are properly defined and updated.|Avoids issues related to missing or outdated dependencies.|


2. ### Post-Commit Hook

**Purpose:** The post-commit hook runs after the commit is successfully created. It is used for tasks that are better handled after the commit is finalized.

**Why Choose Post-commit Hook:**

A post-commit hook automates tasks after a successful commit, such as **sending notifications**, **triggering deployment pipelines**, **logging commit details**, and **updating external systems**. It streamlines development,**enhances efficiency**, and **improves team collaboration** by handling tasks that rely on the commit being finalized.

**Essential post-commit git hooks:**
| Hook Type           | Purpose                                             | Benefits                                                            |
|---------------------|------------------------------------------------------|--------------------------------------------------|
| Notifications     | Sends alerts or messages about recent commits to team members.| EKeeps the team informed about changes and updates.|
| Log Management        | Records commit details in logs for auditing and tracking purposes.| Provides historical context and traceability for commits.|
|CI/CD Triggers|Initiates continuous integration or deployment processes.|Automatically builds and deploys code after a commit.|
|Post-commit Actions|Executes additional scripts or tools that require a finalized commit.|Allows for complex actions or integrations post-commit.|

## Conclusion
Implementing pre-commit and post-commit hooks is crucial for maintaining high code quality and efficient development workflows. Pre-commit hooks focus on code formatting, linting, and running tests to ensure that only high-quality code gets committed. Post-commit hooks handle automation tasks such as triggering CI/CD pipelines, sending notifications, and updating external systems.

## Contact Information

| Name| Email Address      |
|-----|--------------------------|
| Raman Tripathi | raman.tripathi.snaatak@mygurukulam.co |

| GitHub | URL |
|----------|---------|
|  Raman-tripathi07  |  https://github.com/Raman-tripathi07 |

## References
For further reading and resources on Commit Hooks, check out the following:

| Links | Descriptions|
|------|---------------------|
|  **Unstop** |https://unstop.com/blog/git-hooks |
| **Medium** |https://tinyurl.com/3822mhpr|
| **Commit Hook detailed doc**|https://tinyurl.com/4xby7m9s|

