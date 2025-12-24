# Safe Git Commands to Update GitHub Repository

## Step 1: Initialize Git (if not already done)

```bash
git init
```

## Step 2: Add the Remote Repository

```bash
git remote add origin https://github.com/DanutSpafiu/constantin-alexeevici-actor.git
```

Or if you prefer SSH (if you have SSH keys set up):

```bash
git remote add origin git@github.com:DanutSpafiu/constantin-alexeevici-actor.git
```

## Step 3: Verify .gitignore is Working (IMPORTANT!)

```bash
# Check that config.js is being ignored
git status
```

**IMPORTANT**: Make sure `config.js` does NOT appear in the file list. If it does, it means it was previously committed. See "Fix if config.js was already committed" section below.

## Step 4: Add All Files (config.js will be automatically excluded)

```bash
git add .
```

## Step 5: Commit Your Changes

```bash
git commit -m "Update website with EmailJS integration and improved structure"
```

## Step 6: Pull Any Existing Changes from GitHub (if any)

```bash
git pull origin main --allow-unrelated-histories
```

Or if your default branch is `master`:

```bash
git pull origin master --allow-unrelated-histories
```

## Step 7: Push to GitHub

```bash
git branch -M main
git push -u origin main
```

---

## If config.js Was Already Committed (Fix This First!)

If `config.js` appears in `git status`, remove it from Git tracking:

```bash
# Remove from Git but keep the file locally
git rm --cached config.js

# Commit the removal
git commit -m "Remove sensitive config.js from repository"

# Then continue with the normal flow above
```

---

## Quick All-in-One Command Sequence

```bash
# Initialize (if needed)
git init

# Add remote
git remote add origin https://github.com/DanutSpafiu/constantin-alexeevici-actor.git

# Check status (VERIFY config.js is NOT listed!)
git status

# Add files
git add .

# Commit
git commit -m "Update website with EmailJS integration, .gitignore, and improved structure"

# Pull existing changes (if any)
git pull origin main --allow-unrelated-histories

# Push
git branch -M main
git push -u origin main
```

---

## For Future Updates (After Initial Push)

```bash
# 1. Always check status first
git status

# 2. Add changes
git add .

# 3. Commit
git commit -m "Your commit message"

# 4. Push
git push
```
