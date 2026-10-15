# Git & GitHub Cheat Sheet 📋

> A comprehensive, quick-reference cheat sheet covering all essential Git and GitHub commands, workflows, and tips.

---

## 🔧 Initial Setup

```bash
# Set your identity
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"

# Check your configuration
git config --list

# Set default branch name to 'main'
git config --global init.defaultBranch main

# Set default editor (e.g., VS Code)
git config --global core.editor "code --wait"
```

---

## 📁 Creating & Cloning Repositories

```bash
# Initialize a new local repository
git init

# Clone an existing remote repository
git clone <repo-url>

# Clone into a specific folder
git clone <repo-url> <folder-name>

# Clone a specific branch
git clone -b <branch-name> <repo-url>
```

---

## 📝 Staging & Committing

```bash
# Check the status of your working directory
git status

# Stage a specific file
git add <filename>

# Stage all changed files
git add .

# Unstage a file (keep changes in working directory)
git restore --staged <filename>

# Commit staged changes with a message
git commit -m "Your descriptive commit message"

# Stage and commit all tracked files in one step
git commit -am "Your commit message"

# Amend the last commit (change message or add files)
git commit --amend -m "Updated commit message"
```

---

## 🌿 Branching

```bash
# List all local branches
git branch

# List all branches (local + remote)
git branch -a

# Create a new branch
git branch <branch-name>

# Switch to an existing branch
git checkout <branch-name>
# OR (modern way)
git switch <branch-name>

# Create and switch to a new branch
git checkout -b <branch-name>
# OR
git switch -c <branch-name>

# Rename the current branch
git branch -m <new-name>

# Delete a local branch (safe – only if merged)
git branch -d <branch-name>

# Force delete a local branch
git branch -D <branch-name>
```

---

## 🔀 Merging & Rebasing

```bash
# Merge a branch into the current branch
git merge <branch-name>

# Abort a merge in progress
git merge --abort

# Rebase current branch onto another branch
git rebase <branch-name>

# Interactive rebase (squash, reorder, edit commits)
git rebase -i HEAD~<number-of-commits>

# Abort a rebase in progress
git rebase --abort

# Continue rebase after resolving conflicts
git rebase --continue
```

---

## 🌐 Working with Remotes (GitHub)

```bash
# View remote connections
git remote -v

# Add a remote repository
git remote add origin <repo-url>

# Change the remote URL
git remote set-url origin <new-url>

# Remove a remote
git remote remove <remote-name>

# Push to remote (first time – set upstream)
git push -u origin <branch-name>

# Push to remote (subsequent times)
git push

# Force push (use with caution!)
git push --force

# Fetch changes from remote (doesn't merge)
git fetch

# Pull changes from remote (fetch + merge)
git pull origin <branch-name>

# Pull with rebase instead of merge
git pull --rebase origin <branch-name>
```

---

## 📜 Viewing History & Logs

```bash
# View commit history
git log

# Compact one-line log
git log --oneline

# Log with graph visualization
git log --oneline --graph --all

# Show changes in a specific commit
git show <commit-hash>

# Show the diff of unstaged changes
git diff

# Show the diff of staged changes
git diff --staged
```

---

## ⏪ Undoing Changes

```bash
# Discard changes in a file (restore to last commit)
git restore <filename>

# Unstage a staged file
git restore --staged <filename>

# Reset to a previous commit (keep changes staged)
git reset --soft <commit-hash>

# Reset to a previous commit (keep changes unstaged)
git reset --mixed <commit-hash>

# Reset to a previous commit (discard all changes) ⚠️
git reset --hard <commit-hash>

# Create a new commit that undoes a previous commit
git revert <commit-hash>
```

---

## 🏷️ Tags

```bash
# List all tags
git tag

# Create a lightweight tag
git tag <tag-name>

# Create an annotated tag
git tag -a <tag-name> -m "Tag message"

# Push a tag to remote
git push origin <tag-name>

# Push all tags to remote
git push origin --tags

# Delete a local tag
git tag -d <tag-name>

# Delete a remote tag
git push origin --delete <tag-name>
```

---

## 📦 Stashing

```bash
# Stash your current changes
git stash

# Stash with a descriptive message
git stash save "Work in progress on feature X"

# List all stashes
git stash list

# Apply the most recent stash (keep it in stash list)
git stash apply

# Apply and remove the most recent stash
git stash pop

# Apply a specific stash
git stash apply stash@{<index>}

# Drop a specific stash
git stash drop stash@{<index>}

# Clear all stashes
git stash clear
```

---

## 🔍 Searching & Blaming

```bash
# Search for a string in tracked files
git grep "search-term"

# Show who last modified each line of a file
git blame <filename>
```

---

## 🤝 GitHub Collaboration Workflow

### Fork & Pull Request Model

1. **Fork** the repository on GitHub
2. **Clone** your fork locally:
   ```bash
   git clone <your-fork-url>
   ```
3. **Add upstream** remote (original repo):
   ```bash
   git remote add upstream <original-repo-url>
   ```
4. **Create a feature branch**:
   ```bash
   git checkout -b feature/my-new-feature
   ```
5. **Make changes**, stage, and commit:
   ```bash
   git add .
   git commit -m "Add my new feature"
   ```
6. **Push** your branch to your fork:
   ```bash
   git push origin feature/my-new-feature
   ```
7. **Open a Pull Request** on GitHub from your branch → upstream `main`

### Keeping Your Fork Up-to-Date

```bash
git fetch upstream
git checkout main
git merge upstream/main
git push origin main
```

---

## ⚠️ Common Mistakes & Fixes

| Mistake | Fix |
|---|---|
| Committed to wrong branch | `git cherry-pick <commit>` on the correct branch, then `git reset HEAD~1` on the wrong one |
| Typo in last commit message | `git commit --amend -m "Corrected message"` |
| Accidentally deleted a branch | `git reflog` → find the commit → `git checkout -b <branch> <commit-hash>` |
| Pushed sensitive data | Use `git filter-branch` or BFG Repo Cleaner, then force push |
| Merge conflicts | Edit conflicted files, `git add .`, then `git commit` |

---

## 💡 Tips & Best Practices

- ✅ Write clear, descriptive commit messages
- ✅ Commit often, push regularly
- ✅ Use branches for every new feature or bug fix
- ✅ Pull before you push to avoid conflicts
- ✅ Use `.gitignore` to exclude unnecessary files
- ✅ Review your changes with `git diff` before committing
- ✅ Use Pull Requests for code review and collaboration
- ❌ Never force push to shared branches
- ❌ Don't commit large binary files or secrets/passwords

---

## 📚 Useful `.gitignore` Patterns

```gitignore
# OS files
.DS_Store
Thumbs.db

# IDE/Editor files
.vscode/
.idea/
*.swp

# Dependencies
node_modules/
vendor/

# Build output
build/
dist/
*.o
*.exe

# Environment files
.env
.env.local

# Logs
*.log
```

---

*Happy coding! 🚀*
