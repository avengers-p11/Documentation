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


## Types of Environment Branches
![image](https://github.com/user-attachments/assets/f8290664-d580-4945-a2c1-87ab006d86f1)

### 1. Development Branch
- **Purpose**: Central branch for active development.
- **Naming**: `develop` or `dev`
- **Workflow**: Feature branches are merged here after completion and review.

### 2. Feature Branches
- **Purpose**: Isolated branches for new features or bug fixes.
- **Naming**: `feature/<feature-name>` (e.g., `feature/login-system`)
- **Workflow**: Created from `develop` and merged back after review.

### 3. Staging Branch
- **Purpose**: Pre-production testing environment.
- **Naming**: `staging`
- **Workflow**: Code from `develop` is merged for QA testing and reviews.

### 4. Release Branch
- **Purpose**: Stabilization and final prep for deployment.
- **Naming**: `release/<version>` (e.g., `release/v1.0.0`)
- **Workflow**: Bug fixes are finalized, then merged into `main` and `develop`.

### 5. Main Branch
- **Purpose**: Contains the live, stable production code.
- **Naming**: `main` or `master`
- **Workflow**: Code from `release` branches is merged; direct changes are restricted.
---

## Environment Branch Flow

1. **Feature Development**:
   - Create a `feature/<name>` branch from `develop`.
   - Complete development and testing in the feature branch.
   - Merge into `develop` after approval.

2. **Testing in Staging**:
   - Merge `develop` into `staging` for testing.
   - Perform QA and stakeholder reviews.

3. **Preparing for Release**:
   - Create a `release/<version>` branch from `staging`.
   - Perform final bug fixes and documentation updates.
   - Merge `release` into `main` and `develop`.

4. **Production Deployment**:
   - Deploy the `main` branch to the production environment.

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
|Advantage|Description|
|---------|-----------|
|Improved Code Quality|Early detection and fixing of bugs.|
|Organized Releases| Systematic and less error-prone deployment process.|
|Efficient Team Work|Teams can work on different features without stepping on each other's toes.|
|Risk Reduction| Isolating changes helps prevent issues in the live environment.|

## Disadvantages
|Disadvantages|Description|
|-------------|-----------|
|Complexity| Managing multiple branches can be tricky.|
|Merge Conflicts|Combining different branches can lead to conflicts that need resolving.|
|Resource Intensive|Requires more resources for managing and testing various environments.|
|Potential Delays|More stages can slow down the release process.|

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

