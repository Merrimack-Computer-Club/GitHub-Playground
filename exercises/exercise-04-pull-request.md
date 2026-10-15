# Exercise 04: Pull Requests

**Goal:** Open a Pull Request on GitHub and go through the review process.

## Steps

### 1. Open a Pull Request

1. Go to the repository on GitHub.
2. Click **"Compare & pull request"** for your branch.
3. Fill in the PR form:
   - **Title:** A short, descriptive summary (e.g., `docs: add Peter's student profile`)
   - **Description:** What you changed and why. Reference the exercise: _"Practicing PR workflow as part of Exercise 04."_
4. Click **"Create pull request"**.

### 2. Request a review

In the right sidebar, click **"Reviewers"** and select a club eBoard member.

- Peter Hajj's GitHub username is `phajj`.

### 3. Respond to review feedback

If a reviewer leaves a comment:
1. Make the requested change locally.
2. Commit and push, the PR updates automatically.
3. Reply to the comment and mark it as resolved.

### 4. Merge the PR

Once approved:
1. Click **"Merge pull request"**.
2. Click **"Confirm merge"**.
3. Click **"Delete branch"** to clean up.

> ⚠️ **Merrimack Class projects:** Never delete a branch in a class project repo. The CS faculty use your branches for grading. Deleting branches is fine here in the playground.

### 5. Update your local `main`

```bash
git checkout main
git pull
```

## What You Learned

- How to open and describe a Pull Request
- How to request and respond to reviews
- How to merge and clean up a branch

## Next Exercise

➡️ [Exercise 05: Merge Conflicts](exercise-05-merge-conflict.md)
