
# 🚦 Git Workflow Cheat Sheet

### 🔧 **For Quick Fixes / Solo Work**
```bash
# Create and switch to a new bugfix branch
git checkout -b bugfix-fix-typo

# Make changes, test
git add .
git commit -m "Fix typo on homepage"

# Merge into main and push
git checkout main
# Pull latest changes from remote main
git pull origin main
git merge bugfix-fix-typo
git push origin main

# Optional cleanup
git branch -d bugfix-fix-typo
```

📌 **Tip:** No need to push the bugfix branch unless you want backup or visibility.

---

### 🚀 **For Larger Features / Team Collaboration**
```bash
# Start a new feature branch
git checkout -b feature-user-auth

# Commit changes as you go. always commit/stage changes before you switch to any branch
git add .
git commit -m "Add login form"
git commit -m "Hook up API to login form"

# Push the branch for others or PR
git push origin feature-user-auth

# After review, merge into main
git checkout main
git pull origin main
git merge feature-user-auth
git push origin main

# Optional: Delete remote & local branch
git push origin --delete feature-user-auth
git branch -d feature-user-auth
```

📌 **Tip:** Ideal for teams, code review, and CI/CD pipelines.

---

### 🔁 **Branch Naming Conventions (Optional but Recommended)**

| Type       | Example                  |
|------------|--------------------------|
| Bug Fix    | `bugfix-login-error`     |
| New Feature| `feature-dark-mode`      |
| Hotfix     | `hotfix-crash-homepage`  |
| Chore/Infra| `chore-update-deps`      |

---

### ✅ **Helpful Commands Recap**

```bash
git branch                # List local branches
git checkout -b <name>    # Create + switch to branch
git switch <branch>       # Modern way to switch
git pull origin main
git merge <branch>        # Merge into current branch
git push origin <branch>  # Push branch to GitHub
git branch -d <branch>    # Delete local branch
git push origin --delete <branch>  # Delete remote branch
```