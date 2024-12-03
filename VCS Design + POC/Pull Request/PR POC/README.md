# **POC of Pull Request in GitHub**

| **Author** | **Created on** | **Version** | **Last updated by** | **Last edited on** | **L0 Reviewer** |
|------------|--------------|------------|-------------|------------|-----------|
| Mohit Saini | 21-11-24 | 1.0 | Mohit Saini | 03-12-24 |Khushi and Shreya |

![image](https://github.com/user-attachments/assets/708172a1-2871-4012-9d98-52ae56692e6d)


# Table of contents

[Introduction](#introduction)

[Purpose](#purpose)

[Pre-requisites](#pre-requisites)

[Workflow Diagram](#workflow-diagram)

[Steps to Create a Pull Request (PR)](#steps-to-create-a-pull-request (PR))

[Conclusion](#conclusion)

[Contact Information](#contact-information)

[References](#references)

# Introduction

Git Pull Request is a feature provided by Git hosting platforms like
GitHub, GitLab, or Bitbucket that enables developers to propose changes
to a codebase. It acts as a request to review and merge changes from one
branch into another, typically from a feature branch into the main
branch.

# Purpose

This document explains how to create a Pull Request (PR) step by step.
It helps you understand why the changes are needed, how to make them
properly, and how these changes will improve the project.

# Pre-requisites 

| Pre-requisite | Description |
|------------------------------------|------------------------------------|
| Git Installed | Make sure Git is installed on your system. |
| GitHub Account | You need an active GitHub account to manage repositories and pull requests. |

# Workflow Diagram

![image](https://github.com/user-attachments/assets/4df6589a-1bf1-4eba-a814-a185db3c371e)


# Steps to Create a Pull Request (PR)

## **Step 1. Create a Repository on GitHub**

**Log in to GitHub**

Go to Repositories and click New.

 Enter a name for your repository, choose public or private, and add a description if you want.

Click Create Repository to set it up.

![image](https://github.com/user-attachments/assets/769cc267-ab26-4ef4-98f0-1945be97d207)


## **Step 2. Clone the repository to your local system**

```
git clone https://github.com/mohitsainin/PR-demo.git
```

![image](https://github.com/user-attachments/assets/c22fd581-d305-4e3b-b347-37ccd3096598)

## **Step 3. Change into the project directory**

```
cd PR-demo
```
![image](https://github.com/user-attachments/assets/6c845481-dfcc-49b0-a0c0-09395d1f0153)

## **Step 4. Create a new branch for your changes**

```
git checkout -b new_branch
```
![image](https://github.com/user-attachments/assets/41c19995-f6de-4b9a-acea-14a55da5bb19)


## **Step 5. View all branches in your repository**

```
git branch
```
![image](https://github.com/user-attachments/assets/d3623a3d-bf45-4277-8c3a-a648a9e18c07)


## **Step 6. Edit the project file**

```
vi pr(file name)
```
![image](https://github.com/user-attachments/assets/f779d15b-9c32-4f73-8abd-389f844fea81)


## **Step 7. Check the changes you made**

```
git status
```
![image](https://github.com/user-attachments/assets/32c2d456-9b60-4637-8792-19b92e2bfc2a)

## **Step 8. Stage your changes**

```
git add \<file name\>
```
![image](https://github.com/user-attachments/assets/43f97c46-57f7-4e08-a033-203aa0c9fbdb)


## **Step 9. Commit the changes with a message**

```
git commit -m "message of change file"
```
![image](https://github.com/user-attachments/assets/f7088151-c591-41ea-bb4f-f08358f2b151)

## **Step 10. Push your code to GitHub**

```
git push --set-upstream origin new_branch
```
![image](https://github.com/user-attachments/assets/e1b0e668-afe2-4b13-b863-eaf5a49316c4)

## **Step 11. Navigate to your GitHub repository to view the new branch**

![image](https://github.com/user-attachments/assets/ba876aa4-d47a-4d32-be0f-710e1200ec09)


## **Step 12. Access the "Pull Requests" section and initiate a new pull request**
![image](https://github.com/user-attachments/assets/899b8f26-146d-4413-90f3-00b6e9036bfc)


## **Step 13. Select the branch you wish to merge with the base branch**

![image](https://github.com/user-attachments/assets/a9625890-84c3-415c-8566-071f819fb1d5)


## **Step 14. Submit the pull request, providing a title and any necessary comments**
![image](https://github.com/user-attachments/assets/0caab22f-c68c-4aa1-804e-66c872da00d6)


## **Step 15. Review for merge conflicts after submission, and ensure it’s ready for review**

![image](https://github.com/user-attachments/assets/f6dc4dbf-a2cb-46b8-bd0f-7043f8d60135)


## **Step 16. Engage in the review process, leaving comments as needed**

![image](https://github.com/user-attachments/assets/628f6726-6411-4549-965a-af123505a511)


## **Step 17. Once the review is complete, merge the pull request**


![image](https://github.com/user-attachments/assets/97c87329-363f-4939-b515-e1dadbb4e824)

## **Step 18. If the branch is no longer required, delete it after merging the changes**

![image](https://github.com/user-attachments/assets/fc989c5d-c8e7-4560-ad27-5af4f85186d2)


# Conclusion
Pull Requests (PRs) are an important tool for teamwork in coding. They let you share your changes, get feedback, and merge them into the main code easily. This guide gives simple steps to help you create a PR, even if you’re new to it. By using these steps, you can work smoothly with others, keep your code organized, and improve your project together.

# Contact Information

| **Name**    | **Email address**         |
|-------------|---------------------------|
| Mohit Saini | <it.mohitsaini@gmail.com> |

# References

| **Link** | **Description** |
|----------------------------------------------------|--------------------|
| <https://www.pagerduty.com/resources/learn/what-is-a-pull-request/> | Pull Request |
| <https://opensource.com/article/19/7/create-pull-request-github> | How create Pull Request |
