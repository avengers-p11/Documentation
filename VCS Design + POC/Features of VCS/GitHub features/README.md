![image](https://github.com/user-attachments/assets/c645eb89-be58-4338-8547-ef0310214aef)

# GitHub Features Documentation

## Author

| Created/Modified | Version | Author               | Comment         | L0 Reviewer      |
|-------------------|---------|----------------------|-----------------|------------------|
| 19-11-2024        | V1     | Anjali Dhiman | L0    |   |


## Table of Contents
1. [Introduction](#introduction)
2. [Key Concept](#key-concept)
     1. [Repositories](#repositories)
     2. [Branches](#branches)
     3. [Pull Request](#pull-requests)
3. [Issues](#issues)
4. [GitHub Actions](#github-actions)
5. [gitignore](#gitignore)
6. [Collaboration Tools](#collaboration-tools)
7. [Conclusion](#conclusion)
8. [Contacts](#contacts)
9. [References](#references)



# Introduction
GitHub is a leading platform for version control and collaboration, built on top of Git, that facilitates efficient project management for developers. It empowers teams to work collaboratively, track changes, and maintain code integrity with features like pull requests, branch protection, and issue tracking. Additionally, it offers powerful tools such as GitHub Actions for automation, GitHub Insights for monitoring project health, and seamless integration with third-party services, making it an indispensable tool for modern software development.

# Key Concept

## Repositories: 
A repository (repo) is a storage space for project files and their version history. It can be:

- **Local Repository**: Stored on your computer.
- **Remote Repository**: Hosted on GitHub or similar platforms.
Repositories can be public (visible to everyone) or private (restricted access).

### Creating a Repository Locally and Pushing to GitHub
**1. Create a Local Repository**:
```
mkdir my-repo
cd my-repo
git init
```
**2. Create a README File**:
```
echo "# My Repository" > README.md
```
**3. Commit Initial Files**:
```
git add .
git commit -m "Initial commit"
```

## Branches: 
Branches in Git allow developers to create separate lines of development within a repository. Each branch is a lightweight pointer to a specific commit, enabling isolated work on features or fixes.
![image](https://github.com/user-attachments/assets/26c3df1b-9219-41f7-b866-aa484f297965)
- **Main Branch** (main or master):
The default branch where the final, stable version of the code resides.

- **Feature Branches**:
Branches are created from the main branch to work on specific features, bug fixes, or tasks without impacting the main codebase.


 Commits are the building blocks of a project’s history, allowing developers to track progress and revert to previous states if needed.
for more details, please go through this link : https://github.com/avengers-p11/Documentation/tree/main/VCS%20Design%20%2B%20POC/Branching%20Strategy/Feature%20Branch

## 2. Creating and Managing Branches

### **Creating a New Branch**

To create a new branch, use the ```git branch``` command followed by the branch name. You can also switch to the new branch immediately using ```git checkout``` or ```git switch```.

```
# Create a new branch
git branch <branch-name>

# Create a new branch and switch to it
git checkout -b <branch-name>

```

### **Switching Between Branches**

To switch between branches, you can use the ```git checkout``` or ```git switch``` command:

```
# Switch to an existing branch
git checkout <branch-name>

```

### **Deleting Branches**

Once a branch is no longer needed, you can delete it to keep your repository clean. This can be done with the ```-d``` (delete) or ```-D``` (force delete) flag.

```
### Delete a branch locally
git branch -d <branch-name>

### Force delete a branch (useful if the branch is not fully merged)
git branch -D <branch-name>

### Delete a branch remotely
git push origin --delete <branch-name>
```

## Pull Requests: 
A pull request (PR) is a feature that allows developers to notify team members that they have completed a feature or a set of changes and would like those changes to be merged into the main branch. The process typically involves:

- **Creating a pull request**: After pushing commits to a branch, a developer creates a PR, summarizing the changes and their purpose.
- **Reviewing**: Team members review the PR, providing feedback, requesting changes, or approving it.
- **Merging**: Once the PR is approved, it can be merged into the main branch, integrating the new changes into the codebase.

Pull requests are a critical part of the collaboration process, enabling code reviews, discussions, and quality control before new code is integrated into the main project.

# Issues 
## Creating and Managing Issues

GitHub Issues is a powerful tool for tracking bugs, enhancements, tasks, and more. Here's how you can create and manage issues effectively:

**Creating an Issue**
1. G**o to the Issues Tab**: Navigate to the repository where you want to create an issue. Click on the "Issues" tab.
2. **Click on "New Issue"**: You'll see a green button labeled "New Issue." Click on it.
3. **Fill Out the Issue Details**:

- **Title**: Provide a concise title for the issue.
- **Description**: Give a detailed description of the issue. You can use Markdown for formatting.
- **Assignees**: Assign the issue to one or more team members by clicking on the "Assignees" section and selecting from the list.
- **Labels**: Add labels to categorize the issue. Click on "Labels" and select relevant ones.
- **Projects**: Link the issue to a project board by selecting the appropriate project.

4. **Submit the Issue**: Once you have filled out all the details, click on the "Submit new issue" button.

# GitHub Actions

GitHub Actions is a tool that helps you automate your project’s workflows, like testing and deployment. It works by defining tasks in YAML files that are triggered by certain events (e.g., pushing code or opening a pull request).
![Screenshot 2024-11-21 130820](https://github.com/user-attachments/assets/225b811c-fd99-478a-b15e-b93474aff022)

## Key Features

| Feature          | Description                                                     |
|------------------|-----------------------------------------------------------------|
| **Automation**    | Automate tasks like code testing, building, and deployment.    |
| **Event-Driven**  | Trigger workflows based on various GitHub events.              |
| **Custom Workflows** | Create customized workflows for different environments and processes. |
| **Extensibility** | Use actions from GitHub’s marketplace or create your own custom actions. |

## gitignore

The ``` .gitignore ``` file is a special file in a Git repository that tells Git which files or directories it should ignore. This means that files listed in the .gitignore file won't be tracked, committed, or pushed to a remote repository. It is commonly used to avoid adding unnecessary or sensitive files to the version control system.

### Why is .gitignore Important?

- **Temporary or System Files**: Files generated by your operating system or tools (e.g., logs, cache files, temp files) are not part of your codebase and don't need to be tracked.
- **Configuration Files**: Files that contain local environment configurations (e.g., API keys, passwords) shouldn’t be shared for security reasons.
- **Build Artifacts**: When you compile or build your project, it generates files (like binaries or compiled code) that should not be tracked because they can be recreated from the source code.

### How Does .gitignore Work?

- **Creating a .gitignore File**: You can create a .gitignore file in the root of your Git repository.
- **Adding Patterns**: In the .gitignore file, you list patterns or file names that you want Git to ignore. These patterns can include specific files, directories, or file types.
- **applying the .gitignore**: After adding patterns to the .gitignore file, Git will stop tracking those files. If the files were already tracked before being added to .gitignore, you'll need to manually remove them from the repository with ``` git rm --cached <file> ```.



# Collaboration Tools

GitHub provides several features to enhance collaboration among developers working on the same project.

**1. Forking and Cloning**
Fork Repositories: Forking allows you to create your own copy of someone else’s repository to experiment with changes before contributing back.
Clone Repositories: Cloning enables you to create a local copy of a repository, allowing you to work on the project offline and push changes back to GitHub.

**2. Branch Protection Rules**
Enforce Standards: Protect your branches by requiring specific checks like code reviews, status checks (CI/CD), or specific approval requirements before merging.
Prevent Force Pushes: Prevent force pushes or deletion of important branches to maintain stability.

# Conclusion
GitHub simplifies software development with version control, collaboration, automation, and security features. It helps manage code through repositories, branching, and pull requests, while GitHub Actions automates testing and deployment. In the OT Microservice project, GitHub is used for efficient code management, and collaboration. It supports continuous integration, tracks tasks, and maintains code stability, making it a key tool for project success.


## Contacts

| Name| Email Address      | GitHub | URL |
|-----|--------------------------|----------|---------|
| Anjali Dhiman | anjali.dhiman.snaatak@mygurukulam.co |  Anjaliopstree  |  https://github.com/Anjaliopstree  |


## References

| Links | Descriptions | 
|--------|------------|
| https://docs.github.com |Official GitHub Documentation  | 
| https://docs.github.com/en/get-started/quickstart/hello-world  | This link provides a quick start guide to GitHub  |
| https://docs.github.com/en/actions | GitHub Actions |
| https://enterprise.github.com | GitHub Enterprise |
| https://github.com/features/codespaces | GitHub Codespaces |



