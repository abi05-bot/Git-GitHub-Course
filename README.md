# Git and GitHub 

A quick-reference guide for version control with Git and collaboration on GitHub.

---

## What is Git vs. GitHub?
- **Git**: A local, distributed version control system to track file changes.
- **GitHub**: A cloud-based platform to host Git repositories and collaborate with others.


---

## Key Concepts
- **Repository (Repo)**: Project folder tracked by Git.
- **Commit**: A snapshot/save point of your changes.
- **Branch**: An isolated line of development (e.g., `main`, `feature-login`).
- **Remote**: The GitHub repository URL hosted online.
- **Pull Request (PR)**: A proposal to merge changes from one branch into another.

---

## Essential Commands Cheat Sheet

### 1. Setup and Configuration
```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

### 2. Starting a Project
```bash
git init                            # Initialize local repo
git clone <repo-url>                # Clone remote repo locally
```

### 3. Tracking Changes and Commits
```bash
git status                          # Check changed files
git add .                           # Stage all changes
git commit -m "Your commit message" # Save snapshot
```

### 4. Working with GitHub (Remote)
```bash
git remote add origin <repo-url>    # Link local repo to GitHub
git branch -M main                  # Set main branch
git push -u origin main             # Push changes to GitHub
git pull origin main                # Fetch and merge latest updates
```

### 5. Branching and Merging
```bash
git checkout -b <branch-name>       # Create and switch to a new branch
git checkout main                   # Switch back to main
git merge <branch-name>             # Merge branch changes into current branch
```

### 6. Understanding the Git Workflow

Git workflow consists of three important areas:

Working Directory: Where you create or modify files.
Staging Area: Where you prepare changes before committing.
Repository: Where committed changes are stored


# Git and GitHub — Quick Reference Guide

A practical quick-reference guide to Git commands, version control, branching, and GitHub collaboration.

## Table of Contents

- [Git vs GitHub](#git-vs-github)
- [Key Concepts](#key-concepts)
- [Git Workflow](#git-workflow)
- [Setup and Configuration](#1-setup-and-configuration)
- [Viewing Changes and History](#2-viewing-changes-and-history)
- [Undoing Changes](#3-undoing-changes)
- [Branch Management](#4-branch-management)
- [GitHub Collaboration](#5-github-collaboration)
- [Merge Conflicts](#6-handling-merge-conflicts)
- [.gitignore](#7-gitignore)
- [Forks and Pull Requests](#8-forks-and-pull-requests)
- [Connecting a Project to GitHub](#9-connecting-a-local-project-to-github)
- [GitHub Best Practices](#10-github-best-practices)
- [Advanced Git Concepts](#11-advanced-git-concepts)

---

## Git vs GitHub

- **Git:** A distributed version control system that tracks changes in files.
- **GitHub:** A cloud-based platform for hosting Git repositories and collaborating with developers.

## Key Concepts

| Concept | Description |
|---|---|
| Repository | A project tracked using Git |
| Commit | A snapshot of project changes |
| Branch | An independent line of development |
| Remote | A reference to a hosted repository |
| HEAD | Reference to the current commit or checkout position |
| Commit Hash | A unique identifier for a commit |
| Pull Request | A proposal to merge changes into another branch |
| Code Review | Reviewing changes before merging |
| `.gitignore` | Specifies untracked files Git should ignore |

## Git Workflow

The standard Git workflow consists of three main areas.

1. **Working Directory:** Create or modify files.
2. **Staging Area:** Prepare changes for the next commit.
3. **Local Repository:** Save changes as commits.
4. **Remote Repository:** Push commits to GitHub.

```bash
git status
git add .
git commit -m "Add project changes"
git push
```

## 1. Setup and Configuration

Set your Git identity:

```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

Check your configuration:

```bash
git config --list
git --version
```

## 2. Starting a Project

Initialize a repository:

```bash
git init
```

Clone an existing repository:

```bash
git clone <repo-url>
cd <repository-folder>
```

Check the repository status:

```bash
git status
```

## 3. Tracking Changes and Commits

| Command | Purpose |
|---|---|
| `git status` | Show the current working tree status |
| `git add .` | Stage changes in the current directory |
| `git add <file>` | Stage a specific file |
| `git commit -m "message"` | Create a commit |
| `git diff` | View unstaged changes |
| `git diff --staged` | View staged changes |
| `git log` | View commit history |
| `git log --oneline` | Display compact commit history |
| `git show` | View details of a commit |
| `git status -sb` | Show a short branch and status summary |
| `git ls-files` | List tracked files |

Example:

```bash
git add .
git diff --staged
git commit -m "Fix login validation"
```

## 4. Undoing Changes

