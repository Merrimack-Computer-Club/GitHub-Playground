# Exercise 05: Merge Conflicts

**Goal:** Intentionally create and resolve a merge conflict.

## Background

A merge conflict happens when two branches modify the same part of the same file. Git cannot automatically decide which version to keep, so it asks you to resolve it manually.

## Steps

### 1. Set up the conflict

1. Make sure `main` is up to date: `git checkout main`, then `git pull`
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

First get the latest `main` (which now includes Branch A), then merge it into Branch B:

```bash
git checkout main
git pull
git checkout yourname/conflict-b
git merge main
```

Git will pause and report a conflict in `sandbox/README.md`. Inside the file, you will see markers like:

```
<<<<<<< HEAD
Your Branch B change
=======
The change that came from main (Branch A)
>>>>>>> main
```

**Reading the markers:**

| Marker | Meaning |
|---|---|
| `<<<<<<< HEAD` | Start of **your** version: the branch you're on right now (Branch B). VS Code calls this the **Current Change**. |
| `=======` | The divider between the two versions. |
| `>>>>>>> main` | End of the **incoming** version: the branch you're merging in (`main`, which has Branch A's change). VS Code calls this the **Incoming Change**. |

An easy way to remember it: `<<<<<<<` points back at where you are, `>>>>>>>` points at what's coming in.

#### Resolve it in VS Code (recommended)

Resolving conflicts is much easier in [VS Code](https://code.visualstudio.com/) than by hand, and it's what we recommend for everyone.

1. Open the repo folder in VS Code and click the **Source Control** icon in the left sidebar. Conflicted files are listed under **Merge Changes**.
2. Open `sandbox/README.md`. VS Code highlights the two versions in different colors and shows clickable options above the conflict:
   - **Accept Current Change**: keep your Branch B version.
   - **Accept Incoming Change**: keep the version from `main`.
   - **Accept Both Changes**: keep both, one after the other.
   - **Compare Changes**: view the two versions side by side.
3. Click the option you want (you can still edit the text afterwards). VS Code removes the markers for you.
4. Save the file.

For bigger conflicts, click **Resolve in Merge Editor** in the bottom right of the file to get a side-by-side view.

#### Resolve it by hand

If you're not using VS Code, edit the file in any text editor to keep the version you want (or combine both). Then delete all three marker lines (`<<<<<<<`, `=======`, `>>>>>>>`).

### 5. Stage and commit the resolution

```bash
git add sandbox/README.md
git commit -m "fix: resolve merge conflict in sandbox/README.md"
git push origin yourname/conflict-b
```

The PR on GitHub should now show no conflicts.

## What You Learned

- What causes merge conflicts
- How to read conflict markers (`<<<<<<<` is your version, `>>>>>>>` is the incoming one)
- How to resolve a conflict in VS Code or by hand
- How to push a conflict resolution

## Next Exercise

➡️ [Exercise 06: Documentation Update](exercise-06-documentation-update.md)
