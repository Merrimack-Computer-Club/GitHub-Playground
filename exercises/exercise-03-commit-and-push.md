# Exercise 03: Commit and Push

**Goal:** Stage your changes, write a commit message, and push your branch to GitHub.

## Steps

### 1. Check what has changed

```bash
git status
git diff
```

### 2. Stage your changes

Stage a specific file:

```bash
git add student-profiles/README.md
```

Or stage everything:

```bash
git add .
```

> 💡 **What this command does:** The `.` means "the current folder," so this stages every changed or new file in the folder you're in and all the folders inside it. Run `git status` first so you don't stage a file you didn't mean to.

### 3. Write a commit message

```bash
git commit -m "docs: add [your name] to student profiles"
```

> 💡 See [Practice Guide: Step 4](../PRACTICE_GUIDE.md#4-stage-and-commit) for commit message conventions.

### 4. Push your branch

```bash
git push origin yourname/add-profile
```

### 5. Verify on GitHub

Open the repository on GitHub. You should see a banner offering to open a Pull Request for your branch.

## What You Learned

- The staging area and `git add`
- How to write a clear commit message
- How to push a branch to the remote

## Next Exercise

➡️ [Exercise 04: Pull Requests](exercise-04-pull-request.md)
