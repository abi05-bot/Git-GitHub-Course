Git & GitHub Advanced Guide
1. Branching in Git

A branch allows developers to work on new features without affecting the main branch.

# Create a new branch
git branch feature-login

# Switch to the branch
git switch feature-login

# Create and switch in one command
git switch -c feature-login

# List all branches
git branch

2. Merging Branches

Merging combines changes from one branch into another.

git switch main
git merge feature-login

3. Undoing Changes
Git Reset

Moves the current branch to an earlier commit.

git reset --soft HEAD~1
git reset --mixed HEAD~1

Git Revert

Creates a new commit that reverses an earlier commit.

git revert HEAD


Use git revert when you want to undo a commit safely in a shared branch.

4. Stashing Changes

Stashing temporarily saves uncommitted changes.

# Save changes
git stash

# View saved stashes
git stash list

# Restore the latest stash and remove it
git stash pop

# Apply without removing the stash
git stash apply

5. Working with Remote Repositories
# View remote repositories
git remote -v

# Download and merge remote changes
git pull origin main

# Upload local commits
git push origin main

# Fetch remote updates without merging
git fetch origin

6. Creating a Pull Request

A Pull Request (PR) allows developers to propose changes and request code review.

Steps:

Create a feature branch.
Make changes to your files.
Stage and commit your changes.
Push the branch to GitHub.
Open the repository on GitHub.
Click Compare & pull request.
Review the changes and create the Pull Request.
Merge the PR after approval.
7. Resolving Merge Conflicts

A merge conflict occurs when Git cannot automatically combine changes.

Steps:

Open the file containing the conflict.
Find the conflict markers.
Edit the file to keep the correct content.
Remove the conflict markers.
Stage and commit the resolved file.
git status
git add filename
git commit -m "Resolve merge conflict"

8. Using .gitignore

A .gitignore file tells Git which untracked files to ignore.

Example:

node_modules/
.env
*.log
build/


Never commit passwords, API keys, or other secrets to GitHub.

9. Useful Git Commands
Command	Purpose
git log --oneline	View commit history
git diff	View unstaged changes
git show	Inspect a commit
git branch -d branch-name	Delete a merged local branch
git stash	Temporarily save changes
git fetch	Download remote updates
git status	Check repository status
10. Best Practices
Write meaningful commit messages.
Create separate branches for new features.
Pull the latest changes before starting work.
Review code before merging Pull Requests.
Use .gitignore for generated and sensitive files.
Never force-push to shared branches without understanding the impact.
Keep commits small and focused.
Conclusion

Git helps track project history, while GitHub enables collaboration and code sharing. Learning branching, merging, Pull Requests, and conflict resolution is essential for effective software development.
