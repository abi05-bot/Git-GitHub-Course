
# Git Branching and Merging

## 1. What is a Branch?

A branch is a separate line of development. It allows developers to work on features without directly changing the main branch.

## 2. List Branches

```bash
git branch
git branch -a
```

## 3. Create and Switch Branch

```bash
git branch feature/login
git switch feature/login
```

Create and switch in one command:

```bash
git switch -c feature/dashboard
```

## 4. Merge a Branch

First, switch to the destination branch:

```bash
git switch main
git merge feature/login
```

## 5. Delete a Branch

```bash
git branch -d feature/login
```

Force deletion (use carefully):

```bash
git branch -D feature/login
```

## 6. Rename a Branch

```bash
git branch -m new-branch-name
```

## 7. Practical Workflow

```bash
git switch main
git pull origin main
git switch -c feature/profile
# Make your code changes
git add .
git commit -m "Add profile feature"
git push -u origin feature/profile
```

Then open GitHub and create a Pull Request.

## Best Practices

- Use descriptive branch names.
- Keep branches focused on one feature or bug.
- Pull the latest changes before starting work.
- Review changes before merging.
