# Practical Git Guide: Real Commands for Real Projects

When I first started with Git, I found most tutorials intricate and theoretical. I wasn't very active on GitHub initially the commands seemed intimidating and the workflows confusing. But once I established a simple, practical routine, version control became second nature.

This guide documents the straightforward workflow I developed to make Git actually useful in day-to-day coding. No unnecessary complexity, just the commands and practices I use every single day. I've organized everything in the exact order you'll need it, from setup to daily use, so you can start being productive immediately.

> **Tip**: If you want to simplify this process, install GitHub Desktop (available for Windows and Mac). It provides a user-friendly GUI where you can commit, view changes, push, and create repositories very easily without memorizing commands.

## Quick Daily Workflow Overview

### Morning
1. **Pull the latest changes** from the main branch
2. **Create or switch to your feature branch** for the day's work

### During Development
3. **Code in small, focused chunks** that accomplish one thing
4. **Commit frequently** after completing each logical unit of work
5. **Write clear commit messages** describing what you did
6. **Push your branch** at reasonable intervals (at least once daily)

### Staying in Sync
7. **Merge main into your branch** daily to avoid big conflicts later
8. **Resolve conflicts immediately** when they occur

### Completing Work
9. **Ensure your branch is up to date** with main before finalizing
10. **Create a pull request** when your feature is complete
11. **Address feedback** with new commits
12. **Clean up** by deleting the branch after it's merged

### End of Day
13. **Commit or stash all changes** before logging off
14. **Push your branch** as a backup

## Initial Setup

### 1. Install Git (if not already installed)

```bash
# Ubuntu/Debian
sudo apt install git

# macOS
brew install git

# Windows
# Download and install from https://git-scm.com/download/win
```

### 2. Configure Git with your identity

```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

## Starting a New Project

### 3. Create a local repository

```bash
# Navigate to your project folder
cd ~/projects/my-new-app

# Initialize git
git init
```

### 4. Create a repository on GitHub

1. Go to GitHub.com and log in
2. Click "+" in the top right, then "New repository"
3. Name your repository "my-new-app"
4. Leave it as public (or choose private)
5. Don't initialize with README, .gitignore, or license
6. Click "Create repository"

### 5. Generate a personal access token on GitHub

1. Click your profile icon → Settings
2. Scroll to "Developer settings" at the bottom of the left sidebar
3. Click "Personal access tokens" → "Tokens (classic)"
4. Click "Generate new token" → "Generate new token (classic)"
5. Give it a name like "my-projects"
6. Select scopes: at minimum check "repo"
7. Click "Generate token"
8. Copy the token (you'll only see it once!)

### 6. Connect your local repository to GitHub

```bash
# Add the remote repository URL with your token
git remote add origin https://YOUR_TOKEN@github.com/your-username/my-new-app.git

# Verify remote was added correctly
git remote -v
```

## Daily Workflow Commands

### 7. Create and add files to your project

```bash
# Create some files

# Add files to staging
git add .

# Check status
git status
```

### 8. Make your first commit

```bash
git commit -m "Initial commit: project structure"
```

### 9. Push to GitHub

```bash
# Push to the main branch
git push -u origin main
```

### 10. Working with branches

```bash
# Create and switch to a new feature branch
git checkout -b feature/login-page

# Make required changes in file(s)

# Add and commit changes
git add .
git commit -m "Add login page files"

# Push the feature branch to GitHub
git push -u origin feature/login-page
```

### 12. Pull changes made by others

```bash
# Get and integrate latest changes
git pull origin main
```

### 13. Undo changes

```bash
# Undo unstaged changes to a file
git checkout -- index.html

# Undo staged changes (unstage)
git reset HEAD index.html

# Undo a commit (creates a new commit that reverts changes)
git revert HEAD
```

### Stash changes temporarily

```bash
# Save changes without committing
git stash
```

## Common Repository Tasks

### Clone an existing repository

```bash
git clone https://github.com/your-username/repo-name.git
```

### 5. Best Practices for Using Git

1. Commit Often: Smaller, focused commits are easier to review and revert.
2. Write Descriptive Commit Messages: Clearly describe what and why you've made changes.
3. Use Branches Wisely: Create branches for features, fixes, and experiments.
4. Pull Before You Push: Avoid conflicts by syncing with the remote before pushing.
5. Don't Commit Secrets: Exclude sensitive information like API keys using .gitignore.

### Conclusion

Learning Git doesn't have to be overwhelming. Start with these basic commands and workflows, and gradually add more advanced features as you become comfortable. Remember, the goal is to make version control work for you, not the other way around.

Happy coding!