## Git Branch Naming Issue

### Problem
When working with GitHub repositories, you might encounter branch naming conflicts:

- GitHub's default branch is named `main`
- Local Git repositories created with `git init` typically use `master` as the default branch
- This mismatch causes problems when pushing, creating separate branches instead of updating the same one

### How to Fix

If you've already pushed to the wrong branch:

```bash
# Rename your local branch
git checkout master
git branch -m master main

# Set the upstream branch and push
git push -u origin main

# Optionally, delete the unwanted remote branch
git push origin --delete master
```

### How to Avoid

Prevent this issue with one of these approaches:

1. Set your default Git branch name globally:
```bash
git config --global init.defaultBranch main
```

2. Rename the branch immediately after repository creation:
```bash
git init
git branch -m master main
```

3. Always clone existing repositories instead of creating new ones:
```bash
git clone <repository-url>
```