| Command | Purpose |
|---|---|
| `git restore <file>` | Discard unstaged changes in a file |
| `git restore --staged <file>` | Remove a file from staging |
| `git commit --amend` | Modify the latest commit |
| `git revert <commit-id>` | Create a commit that reverses an earlier commit |
| `git reset --soft HEAD~1` | Undo the latest commit while keeping changes staged |
| `git stash` | Temporarily store uncommitted changes |
| `git stash pop` | Restore stashed changes |

**Warning:** `git reset --hard` can permanently discard local changes. Use it carefully.

## 5. Branch Management

| Command | Purpose |
|---|---|
| `git branch` | List local branches |
| `git branch <name>` | Create a branch |
| `git switch <name>` | Switch branches |
| `git switch -c <name>` | Create and switch to a branch |
| `git branch -d <name>` | Delete a merged local branch |
| `git branch -a` | List local and remote-tracking branches |
| `git merge <branch>` | Merge a branch into the current branch |

Recommended branch naming:

- `feature/login-page`
- `feature/user-profile`
- `bugfix/navbar-error`
- `hotfix/payment-error`

Example:

```bash
git switch -c feature/login-page
git add .
git commit -m "Add login page"
git switch main
git merge feature/login-page
```

## 6. GitHub Collaboration

View configured remotes:

```bash
git remote -v
```

Download remote updates without merging:

```bash
git fetch origin
```

Fetch and integrate updates from the remote main branch:

```bash
git pull origin main
```

Push the current branch to GitHub:

```bash
git push
```

Push a new branch and set its upstream:

```bash
git push -u origin feature/login-page
```

Delete a remote branch:

```bash
git push origin --delete feature/login-page
```

### Fetch vs Pull

- **Fetch:** Downloads remote updates without integrating them into your current branch.
- **Pull:** Fetches remote updates and integrates them into your current branch.

## 7. Handling Merge Conflicts

A merge conflict occurs when Git cannot automatically combine conflicting changes.

Example:

```text
<<<<<<< HEAD
Welcome to my website
=======
Welcome to our website
>>>>>>> feature/homepage
```

Resolution steps:

1. Open the conflicted file.
2. Choose or combine the correct changes.
3. Remove the conflict markers.
4. Stage the resolved file.
5. Complete the merge if Git requires a merge commit.

```bash
git status
git add <file>
git commit
```

## 8. `.gitignore`

The `.gitignore` file specifies untracked files and directories that Git should ignore.

Example:

```gitignore
# Dependencies
node_modules/

# Environment variables and secrets
.env
.env.*
!.env.example

# Build output
dist/
build/

# Python cache
__pycache__/
*.pyc

# IDE settings
.vscode/
```

**Important:** `.gitignore` does not stop tracking files already committed. If a secret has been exposed, revoke or rotate the credential immediately.

## 9. Forks and Pull Requests

- **Fork:** Creates your own GitHub copy of another repository.
- **Pull Request (PR):** Proposes changes for review and merging.
- **Code Review:** Checks code quality, correctness, and potential issues before merging.

Typical workflow:

```bash
git switch -c feature/new-feature
git add .
git commit -m "Add new feature"
git push -u origin feature/new-feature
```

Then open a Pull Request on GitHub, review feedback, make any necessary updates, and merge when approved.

## 10. Connecting a Local Project to GitHub

For a new local project and an empty GitHub repository:

```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin <repo-url>
git push -u origin main
```

Replace `<repo-url>` with your actual GitHub repository URL.

If the remote repository already contains commits, such as a README, check the repository history before pushing to avoid unrelated-history issues.

For an existing GitHub project:

```bash
git clone <repo-url>
cd <repository-folder>
git status
```

## 11. Advanced Git Concepts

| Concept or Command | Description |
|---|---|
| `HEAD` | Reference to the current commit or checkout position |
| `origin` | Conventional name for the default remote |
| `HEAD~1` | First parent of the current commit |
| `git rebase` | Replays commits onto another base commit |
| `git cherry-pick <commit-id>` | Applies a specific commit to the current branch |
| `git tag` | Creates or manages named references, often for releases |
| GitHub Actions | Automates testing, builds, and deployment |
| SSH Key | Supports key-based authentication for Git operations |
| `README.md` | Documents the project, setup, and usage |

## 12. GitHub Best Practices

- Write meaningful commit messages.
- Create separate branches for features and bug fixes.
- Fetch or pull updates regularly when collaborating.
- Never commit passwords, API keys, tokens, or private credentials.
- Maintain a clear `README.md`.
- Use Pull Requests and code reviews.
- Keep commits focused on logical changes.
- Add automated tests where appropriate.
- Use GitHub Actions for CI/CD workflows.
- Review changes before pushing or merging.

## Learning Resources

- [Official Git Documentation](https://git-scm.com/doc)
- [Git Reference](https://git-scm.com/docs)
- [GitHub Docs](https://docs.github.com/)
- [GitHub Skills](https://skills.github.com/)

---


