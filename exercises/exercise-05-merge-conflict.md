# Exercise 05: Merge Conflicts

**Goal:** Intentionally create and resolve a merge conflict.

## Background

A merge conflict happens when two branches modify the same part of the same file. Git cannot automatically decide which version to keep, so it asks you to resolve it manually.

## Steps

### 1. Set up the conflict

1. Make sure `main` is up to date: `git pull origin main`
2. Create **Branch A**: `git checkout -b yourname/conflict-a`
3. Edit the first line of `sandbox/README.md` and commit.
4. Push Branch A: `git push origin yourname/conflict-a`
5. Switch back to `main`: `git checkout main`
6. Create **Branch B**: `git checkout -b yourname/conflict-b`
7. Edit the **same first line** of `sandbox/README.md` differently and commit.
8. Push Branch B: `git push origin yourname/conflict-b`

### 2. Merge Branch A into main first (via PR)

Open a PR for Branch A and merge it.

### 3. Open a PR for Branch B

GitHub will warn that Branch B has a conflict with `main`.

### 4. Resolve the conflict locally

```bash
git checkout yourname/conflict-b
git pull origin main
```

Git will pause and show a conflict. Open the conflicted file. You will see markers like:

```
<<<<<<< HEAD
Your Branch B change
=======
The change that came from main (Branch A)
>>>>>>> main
```

Edit the file to keep the version you want (or combine both). Remove all conflict markers.

### 5. Stage and commit the resolution

```bash
git add sandbox/README.md
git commit -m "fix: resolve merge conflict in sandbox/README.md"
git push origin yourname/conflict-b
```

The PR on GitHub should now show no conflicts.

## What You Learned

- What causes merge conflicts
- How to read and resolve conflict markers
- How to push a conflict resolution

## Next Exercise

➡️ [Exercise 06: Documentation Update](exercise-06-documentation-update.md)
