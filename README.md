# Git & GitHub Reference Guide

By: supersimple.dev  
Tutorial: [YouTube Video](https://www.youtube.com/watch?v=hrTQipWp6co)

---

## **Command Line Basics**

- **`ls`**: List files and folders in the current directory.
- **`cd ~/Desktop/folder`**: Change to a specific directory.
  
> **Note:** Git commands must be run inside the folder that contains your code.

---

## **Creating Commits**

- **`git init`**: Start tracking changes in the current folder.
- **`git status`**: Show changes since the last commit.
- **`git add <file|folder>`**: Stage changes for the next commit.
  - `git add file`: Stage a single file.
  - `git add folder/`: Stage all files in a folder.
  - `git add .`: Stage all changes.
- **`git commit -m "message"`**: Commit staged changes with a message.
- **`git commit -m "message" --amend`**: Modify the last commit instead of creating a new one.
- **`git log`**: View commit history.
  - `git log --all`: Show all commits.
  - `git log --all --graph`: Visualize branches in the terminal.

---

## **Configuring Git**

- **Set Name and Email**
  ```bash
  git config --global user.name "Your Name"
  git config --global user.email "email@example.com"
  ```
- **Alias Commands**
  ```bash
  git config --global alias.<shortcut> <command>
  ```
  Example: `git config --global alias.s "status"`  
  Now, `git s` = `git status`

---

## **Working with Changes**

1. **Areas**:
   - **Working Area**: Unstaged changes.
   - **Staging Area**: Staged changes ready to be committed.

2. **Commands**:
   - **Stage Changes**: `git add .`
   - **Commit Changes**: `git commit -m "message"`
   - **Unstage Changes**: `git reset <file|folder>`
   - **Discard Changes**: `git checkout -- <file|folder>`

---

## **Viewing and Restoring Commits**

- **View a Previous Commit**
  ```bash
  git checkout <commit_hash|branch_name>
  ```
- **Restore Files to a Previous Commit**
  ```bash
  git checkout <hash|branch> <file|folder>
  ```

---

## **GitHub Basics**

- **Repositories**:
  - Local Repository: Git repository on your computer.
  - Remote Repository: Git repository hosted online (e.g., GitHub).

- **Link a Local Repository to GitHub**
  ```bash
  git remote add origin <repository_url>
  ```

- **Push Code to GitHub**
  ```bash
  git push origin main
  ```

- **Clone a Repository**
  ```bash
  git clone <repository_url>
  ```

---

## **Branching**

- **Create a Branch**
  ```bash
  git branch <branch_name>
  ```
- **Switch to a Branch**
  ```bash
  git checkout <branch_name>
  ```
- **Delete a Branch**
  ```bash
  git branch -D <branch_name>
  ```

---

## **Merging Branches**

- **Merge a Branch**
  ```bash
  git merge <branch_name> -m "merge message"
  ```
- **Resolve Merge Conflicts**:
  1. Edit the conflicting files.
  2. Remove markers (e.g., `<<<<<<< HEAD`).
  3. Stage changes: `git add .`
  4. Commit: `git commit -m "Resolved merge conflict"`

---

## **Feature Branch Workflow**

1. Create and switch to a feature branch:
   ```bash
   git branch new-feature
   git checkout new-feature
   ```
2. Work on the feature and commit changes:
   ```bash
   git add .
   git commit -m "Add new feature"
   ```
3. Push the branch to GitHub:
   ```bash
   git push origin new-feature
   ```
4. Create a pull request on GitHub.
5. Merge the branch into `main` via the pull request.
6. Update your local repository:
   ```bash
   git checkout main
   git pull origin main
   
