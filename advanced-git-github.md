
# Advanced Git & GitHub Course

## 1. Introduction

Git is a distributed version control system used to track changes in source code.

GitHub is an online platform used to host Git repositories and collaborate with developers.

## 2. Important Git Commands

### Check Repository Status

```bash
git status
git log --oneline
git diff
git diff --staged
```

### Undo Changes

```bash
# Unstage a file
git restore --staged filename.txt

# Discard unstaged changes in a file
git restore filename.txt

# Create a new commit that reverses an earlier commit
git revert <commit-id>
```

### Stash Changes

```bash
# Temporarily save uncommitted changes
git stash

# List saved changes
git stash list

# Restore the latest stash
git stash pop
```

## 3. Branching and Merging

```bash
# Create a new branch
git branch feature-login

# Switch to a branch
git switch feature-login

# Create and switch to a new branch
git switch -c feature-dashboard

# View all branches
git branch

# Merge a feature branch into the current branch
git merge feature-login

# Delete a local branch
git branch -d feature-login
```

## 4. GitHub Collaboration

### Fork and Clone

```bash
# Clone a repository
git clone <repository-url>

# Add the original repository as an upstream remote
git remote add upstream <original-repository-url>

# View configured remotes
git remote -v

# Fetch updates from the original repository
git fetch upstream
```

### Pull Requests Workflow

1. Create a new feature branch.
2. Make changes to your files.
3. Stage and commit your changes.
4. Push the branch to GitHub.
5. Open a Pull Request.
6. Review the changes and discuss feedback.
7. Merge the Pull Request after approval.

## 5. Resolve Merge Conflicts

Merge conflicts happen when Git cannot automatically combine
changes made to the same part of a file.

Steps:
1. Run `git status` to identify conflicted files.
2. Open each conflicted file.
3. Look for conflict markers.
4. Edit the file to keep the intended content.
5. Remove the conflict markers.
6. Stage the resolved files.
7. Commit the resolution.

```bash
git add <resolved-file>
git commit -m "Resolve merge conflict"
```

## 6. .gitignore

A `.gitignore` file tells Git which untracked files to ignore.

Example:

```gitignore
node_modules/
.env
*.log
dist/
__pycache__/
```

Never commit passwords, API keys, access tokens,
or other confidential information.

## 7. Tags and Releases

```bash
# Create a version tag
git tag v1.0.0

# List tags
git tag

# Push a tag to GitHub
git push origin v1.0.0
```

GitHub Releases can be used to publish versioned
software and release notes.

## 8. GitHub Issues and Projects

- Issues: Track bugs, tasks, and feature requests.
- Labels: Categorize issues and pull requests.
- Milestones: Group work toward a target.
- Projects: Organize and track project tasks.
- Discussions: Enable community conversations.

## 9. GitHub Actions

GitHub Actions automates workflows such as testing,
building, and deploying applications.

Workflow files are stored in:

`.github/workflows/`

Example workflow:

```yaml
name: Basic CI

on:
  push:
  pull_request:

jobs:
  check:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout repository
        uses: actions/checkout@v4

      - name: Display success message
        run: echo "GitHub Actions is working!"
```

## 10. Practical Exercises

1. Create a new Git repository.
2. Add a README.md file and commit it.
3. Create a feature branch.
4. Make changes and push the branch.
5. Open a Pull Request on GitHub.
6. Create and resolve a merge conflict.
7. Add a .gitignore file.
8. Create a version tag.
9. Create a GitHub Issue.
10. Configure a basic GitHub Actions workflow.

## 11. Learning Resources

- Git Documentation: https://git-scm.com/doc
- GitHub Documentation: https://docs.github.com/
- GitHub Skills: https://skills.github.com/

## Conclusion

Practice Git commands regularly to understand version control,
collaboration, branching, and software development workflows.
