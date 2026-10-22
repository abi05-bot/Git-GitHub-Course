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
