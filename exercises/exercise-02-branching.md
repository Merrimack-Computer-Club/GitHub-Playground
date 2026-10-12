# Exercise 02: Branching

**Goal:** Create a feature branch so your changes are isolated from `main`.

## Steps

### 1. Make sure you are on `main` and up to date

See [Practice Guide: Step 2](../PRACTICE_GUIDE.md#2-create-a-branch) for a refresher on why you always branch from the latest `main`.

```bash
git checkout main
git pull origin main
```

### 2. Create and switch to a new branch

Use the naming format `yourname/description`:

```bash
git checkout -b yourname/add-profile
```

### 3. Verify you are on the new branch

```bash
git branch
```

> 💡 **What this command does:** Lists the branches in your local copy of the repo. You should see `main` and `yourname/add-profile`.

The active branch is marked with `*`.

### 4. Make a small change

Add a line to `student-profiles/README.md` with your name.

### 5. Confirm the branch and change are isolated

Switch back to `main` and confirm your change is not there:

```bash
git checkout main
cat student-profiles/README.md
```

Then switch back to your branch:

```bash
git checkout yourname/add-profile
```

## What You Learned

- How to create and switch branches
- Why branches isolate work from `main`
- How branch state differs between checkouts

## Next Exercise

➡️ [Exercise 03: Commit and Push](exercise-03-commit-and-push.md)
