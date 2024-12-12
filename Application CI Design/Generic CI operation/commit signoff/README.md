# Commit Signoff in CI: Detailed Documentation and POC

This document provides comprehensive guidance on implementing a **commit signoff** process as part of your CI workflow. Commit signoff ensures that contributors affirm their compliance with the project’s contribution guidelines.

| **Author** | **Created on** | **Last updated by** | **Last edited on** | **Reviwer L0** |**Reviwer L1** |**Reviwer L2** |
|------------|----------------|----------------------|---------------------|---------------|---------------|---------------|
| Neelesh kumar      | 29-11-24      | Neelesh  Kumar             | 29-11-24           |  | | | 
---

## Table of Contents

1. [Introduction](#introduction)
2. [What is Commit Signoff?](#what-is-commit-signoff)
3. [Why Use Commit Signoff?](#why-use-commit-signoff)
4. [Prerequisites](#prerequisites)
5. [Setup Instructions](#setup-instructions)
    - [Step 1: Enable Signed Commits](#step-1-enable-signed-commits)
    - [Step 2: Add Signoff Validation to CI](#step-2-add-signoff-validation-to-ci)
6. [Proof of Concept (POC)](#proof-of-concept-poc)
7. [Best Practices](#best-practices)
8. [contacts](#contacts)
9. [References](#references)

---

## Introduction

Commit sign-off is a way to certify that you adhere to the rules and guidelines of the project you are contributing to. By signing off on your commits, you acknowledge that you have the right to submit the work under the project's license.

This mechanism is commonly used in open-source projects to ensure compliance with licensing requirements, such as the **Developer Certificate of Origin (DCO)**.

---

## What is Commit Signoff?

A commit sign-off is a line at the end of the commit message that follows this format:

```
Signed-off-by: Your Name <your.email@example.com>
```

This line can be added automatically using the `--signoff` (`-s`) flag when creating a commit.

The sign-off indicates:
- You wrote the patch or have the right to submit it under the open-source license.
- You comply with the Developer Certificate of Origin (DCO).


## Why Use Commit Signoff?

1. **Licensing Compliance**: Ensures contributions are made with an agreement to the licensing terms.
2. **Accountability**: Tracks the authorship and approval of changes.
3. **Transparency**: Facilitates better project governance by documenting consent for contributions.

---

## Prerequisites

1. A Git-based repository.
2. Continuous Integration (CI) setup using tools like GitHub Actions, GitLab CI, Jenkins, or CircleCI.
3. Basic understanding of Git hooks.

---

## Setup Instructions

### Step 1: Enable Signed Commits

To sign off on a commit, use the `-s` flag in your Git commit command:
```bash
git commit -s -m "Your commit message"
```
This appends the Signed-off-by line automatically, using the name and email in your Git configuration:
```
Signed-off-by: Your Name <your.email@example.com>
```
### Step 2: Add Signoff Validation to CI
Example: GitHub Actions

   Create a CI Workflow File: Add a .github/workflows/validate-signoff.yml file to your repository:
```   
name: Validate Commit Signoff

on:
  pull_request:

jobs:
  validate-signoff:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout Repository
        uses: actions/checkout@v3

      - name: Validate Commit Signoff
        run: |
          for commit in $(git rev-list HEAD ^$(git merge-base HEAD main)); do
            if ! git log -n 1 --pretty=format:"%B" $commit | grep -q "Signed-off-by:"; then
              echo "❌ Commit $commit is missing a Signed-off-by line."
              exit 1
            fi
          done
          echo "✅ All commits have a Signed-off-by line."
```
    Trigger Workflow: This workflow will trigger on every pull request and validate that all commits include a Signed-off-by line.

## Proof of Concept (POC)
Step 1: Create a Repository

  Initialize a Git repository:
```
git init commit-signoff-demo
cd commit-signoff-demo
```
Create a sample file and make a commit:
```
    echo "Hello, World!" > sample.txt
    git add sample.txt
    git commit -s -m "Initial commit"
```
Step 2: Configure the CI Workflow

   Add the validate-signoff.yml workflow file to .github/workflows/.
   Push the changes to a remote repository:
```
    git remote add origin <your-repo-url>
    git push -u origin main
```
Step 3: Create a Pull Request

   Make a change and commit it without the -s flag.
   Open a pull request and observe the CI pipeline fail due to a missing Signed-off-by line.

## Best Practices

 1. Always sign off your commits to maintain compliance with licensing requirements.
 2. Use tools like the DCO app or pre-commit hooks to enforce sign-off policies.
 3. Double-check your commit messages to ensure proper formatting and sign-off inclusion.

---


## Contacts

| Name| Email Address      |
|-----|--------------------------|
| Neelesh kumar | nilesh.rajput.snaatak@mygurukulam.co || GitHub | URL |
|----------|---------|
|  devneelesh921  |  https://github.com/devneelesh921  |

## References

-----------------------------------------------------

