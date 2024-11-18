# Branch access policies

## Author

| Created/Modified | Version | Author               | Comment         | L0 Reviewer      |
|-------------------|---------|----------------------|-----------------|------------------|
| 18-11-2024        | V1     | Anjali Dhiman | L2 Feedbacks    |  Khushi Malhotra |
## Table of Contents

- [Introduction](#introduction)
- [Branch Protection Rules](#branch-protection-rules)
  - [Few reasons why Branch Protection Rules are Important](#few-reasons-why-branch-protection-rules-are-important)
  - [Protection rules available](#protection-rules-available)
- [Creating Branch Protection Rules](#creating-branch-protection-rules)
- [Access permissions](#access-permissions)
  - [Types of Github Account](#types-of-github-account)
- [Roles in an organization](#roles-in-an-organisation)
  - [Roles available for an organization repository](#roles-available-for-an-organization-repository)
- [Creating a repository role](#creating-a-repository-role)
- [Conclusion](#conclusion)
- [Contacts](#contacts)
- [References](#references)

***
![image](https://github.com/user-attachments/assets/ca27d2e0-930a-49d3-8ff9-542ebc2aea36)

## Introduction

Branch access policies in Git, used on platforms like GitHub, GitLab, or Bitbucket, are rules that control how and when changes can be made to branches in a repository. These policies help ensure that important branches, like the main or production branches, are protected from unauthorized changes. They can require code reviews, enforce certain checks, and prevent direct edits to sensitive branches, promoting better code quality and team collaboration.
***

## Branch Protection Rules
Git branch protection rules are essential security configurations that allow repository administrators to enforce policies to safeguard branches. These rules prevent unauthorized users from making changes or accidentally deleting important branches, such as the main or production branch.

### Few reasons why Branch Protection Rules are Important

| Reasons  | 
|----------|
| They stop accidental or unapproved code commits to important branches. |
| They make sure code is reviewed before being merged, ensuring better quality and collaboration. |
| These rules help prevent errors from untested or unreviewed code, keeping the project in good shape. |
| They prevent force pushes that could overwrite important commit history, keeping the project organized.  |

### Protection rules available
| Rules  | Description |
|----------|----------|
| **Require a pull request before merging** | When enabled, all commits must be made to a non-protected branch and submitted via a pull request before they can be merged into a branch that matches this rule. |
| **Require branches to be up to date before merging** | Each commit will have a status defined for it. Namely, error, failure, pending, success. Enable this option, if you want the status checks to be in success state before merging the commits into the protected branches.  |
| **Require conversation resolution before merging** | When enabled, all conversations on code must be resolved before a pull request can be merged into a branch that matches this rule. |
| **Require signed commits** |  Enable this option, if you want verified signatures on the commits pushed to this branch. |
| **Require linear history** | Prevent merge commits from being pushed to matching branches. Prevents collaborators from pushing merge commits to the branch. |
| **Lock branch** | Branch become read-only. Users cannot push to the branch. Locked branches can also not be deleted. |
***

## Creating Branch Protection Rules
### 1. Navigate to your repository homepage at Github. Then click on the Settings Option
  
![Screenshot 2024-11-15 175827](https://github.com/user-attachments/assets/ccf7c453-7c31-4b43-a556-24133f6475d3)


### 2. In the "Code and automation" section of the sidebar, click  Branches

![Screenshot 2024-11-15 180111](https://github.com/user-attachments/assets/d7a71cfd-a1e5-4443-8913-1fa61bfec7fa)

### 3. Next to "Branch protection rules", click Add rule
   
![Screenshot 2024-11-15 180154](https://github.com/user-attachments/assets/6cef9575-400b-4c35-92a2-faf88f960a85)

  
### 4. Under "Branch name pattern", type the branch name or pattern you want to protect

![Screenshot 2024-11-15 180238](https://github.com/user-attachments/assets/1263dd71-1c12-4c11-ad29-a59378fab356)


### 5. Select the protection rules for your branch and then click on create
***

## Access permissions
To perform actions on GitHub, such as creating pull requests or changing billing settings, a person must have sufficient access, controlled by permissions. Permissions define the ability to perform specific actions (e.g., deleting an issue). A role is a set of permissions assigned to individuals or teams.

With roles, you can control who has access to your accounts and resources on GitHub and the level of access each person has. Roles work differently for different types of accounts. For more information about accounts, see "[Types of GitHub accounts](https://docs.github.com/en/enterprise-cloud@latest/organizations/managing-user-access-to-your-organizations-repositories/managing-repository-roles/about-custom-repository-roles)."

### Types of Github Account
There are three types of accounts on GitHub.

| Type | Description   |
|-----|--------------------------|
| [Personal accounts](https://docs.github.com/en/account-and-profile/setting-up-and-managing-your-personal-account-on-github/managing-user-account-settings/permission-levels-for-a-personal-account-repository) | A repository owned by a personal account has two permission levels: the repository owner and collaborators |
| [Organization accounts](https://docs.github.com/en/organizations/managing-user-access-to-your-organizations-repositories/managing-repository-roles/repository-roles-for-an-organization) | Organization owners can assign roles to individuals and teams giving them different sets of permissions in the organization. |
| [Enterprise accounts](https://docs.github.com/en/enterprise-cloud@latest/admin/managing-your-enterprise-account/about-enterprise-accounts) | GitHub Enterprise Cloud and GitHub Enterprise Server offer enterprise accounts for centralized management of policy, billing, and promoting innersourcing across multiple organizations. |
***

## Roles in an organization
Organization owners can assign roles to individuals and teams giving them different sets of permissions in the organization. You can give organization members, outside collaborators, and teams of people different levels of access to repositories owned by an organization by assigning them to roles. Choose the role that best fits each person or team's function in your project without giving people more access to the project than they need.

### Roles available for an organization repository
| Type of role| Description |
|-----|--------------------------|
| Read | Recommended for non-code contributors who want to view or discuss your project |
| Write | Recommended for contributors who actively push to your project |
| Maintain | Recommended for project managers who need to manage the repository without access to sensitive or destructive actions. | 
| Triage | Recommended for contributors who need to manage issues, discussions, and pull requests but don't have write access. |
| Admin | Recommended for people who need full access to the project, including sensitive and destructive actions like managing security or deleting a repository |
| Custom roles | Only organizations that use GitHub Enterprise Cloud can create custom repository roles. |

***

## Creating a repository role
- In the upper-right corner of GitHub, select your profile photo, then click  Your Organizations.

![Screenshot 2024-11-18 134347](https://github.com/user-attachments/assets/8d2d446e-d76b-4d3b-8f54-5c7219c07986)


- Under "Organizations", next to the name of your organization, click Settings.

![Screenshot 2024-11-18 134412](https://github.com/user-attachments/assets/b6b96018-9559-4284-8a0a-a7a4ea42f72c)


- In the "Access" section of the sidebar, click  Repository roles.

![Screenshot 2024-11-18 135631](https://github.com/user-attachments/assets/6fa5b7d3-c1c5-4dd0-83e6-b9f86caf4847)


- Scroll to the "Custom roles" section, then click Create a Role. Fill out all the details and then click on Create Role.

![Screenshot 2024-11-18 140056](https://github.com/user-attachments/assets/e9a9be12-4c7b-4885-bc60-f6c54fcf6357)

- After the create, we see this page 

![Screenshot 2024-11-18 140107](https://github.com/user-attachments/assets/62887950-6629-44ee-b8cf-087983382630)


***
## Conclusion

In conclusion, implementing branch access policies in the OT Microservice project is essential for maintaining code quality, security, and collaboration efficiency. By using GitHub's branch protection rules, you can make sure that important branches like main are only updated through pull requests, with required checks like tests and code reviews. This prevents unauthorized changes and helps keep the codebase clean. Additionally, you can control who has permission to push to these branches, ensuring that only authorized contributors can make updates, leading to a more organized and secure development process.

***

## Contacts

| Name| Email Address      | GitHub | URL |
|-----|--------------------------|----------|---------|
| Anjali Dhiman | anjali.dhiman.snaatak@mygurukulam.co |  Anjaliopstree  |  https://github.com/Anjaliopstree  |






## References

| Links | Description      |
|-----  |--------------------------|
| https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-protected-branches | About protected branches |
| https://spectralops.io/blog/how-to-set-up-git-branch-protection-rules/ | How to set up Git branch protection rules |
| https://docs.github.com/en/organizations/managing-peoples-access-to-your-organization-with-roles/roles-in-an-organization | Roles in an organisation |

