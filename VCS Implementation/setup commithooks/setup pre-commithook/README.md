# Setup Commit Hooks (pre-commithook)in Git

This guide explains how to set up and configure commit hooks in Git to enforce best practices and automate pre-commit checks.

---

## Table of Contents

1. [Introduction](#introduction)
2. [What Are Commit Hooks?](#what-are-commit-hooks)
3. [Prerequisites](#prerequisites)
4. [Setting Up Commit Hooks](#setting-up-commit-hooks)
    - [Step 1: Locate the Hooks Directory](#step-1-locate-the-hooks-directory)
    - [Step 2: Create a Pre-Commit Hook](#step-2-create-a-pre-commit-hook)
    - [Step 3: Configure the Hook](#step-3-configure-the-hook)
5. [Using Tools for Managing Hooks](#using-tools-for-managing-hooks)
6. [contacts](#contacts)
6. [References](#references)

---

## Introduction

Git hooks are scripts that Git executes before or after certain events, such as committing changes or pushing to a remote repository. These hooks help enforce standards, automate checks, and ensure quality in your workflow.

---

## What Are Commit Hooks?

Commit hooks are part of Git's hook system and are typically used to:
- Validate commit messages.
- Run linting or testing scripts.
- Prevent commits that fail predefined rules.

---

## Prerequisites

- Git installed on your system.
- A local Git repository.
- Basic scripting knowledge (e.g., Bash, Python, or Node.js).

---


## Setting Up Commit Hooks

### Step 1: Locate the Hooks Directory

Navigate to your repository's `.git/hooks` directory:
```bash
cd path/to/your-repo/.git/hooks
```
This directory contains sample hook scripts (e.g., pre-commit.sample, commit-msg.sample).
Step 2: Create a Pre-Commit Hook

### Step 2: Create a new pre-commit file:
```
touch pre-commit
```
![Screenshot from 2024-12-08 21-48-55](https://github.com/user-attachments/assets/d3d78ed2-96ce-43cd-a67c-408f485ed846)


### Step 3: Configure the Hook

Edit the pre-commit file with your preferred script. For example, to enforce code linting:
```
#!/bin/bash
```
# Run linting
```
echo "Running lint checks..."
npm run lint

if [ $? -ne 0 ]; then
    echo "❌ Linting failed. Commit aborted."
    exit 1
fi

echo "✅ Linting passed. Proceeding with commit."
exit 0
```
![Screenshot from 2024-12-08 21-48-24](https://github.com/user-attachments/assets/a58fd405-d029-4767-b9ec-2b6124ba6f0a)

Make the script executable:
```
chmod +x pre-commit
```
![Screenshot from 2024-12-08 21-49-24](https://github.com/user-attachments/assets/04ee8ae3-d93b-430b-9d69-e2d9d07764b3)
![Screenshot from 2024-12-08 12-08-48](https://github.com/user-attachments/assets/e33e82b2-efeb-4d17-b9cb-de5a36af67cb)




## Using Tools for Managing Hooks

Instead of manually managing hooks, you can use tools like:

  Husky: A tool for managing Git hooks in JavaScript/Node.js projects.
  pre-commit: A framework for managing multi-language pre-commit hooks.

### Husky Example

 Install Husky:
```
npm install husky --save-dev
```
 Add a pre-commit hook:
```
npx husky add .husky/pre-commit "npm run lint"
```
Commit the changes:

    git add .husky/pre-commit
    git commit -m "Setup Husky pre-commit hook"
## Contacts

| Name| Email Address      |
|-----|--------------------------|
| Neelesh kumar | nilesh.rajput.snaatak@mygurukulam.co || GitHub | URL |
|----------|---------|
|  devneelesh921  |  https://github.com/devneelesh921  |


## References

| **Topic**                   | **Description**                                                                                       | **Reference Link**                                      |
|-----------------------------|-------------------------------------------------------------------------------------------------------|---------------------------------------------------------|
| **What is Pre-commit?**      | Pre-commit is a framework for managing and maintaining multi-language pre-commit hooks.               | [Pre-commit Official](https://pre-commit.com/)          |
| **Setting up Pre-commit**    | You can configure pre-commit hooks by adding a `.pre-commit-config.yaml` file to your repository.      | [Pre-commit Setup](https://pre-commit.com/#install)     |
| **Common Hooks Examples**    | Pre-commit provides hooks for tasks like linting, formatting, and security checks.                   | [Pre-commit Hooks List](https://pre-commit.com/hooks.html) |

---





