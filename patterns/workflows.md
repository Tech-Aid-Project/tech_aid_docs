# Workflow do GitHub
## This file describes the workflow for contributing to the repository using Git and GitHub.

## The goal is to ensure that all contributors follow a consistent standard when working on the code.

## Sumary

1. [Clone the Repository](#1-clone-the-repository)  
2. [Switch to the dev Branch](#2-switch-to-the-dev-branch)  
3. [Update the Repository](#3-update-the-repository)  
4. [Create a New Branch](#4-create-a-new-branch)  
5. [Make Changes](#5-make-changes)  
6. [Commit the Changes](#6-commit-the-changes)  
7. [Push the Branch to the Remote Repository](#7-push-the-branch-to-the-remote-repository)  
8. [Create a Pull Request (PR)](#8-create-a-pull-request-pr)  
9. [Review and Merge](#9-review-and-merge)  
10. [Update Your Local Branch](#10-update-your-local-branch)  


## 1. Clone the Repository

To get started, clone the repository locally. If you haven't done this yet, run the following command:

```bash
git clone https://github.com/Tech-Aid-Project/repository-name
```

## 2. Switch to the dev Branch

Make sure you are on the `dev` branch, which is the main development branch. The `main` branch is used for production, so only push to it if everything is working without breaking anything!

```bash
git checkout dev
```

## 3. Update the Repository

Before starting any changes, ensure your `dev` branch is up to date with the latest version.

```bash
git pull origin dev
```

## 4. Create a New Branch

Always create a new branch from `dev` for your changes. The branch name should follow the pattern `TechAid-<description>`, where `<description>` briefly describes what will be done. The `TechAid` pattern has been explained in another document.

Example:

```bash
git checkout -b TechAid-<task-description>
```
Note: Replace `<task-description>` with a short and clear description of what you are implementing.

## 5. Make Changes

Make the necessary modifications to the code. Ensure that the changes comply with the project's guidelines.

## 6. Commit the Changes

When the changes are ready, commit them. The commit title should also follow the `TRFAT-<description>` pattern.

Example:

```bash
git add .
git commit -m "TechAid-<task-description> - Clear description of the change made"
```
Note: The commit title should start with `TechAid-` followed by a clear and concise description of the task completed.

## 7. Push the Branch to the Remote Repository

Push your new branch to the remote repository on GitHub.

```bash
git push origin TechAid-<task-description>
```

## 8. Create a Pull Request (PR)

After pushing your branch, go to GitHub and create a Pull Request (PR) for the `dev` branch. When creating the PR, ensure the PR title follows the `TechAid-` pattern.

### Branch Name and PR Title Validation

To ensure both the branch name and the PR title follow the correct format, we have implemented a Python script that validates whether they adhere to the `TechAid-` pattern. If either does not follow the pattern, the process is halted with an error.

## 9. Review and Merge

After the PR is reviewed and approved, it will be merged into the `dev` branch.

## 10. Update Your Local Branch

After the merge, always update your local `dev` branch to keep the repository synchronized:

```bash
git checkout dev
git pull origin dev
```
This ensures you have the latest changes from the repository.

This workflow helps maintain organized code and ensures all developers follow a consistent standard when creating branches and PR titles.

