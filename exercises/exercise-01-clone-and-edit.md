# Exercise 01: Clone and Edit

**Goal:** Clone the repository to your local machine and make your first edit.

## Steps

### 1. Clone the repository

Follow **Step 1** in the [Practice Guide](../PRACTICE_GUIDE.md#1-clone-the-repository) for the full clone instructions, including the recommended path and what each command does.

Once cloned, navigate into the repo:

```bash
cd GitHub-Playground
```

### 2. Explore the structure

Look around before making changes:

```bash
ls
cat README.md
```

> 💡 **What these commands do:**
> - `ls`: Lists the files and folders in your current directory. Use this to get a feel for how the project is laid out before touching anything.
> - `cat README.md`: Prints the contents of `README.md` directly in the terminal. Every repository should have a README that explains the project's purpose and how to use it.

### 3. Open a file and edit it

Open `sandbox/README.md` in your text editor or VS Code and add a line with your name and today's date:

```
- Your Name, YYYY-MM-DD, first edit!
```

### 4. Check the status

```bash
git status
```

You should see `sandbox/README.md` listed as modified.

> 💡 **What this command does:** Shows the current state of your working directory. Git categorizes files as *modified* (changed but not staged), *staged* (ready to commit), or *untracked* (new files Git doesn't know about yet). `git status` is one of the most useful commands to run frequently, since it tells you exactly where you are at any point.

### 5. View your changes

```bash
git diff sandbox/README.md
```

> 💡 **What this command does:** Displays a line-by-line comparison between the file as it exists on disk and the last committed version. Lines prefixed with `+` are additions and lines with `-` are removals. Reviewing a diff before committing is a good habit because it lets you confirm you are only saving what you intended.

## What You Learned

- How to clone a repository
- How to navigate the file structure
- How to edit a file and see uncommitted changes with `git diff`

## Next Exercise

➡️ [Exercise 02: Branching](exercise-02-branching.md)
