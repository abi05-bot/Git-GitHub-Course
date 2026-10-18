
# Git and GitHub Essentials

A quick-reference guide for version control with Git and collaboration on GitHub.

## Table of Contents

- [Git vs. GitHub](#git-vs-github)
- [Key Concepts](#key-concepts)
- [Setup and Configuration](#1-setup-and-configuration)
- [Starting a Project](#2-starting-a-project)
- [Tracking Changes and Commits](#3-tracking-changes-and-commits)
- [Working with Remote Repositories](#4-working-with-remote-repositories)
- [Branching and Merging](#5-branching-and-merging)
- [Viewing History and Changes](#6-viewing-history-and-changes)
- [Undoing Changes](#7-undoing-changes)
- [Working with Pull Requests](#8-working-with-pull-requests)
- [Understanding the Git Workflow](#9-understanding-the-git-workflow)
- [Best Practices](#10-best-practices)
- [Additional Learning Resources](#additional-learning-resources)

---

## Git vs. GitHub

**Git:** A distributed version control system that tracks changes in files and allows developers to manage project history locally.

**GitHub:** A cloud-based platform that hosts Git repositories and supports collaboration through Pull Requests, code reviews, issues, and project management.

## Key Concepts

| Concept | Description |
|---|---|
| Repository (Repo) | A project directory tracked by Git. |
| Commit | A recorded snapshot of changes. |
| Branch | An independent line of development. |
| Remote | A reference to a repository hosted elsewhere. |
| Clone | A local copy of an existing repository. |
| Staging Area | The area where changes are prepared before committing. |
| Merge | Combining changes from different branches. |
| Pull Request (PR) | A proposal to review and merge changes. |
| Merge Conflict | A situation where Git cannot automatically combine changes. |
| HEAD | A reference to the currently checked-out commit. |

---

## 1. Setup and Configuration

### Configure Your Git Identity

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

### Check Your Configuration

```bash
git config --list
git config user.name
git config user.email
```

### Check the Installed Git Version

```bash
git --version
```

## 2. Starting a Project

### Initialize a New Repository

```bash
git init
```

### Clone an Existing Repository

```bash
git clone <repo-url>
```

### Move Into the Project Directory

```bash
cd <project-folder>
```

### Check Repository Status

```bash
git status
```

## 3. Tracking Changes and Commits

### Stage a Specific File

```bash
git add <filename>
```

### Stage All Intended Changes

```bash
git add .
```

### Review Changes

```bash
git diff
git diff --staged
```

### Commit Staged Changes

```bash
git commit -m "docs: update documentation"
```

### View Files Changed in the Latest Commit

```bash
git show --stat HEAD
```

## 4. Working with Remote Repositories

### Add a Remote Repository

```bash
git remote add origin <repo-url>
```

### View Configured Remotes

```bash
git remote -v
```

### Rename the Current Branch to Main

```bash
git branch -M main
```

### Push the Main Branch to GitHub

```bash
git push -u origin main
```

### Push Subsequent Commits

```bash
git push
```

### Fetch and Integrate Updates

```bash
git pull origin main
```

### Download Remote Updates Without Merging

```bash
git fetch origin
```

### Set an Upstream Branch

```bash
git push --set-upstream origin <branch-name>
```

**Note:** Create the GitHub repository before pushing. If a remote named `origin` already exists, inspect it using `git remote -v` before adding another remote.

## 5. Branching and Merging

### List Local Branches

```bash
git branch
```

### List Local and Remote Branches

```bash
git branch -a
```

### Create and Switch to a New Branch

```bash
git switch -c feature-login
```

### Switch to an Existing Branch

```bash
git switch main
```

### Merge Another Branch Into the Current Branch

```bash
git merge feature-login
```

### Delete a Merged Local Branch

```bash
git branch -d feature-login
```

### Rename the Current Branch

```bash
git branch -m <new-branch-name>
```

## 6. Viewing History and Changes

### View Commit History

```bash
git log
```

### View Compact Commit History

```bash
git log --oneline
```

### View Branches and Commit History as a Graph

```bash
git log --oneline --graph --all
```

### View the Latest Commit

```bash
git show HEAD
```

### Compare Two Branches

```bash
git diff main..feature-login
```

## 7. Undoing Changes

### Discard Unstaged Changes in a File

```bash
git restore <filename>
```

### Unstage a File While Keeping Its Changes

```bash
git restore --staged <filename>
```

### Reverse an Earlier Commit With a New Commit

```bash
git revert <commit-hash>
```

### Reset the Current Branch to an Earlier Commit

```bash
git reset --soft <commit-hash>
```

`git reset --soft` moves the branch pointer while keeping changes staged.

**Warning:** Use reset commands carefully. Avoid `git reset --hard` unless you understand that uncommitted changes may be permanently lost.

## 8. Working with Pull Requests

A typical GitHub Pull Request workflow:

1. Create a feature branch.
2. Make and commit changes.
3. Push the branch to GitHub.
4. Open a Pull Request.
5. Review the changes and address feedback.
6. Merge the Pull Request when approved.

### Example Commands

```bash
git switch -c feature-update-guide
git add .
git commit -m "docs: improve Git guide"
git push -u origin feature-update-guide
```

Open your repository on GitHub and create a Pull Request from `feature-update-guide` into `main`.

## 9. Understanding the Git Workflow

Git uses three important areas to manage changes.

### Working Directory

The files and folders where you create, edit, or delete content.

### Staging Area

The area where you select changes to include in the next commit.

### Repository

The local Git database that stores committed snapshots and project history.

### Typical Workflow

```text
Working Directory
        |
        | git add
        v
Staging Area
        |
        | git commit
        v
Local Repository
        |
        | git push
        v
Remote Repository (GitHub)
```

To bring remote changes into your local branch, use `git pull`, or fetch updates and integrate them separately.

## 10. Best Practices

- Write clear and meaningful commit messages.
- Commit small, logically related changes.
- Check `git status` before committing.
- Review changes using `git diff`.
- Use descriptive branch names.
- Keep feature branches updated with the target branch.
- Review code before merging Pull Requests.
- Never commit passwords, API keys, tokens, or private credentials.
- Avoid rewriting shared commit history without team agreement.
- Use `git revert` to reverse a shared commit safely.

## Additional Learning Resources

- [Official Git Documentation](https://git-scm.com/doc)
- [Pro Git Book](https://git-scm.com/book/en/v2)
- [GitHub Documentation](https://docs.github.com/)
- [GitHub Skills](https://skills.github.com/)

---

This cheat sheet is intended as a quick reference for common Git commands and everyday GitHub collaboration workflows.
