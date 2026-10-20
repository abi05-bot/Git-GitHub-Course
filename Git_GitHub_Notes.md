# Git & GitHub Complete Notes

## 1. What is Git?

Git is a **Distributed Version Control System (DVCS)** used to track changes in files and manage source code history.

### Why Use Git?

- Track changes in code.
- Restore previous versions.
- Create and manage branches.
- Work with multiple developers.
- Maintain project history.

## 2. What is GitHub?

GitHub is an online platform used to host Git repositories and collaborate with other developers.

### Why Use GitHub?

- Store code online.
- Share projects with others.
- Collaborate using Pull Requests.
- Report bugs using Issues.
- Showcase projects in a developer portfolio.

## 3. Git vs GitHub

| Git | GitHub |
|---|---|
| Version control tool | Online hosting platform |
| Works locally | Hosts repositories online |
| Tracks file changes | Stores Git repositories |
| Uses Git commands | Provides collaboration tools |
| Example: `git commit` | Example: Pull Request |

## 4. Git Workflow

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
GitHub Repository
       |
       | git pull
       v
Updated Local Files
```

## 5. Important Git Commands

### Configure Git

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

Replace the example name and email with your own details.

### Create or Download a Repository

```bash
git init
git clone <repository-url>
```

- `git init` — Initializes a new Git repository.
- `git clone` — Downloads an existing repository to your computer.

### Check Changes

```bash
git status
git log
git diff
```

- `git status` — Checks the current working state.
- `git log` — Displays commit history.
- `git diff` — Shows changes that have not been staged.

### Add and Commit Changes

```bash
git add .
git commit -m "Add Git notes"
```

- `git add .` — Stages changes in the current directory.
- `git commit` — Saves a snapshot of staged changes.

### Connect to GitHub and Push

```bash
git remote add origin <repository-url>
git branch -M main
git push -u origin main
```

Replace `<repository-url>` with your actual GitHub repository URL. If `origin` already exists, do not add it again.

### Pull and Push Updates

```bash
git pull origin main
git push origin main
```

- `git pull` — Fetches and integrates remote changes.
- `git push` — Uploads local commits to GitHub.

## 6. Branches in Git

A branch lets you develop a feature separately without directly changing the main branch.

```bash
git branch
git switch -c feature
git switch main
git merge feature
```

### Branch Workflow

```text
main
 |
Create Feature Branch
 |
 v
Write Code
 |
Commit Changes
 |
Merge into main
 |
 v
Updated main
```

## 7. What is a Commit?

A commit is a snapshot of staged changes in a Git repository.

Example:

```bash
git add README.md
git commit -m "Update README"
```

### Good Commit Messages

- `Add login page`
- `Fix navbar issue`
- `Update documentation`
- `Improve error handling`

## 8. What is a Pull Request?

A Pull Request (PR) proposes changes from one branch to another on GitHub. It allows other developers to review changes before merging them.

### Pull Request Workflow

```text
Create Branch
     |
Make Changes
     |
Commit Changes
     |
Push Branch to GitHub
     |
Create Pull Request
     |
Review Changes
     |
Merge Pull Request
```

## 9. Practical Example: Upload a Project

```bash
# Clone your repository
git clone <repository-url>

# Enter the project directory
cd Git-GitHub-Course

# Check file changes
git status

# Stage the notes file
git add Git_GitHub_Notes.md

# Commit the changes
git commit -m "Add complete Git and GitHub notes"

# Push changes to GitHub
git push
```

Run these commands in your terminal after replacing the repository URL. If the repository is already open locally, you do not need to clone it again.

## 10. Important Git Terms

- **Repository:** A project and its tracked history.
- **Working Directory:** Files you are currently editing.
- **Staging Area:** Changes prepared for the next commit.
- **Commit:** A saved snapshot of staged changes.
- **Branch:** An independent line of development.
- **Merge:** Combines changes from different branches.
- **Remote:** A repository hosted elsewhere, such as GitHub.
- **Pull Request:** A proposal to review and merge changes.
- **Merge Conflict:** Occurs when Git cannot automatically reconcile conflicting changes.

## 11. Useful Git Commands Cheat Sheet

| Command | Purpose |
|---|---|
| `git init` | Initialize a repository |
| `git clone URL` | Clone a repository |
| `git status` | Check repository status |
| `git add .` | Stage changes |
| `git commit -m "message"` | Commit changes |
| `git log` | View commit history |
| `git diff` | View unstaged changes |
| `git branch` | List branches |
| `git switch -c feature` | Create and switch to a branch |
| `git merge feature` | Merge a branch |
| `git pull origin main` | Pull remote changes |
| `git push origin main` | Push commits to GitHub |

## 12. Useful Learning Resources

- [Git Official Website](https://git-scm.com/)
- [Git Documentation](https://git-scm.com/docs)
- [GitHub Docs](https://docs.github.com/)
- [GitHub Hello World Tutorial](https://docs.github.com/en/get-started/using-github/hello-world)

---

**Happy Learning! 🚀**

Learn Git, practice commands, and use GitHub to collaborate on projects.
