# Setting Up Authorization in Version Control System (VCS)


| **Author** | **Created on** | **Last updated by** | **Last edited on** | **Reviwer L0** |**Reviwer L1** |**Reviwer L2** |
|------------|----------------|----------------------|---------------------|---------------|---------------|---------------|
| Neelesh kumar      | 29-11-24      | Neelesh  Kumar             | 29-11-24           |  | | |     

This guide explains how to set up authorization for a Version Control System (VCS) to control access to repositories, branches, and specific actions like pull requests and merges.

---

## Table of Contents

1. [Introduction](#introduction)
2. [Prerequisites](#prerequisites)
3. [Authorization Setup](#authorization-setup)
    - [Step 1: Define Access Policies](#step-1-define-access-policies)
    - [Step 2: Configure Role-Based Access Control (RBAC)](#step-2-configure-role-based-access-control-rbac)
    - [Step 3: Protect Branches](#step-3-protect-branches)
    - [Step 4: Monitor and Audit Permissions](#step-4-monitor-and-audit-permissions)
4. [Best Practices](#best-practices)
5. [Troubleshooting](#troubleshooting)
6. [References](#references)

---

## Introduction

Authorization in a VCS ensures that only authorized users or roles can access and modify repositories or branches. This is critical for maintaining code integrity and implementing secure development practices.

---

## Prerequisites

1. A working VCS (e.g., GitHub, GitLab, Bitbucket, etc.).
2. Admin or Owner access to your repositories.
3. A defined set of user roles and permissions.

---

## Authorization Setup

### Step 1: Define Access Policies

Identify the access levels required for your users and teams:
- **Admin:** Full access to repositories, branches, and settings.
- **Developer:** Can push to feature branches but requires approval for merges.
- **Reviewer:** Can review pull requests but cannot push code.
- **Read-Only:** Can only view code but cannot make changes.

---

### Step 2: Configure Role-Based Access Control (RBAC)

Use your VCS's built-in RBAC to assign roles and permissions.

#### GitHub:
1. Navigate to **Settings** > **Manage Access** for your repository.
2. Assign roles:
   - Admin
   - Maintainer
   - Write
   - Read

#### GitLab:
1. Navigate to **Settings** > **Members**.
2. Add users or groups and assign roles:
   - Owner
   - Developer
   - Reporter
   - Guest

#### Bitbucket:
1. Go to **Repository Settings** > **User and Group Access**.
2. Assign permissions:
   - Admin
   - Write
   - Read

---

### Step 3: Protect Branches

Set up branch protection rules to enforce authorization policies.

#### GitHub:
1. Go to **Settings** > **Branches** > **Branch Protection Rules**.
2. Configure rules:
   - Require pull request reviews before merging.
   - Restrict who can push to the branch.
   - Require status checks to pass before merging.

#### GitLab:
1. Navigate to **Settings** > **Repository** > **Protected Branches**.
2. Protect branches:
   - Set roles allowed to push and merge.
   - Require approvals.

#### Bitbucket:
1. Go to **Repository Settings** > **Branch Permissions**.
2. Add permissions:
   - Restrict push to specific branches.
   - Require pull request approval.

---

### Step 4: Monitor and Audit Permissions

1. Regularly review user and group permissions.
2. Use audit logs provided by your VCS to track changes and unauthorized access attempts.

#### GitHub Audit Logs:
Access logs from your **organization settings** to monitor changes.

#### GitLab Audit Events:
Navigate to **Admin Area** > **Audit Events** to track activities.

#### Bitbucket Audit Logs:
View activity logs in the **Workspace Settings**.

---

## Best Practices

- **Enforce Least Privilege:** Assign the minimum permissions required for each role.
- **Enable Two-Factor Authentication (2FA):** Ensure all users have 2FA enabled for added security.
- **Use Groups:** Manage permissions via user groups instead of individual users.
- **Enable Code Owners:** Automatically request reviews from designated users for specific files or directories.
- **Periodic Audits:** Regularly review and update permissions.

---

## Troubleshooting

- **Issue:** A user cannot push to a branch.  
  **Solution:** Check if the branch is protected or if the user lacks appropriate permissions.

- **Issue:** Unauthorized commits to the main branch.  
  **Solution:** Enable branch protection rules to restrict direct pushes.

- **Issue:** Users cannot access the repository.  
  **Solution:** Verify their assigned role and ensure they are part of the repository or group.

---
## Contacts

| Name| Email Address      |
|-----|--------------------------|
| Neelesh kumar | nilesh.rajput.snaatak@mygurukulam.co || GitHub | URL |
|----------|---------|
|  devneelesh921  |  https://github.com/devneelesh921  |



## References

- [GitHub Branch Protection Rules](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/defining-the-mergeability-of-pull-requests/about-protected-branches)
- [GitLab Protected Branches](https://docs.gitlab.com/ee/user/project/protected_branches.html)
- [Bitbucket Branch Permissions](https://support.atlassian.com/bitbucket-cloud/docs/enforce-branch-permissions/)

---
