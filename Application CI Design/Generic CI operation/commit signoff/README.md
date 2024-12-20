# Commit Signoff : Detailed Documentation and POC

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
5. [Proof of Concept (POC)](#proof-of-concept-poc)
6. [Best Practices](#best-practices)
7. [contacts](#contacts)
8. [References](#references)

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

 
## Proof of Concept (POC)
### 1.Set Up Git Config (if not done already):
```
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
```
### 2.Commit with Sign-Off:
When making a commit, you can use the --signoff flag to add a "Signed-off-by" line to your commit message.
```
git commit --signoff -m "Your commit message"
```
### 3.check the commit
use git log to check
```
git log
```
### 4.Push Your Commit:
push the commit to your repo
```
git push origin main
```
![Screenshot from 2024-12-20 23-29-27](https://github.com/user-attachments/assets/c58adbe1-f28b-4cbf-a7a5-300626875b00)
![Screenshot from 2024-12-20 23-30-14](https://github.com/user-attachments/assets/e5cf6cca-bc8f-4cfc-abb1-d7f8753ebff0)

## Best Practices


| Practice                                      | Description                                                                 |
|-----------------------------------------------|-----------------------------------------------------------------------------|
| **Always use `--signoff` flag**               | Use the `git commit --signoff` option to automatically add a "Signed-off-by" line to your commits. |
| **Use your real name and email address**      | Ensure that the name and email used in your commits are accurate and match your Git configuration. |
| **Don't sign off on behalf of others**        | Only sign off on commits you’ve personally authored, as it indicates agreement with the contribution terms. |
| **Review your commit history**                | Regularly check your commit messages to verify that the "Signed-off-by" line is included, especially before pushing. |
| **Follow contribution guidelines**            | Always review the project's contribution guidelines and make sure to follow them while contributing. |
    

---


## Contacts

| Name| Email Address      |
|-----|--------------------------|
| Neelesh kumar | nilesh.rajput.snaatak@mygurukulam.co || GitHub | URL |
|----------|---------|
|  devneelesh921  |  https://github.com/devneelesh921  |

## References

| Resource                                  | Link                                                       |
|-------------------------------------------|------------------------------------------------------------|
| Developer Certificate of Origin (DCO)     | [https://developercertificate.org/](https://developercertificate.org/) |
| Git Commit Documentation                  | [https://git-scm.com/docs/git-commit](https://git-scm.com/docs/git-commit) |
| Why Signed Commits Matter                 | [https://www.contributor-covenant.org/](https://www.contributor-covenant.org/) |
| GitHub's Commit Signing Guide             | [https://docs.github.com/en/authentication/managing-commit-signature-verification](https://docs.github.com/en/authentication/managing-commit-signature-verification) |

-----------------------------------------------------

