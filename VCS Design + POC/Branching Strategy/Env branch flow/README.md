# Environment Branch Flow

## Author

| Created/Modified | Version | Author               | Comment         | L0 Reviewer      |L1 Reviewer | L2 Reviewer |
|-------------------|---------|----------------------|-----------------|------------------|------------------|------------------|
| 21-11-2024        | V1     | Anjali Dhiman | L0    |  Khushi Malhotra |    |    |

## Table of content 
- [Introduction](#introduction)
- [Why use Environment Branching](#why-use-environment-branching)
- [Types of Environment Branches](#types-of-environment-branches)
- [Environment Branch Flow](#environment-branch-flow)
- [Advantages](#advantages)
- [Disadvantages](#disadvantages)
- [Conclusion](#conclusion)
- [Contact Information ](#contact-information )
- [References](#references)


# Introduction

Environment Branch Flow is a structured branching strategy in Git that helps manage code changes across multiple environments, ensuring seamless development, testing, and deployment. This approach supports collaboration while maintaining stability in critical environments like production.

---

## Why use Environment branching

Environment branching simplifies code management by isolating changes for development, staging, and production environments. This approach ensures that only thoroughly tested and approved code is deployed to production, reducing risks and enhancing deployment quality. By maintaining separate branches for each environment, teams can streamline workflows, improve collaboration between development and QA teams, and ensure reliable and consistent releases.

---



![image](https://github.com/user-attachments/assets/f8290664-d580-4945-a2c1-87ab006d86f1)
### This diagram shows a typical Git branching workflow:
**Workflow**:
- Developers work on the developer branch.
- Once changes are ready, they are tested in the Testing branch.
- After testing, changes are merged into the main branch for release.
  
## Types of Environment Branches
| **Branch**          | **Purpose**                                    | **Naming**                  | **Workflow**                                                                                          |
|---------------------|------------------------------------------------|-----------------------------|-------------------------------------------------------------------------------------------------------|
| **Development Branch** | Central branch for active development.       | `develop` or `dev`           | Feature branches are merged here after completion and review.                                          |
| **Feature Branches**  | Isolated branches for new features or bug fixes. | `feature/<feature-name>` (e.g., `feature/login-system`) | Created from `develop` and merged back after review. [Link to more details](https://github.com/avengers-p11/Documentation/blob/main/VCS%20Design%20%2B%20POC/Branching%20Strategy/Feature%20Branch/README.md) |
| **Staging Branch**    | Pre-production testing environment.           | `staging`                    | Code from `develop` is merged for QA testing and reviews.                                              |
| **Release Branch**    | Stabilization and final prep for deployment.  | `release/<version>` (e.g., `release/v1.0.0`) | Bug fixes are finalized, then merged into `main` and `develop`.                                        |

## Environment Branch Flow

1. **Development**:
   - Active development occurs on the `develop` branch.
   - Feature branches are created from `develop` for new features or bug fixes.

2. **Testing in Staging**:
   - Merge `develop` into `staging` for testing.
   - Perform QA and stakeholder reviews to ensure the code is stable and meets requirements.

3. **Preparing for Release**:
   - Create a `release/<version>` branch from `staging` for final preparation.
   - Perform final bug fixes, quality checks, and documentation updates in the `release` branch.
   - Once ready, merge the `release` branch into both `main` (for production) and `develop` (to ensure any changes are captured in future development).
---

## Branch Naming Conventions

| **Branch Type**  | **Naming Pattern**            | **Example**                    |
|-------------------|-------------------------------|---------------------------------|
| Main              | `main`                       | `main`                         |
| Development       | `develop` or `dev`           | `develop`                      |
| Feature           | `feature/<feature-name>`     | `feature/user-authentication`  |
| Staging           | `staging`                    | `staging`                      |
| Release           | `release/<version>`          | `release/v1.0.0`               |

---

## Benefits

1. **Isolation**: Ensures active development does not impact production stability.
2. **Quality Assurance**: Enables thorough testing in staging and release branches.
3. **Scalability**: Supports multiple developers working on different features.
4. **Transparency**: Provides clear visibility into the flow of code changes.

---

## Best Practices

1. Always follow the branch naming conventions.
2. Protect critical branches (`main`, `staging`) with access rules and pull request reviews.
3. Keep feature branches short-lived to minimize merge conflicts.
4. Use CI/CD pipelines to automate testing and deployment workflows.

---

## Advantages
| **Advantage**            | **Description**                                                    |
|--------------------------|--------------------------------------------------------------------|
| **Isolation**             | Ensures active development does not impact production stability.  |
| **Scalability**           | Supports multiple developers working on different features.      |
| **Improved Code Quality** | Early detection and fixing of bugs.                               |
| **Organized Releases**    | Systematic and less error-prone deployment process.               |
| **Efficient Team Work**   | Teams can work on different features without stepping on each other's toes. |
| **Risk Reduction**        | Isolating changes helps prevent issues in the live environment.    |

## Disadvantages
| **Disadvantage**          | **Description**                                                    |
|--------------------------|--------------------------------------------------------------------|
| **Complexity**            | Managing multiple branches can be tricky.                         |
| **Merge Conflicts**       | Combining different branches can lead to conflicts that need resolving. |
| **Resource Intensive**    | Requires more resources for managing and testing various environments. |
| **Potential Delays**      | More stages can slow down the release process.                    |

## Conclusion
Environment branching is a great way to manage software development, testing, and deployment. It helps maintain code quality and reduces risks, though it does come with some complexity. Understanding the flow and types of branches can help teams use this strategy effectively.

## Contacts

| Name| Email Address      | GitHub | URL |
|-----|--------------------------|----------|---------|
| Anjali Dhiman | anjali.dhiman.snaatak@mygurukulam.co |  Anjaliopstree  |  https://github.com/Anjaliopstree  |

## References 
|Links|Description|
|------|-----------|
| https://matiascreimerman.neocities.org/blogposts/creimerman/matias/methodology/environment-based-branching-strategy-branching-by-environment| Environment Branch Flow|
| https://www.abtasty.com/blog/git-branching-strategies/ | Different Branching Strategy|

