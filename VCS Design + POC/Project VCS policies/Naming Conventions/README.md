# Naming Conventions Documentation

## Author

| Created/Modified | Version | Author               | Comment         | L0 Reviewer      |
|-------------------|---------|----------------------|-----------------|------------------|
| 18-11-2024        | V1     | Anjali Dhiman | L0    |   |


## Table of Contents

- [Introduction](#introduction)
- [Branch Naming Conventions](#branch-naming-conventions)
- [Tag Naming Conventions](#tag-naming-conventions)
- [Commit Message Conventions](#commit-message-conventions)
- [Contacts](#Contacts)
- [References](#references)

## Introduction

This documentation provides a comprehensive guide to the naming conventions for branches, tags, and commit messages used in our project. Adhering to these conventions ensures consistency, clarity, and ease of collaboration across the development team.

## Branch Naming Conventions

Branches are used to encapsulate specific features, fixes, or other workstreams. Consistent branch naming makes it easier to understand the purpose and scope of each branch at a glance.

### General Structure

```
<type>/<ticket-number>-<short-description>
```

### Types

- `feat`: New features
- `fix`: Bug fixes
- `chore`: Maintenance or non-feature updates (e.g., refactoring, dependency updates)
- `docs`: Documentation updates
- `test`: Testing additions or updates
- `hotfix`: Critical fixes that need to be merged immediately

### Examples

- `feat/1234-add-user-login`
- `fix/5678-fix-login-bug`
- `chore/91011-update-dependencies`
- `docs/1213-update-readme`
- `test/1415-add-login-tests`
- `hotfix/1617-fix-critical-login-issue`

## Tag Naming Conventions

Tags are used to mark specific points in the repository's history, such as releases.

### General Structure

```
v<major>.<minor>.<patch>
```
### Examples

- `v1.0.0`: Initial stable release
- `v1.1.0`: New feature added in a backwards-compatible manner
- `v1.1.1`: Bug fix in a backwards

### Commit Message Conventions
Commit messages are crucial for understanding the history and context of changes. A consistent format helps maintain clear project history and facilitates easier code reviews.

### General Structure

```
<type>(<scope>): <subject>
<BLANK LINE>
<body>
<BLANK LINE>
<footer>
```
### Scope
The scope provides additional context about the section of the codebase affected by the change. It should be consistent with the module or component being modified.

### Subject
The subject is a concise summary of the change. It should be:

Written in imperative, present tense: "change" not "changed" or "changes"
No more than 50 characters long
Should not end with a period

### Body
The body should include:

A detailed explanation of what the commit does
The motivation for the change and its context
Any relevant information that helps understand the change

### Footer
The footer should contain any information about breaking changes and references to issues, e.g., "BREAKING CHANGE: type is removed", "Closes #1234".

#### Examples
```
feat(login): add login feature

Implement login functionality using OAuth2. This includes the creation of login page, integration with backend API, and unit tests.

Closes #1234
```

```
fix(auth): fix token refresh logic

Correct the token refresh mechanism to handle expired tokens properly. This ensures the application maintains session state correctly.

Closes #5678
```

```
docs: update contributing guidelines

Add more details about the branching and commit message conventions to the contributing guidelines to help new contributors.

Closes #91011
```

## Benefits of Naming Conventions
Improved collaboration across teams.
Simplified navigation in large repositories.
Consistent CI/CD pipeline configurations.
Enhanced readability and maintainability.


## Conclusion

In conclusion, implementing branch access policies in the OT Microservice project is essential for maintaining code quality, security, and collaboration efficiency. By using GitHub's branch protection rules, you can make sure that important branches like main are only updated through pull requests, with required checks like tests and code reviews. This prevents unauthorized changes and helps keep the codebase clean. Additionally, you can control who has permission to push to these branches, ensuring that only authorized contributors can make updates, leading to a more organized and secure development process.


## Contacts

| Name| Email Address      | GitHub | URL |
|-----|--------------------------|----------|---------|
| Anjali Dhiman | anjali.dhiman.snaatak@mygurukulam.co |  Anjaliopstree  |  https://github.com/Anjaliopstree  |


### References
| Links | Descriptions | 
|--------|------------|
| https://dev.to/shinjithdev/git-good-best-practices-for-branch-naming-and-commit-messages-oj4 | This link explains the naming conventions  | 

