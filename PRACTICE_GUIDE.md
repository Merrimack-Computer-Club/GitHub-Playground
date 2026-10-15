# Practice Guide

This guide walks you through the full GitHub workflow you'll practice in this repository. Follow each step in order the first time, then repeat any exercise as many times as you like.

## Prerequisites

- [Git](https://git-scm.com/downloads) installed on your machine (`git --version` to verify)
  - **Mac:** Git comes preinstalled macOS. Run `git --version` to verify it was installed.
  - **Windows:** Download and run the installer from [Git for Windows](https://git-scm.com/download/win).
- A [GitHub account](https://github.com/signup), I recommend setting your username to your Merrimack email without the @merrimack.edu for convenience in Merrimack classes that use GitHub (e.g. hajjp for hajjp@merrimack.edu)
- (recommended) An IDE (integrated development environment) such as [VS Code](https://code.visualstudio.com/).

## Step-by-Step Workflow

### 1. Clone the Repository

> ⚠️ **Where to clone:** Do **not** clone into a folder synced to OneDrive or iCloud. Repositories may contain environment variables and secrets that should never be uploaded to cloud storage.
>
> **Recommended path:** Create a `Repos` folder directly under your user profile and clone there.

**Windows** (recommended path: `C:\Users\your-name\Repos\`)

```bash
# Windows (Command Prompt or PowerShell)
# Create the Repos directory if it doesn't exist (run once)
mkdir C:\Users\%USERNAME%\Repos

# Navigate to it, then clone
cd C:\Users\%USERNAME%\Repos
git clone https://github.com/Merrimack-Computer-Club/GitHub-Playground.git
cd GitHub-Playground
```

**Mac/Linux** (recommended path: `~/Repos/`)

```bash
# Mac/Linux (Terminal)
# Create the Repos directory if it doesn't exist (run once)
mkdir -p ~/Repos

# Navigate to it, then clone
cd ~/Repos
git clone https://github.com/Merrimack-Computer-Club/GitHub-Playground.git
cd GitHub-Playground
```

> 💡 **What these commands do:**
> - `mkdir`: Stands for **M**a**k**e **Dir**ectory (a directory is just a folder). Here it creates a `Repos` folder inside your user folder. You only need to do this once.
>   - `%USERNAME%` (Windows) fills in your username for you.
>   - `~` (Mac/Linux) is short for your home folder.
>   - `-p` (Mac/Linux) tells `mkdir` not to complain if the folder already exists.
> - `cd`: Stands for **C**hange **D**irectory. It moves you into a folder, like double-clicking it. Here it moves you into `Repos` so the repo downloads there.
> - `git clone <url>`: Clone means "make a copy." It downloads the whole repo from GitHub (files, history, and branches) into a new `GitHub-Playground` folder. The first time you push, Git will ask you to sign in to GitHub.
> - `cd GitHub-Playground`: Moves you into the folder you just downloaded, so your next Git commands work on this repo.

### 2. Create a Branch

Always branch from the latest `main`:

```bash
git checkout main
git pull
git checkout -b yourname/your-change
```

> 💡 **What these commands do:**
> - `git checkout main`: Switches your working copy to the `main` branch. This ensures you are branching off the correct base.
> - `git pull`: Fetches the latest changes from GitHub and merges them into your local `main`. This keeps you in sync with any work other club members have already merged.
> - `git checkout -b yourname/your-change`: Creates a new branch and immediately switches to it. The `-b` flag means "create". Naming the branch with your name (e.g. `peter/update-readme`) makes it easy to identify who owns it.

### 3. Make Changes

Edit one of the Markdown files in `student-profiles/` or `sandbox/`, or add a link to `RESOURCES.md`. Follow the instructions in the relevant exercise file under `exercises/`.

> 💡 **Why:** All edits are made on your branch, not on `main`. This keeps the main codebase stable while you work, and lets others review your changes before they are merged.

### 4. Stage and Commit

```bash
git add <file>
git commit -m "docs: describe your change"
```

> 💡 **What these commands do:**
> - `git add <file>`: Stages the specified file, marking it to be included in the next commit. You are telling Git "I want to save this change." Replace `<file>` with the actual file path (e.g. `sandbox/README.md`).
> - `git commit -m "..."`: Records a snapshot of the staged changes in your local Git history with a message describing what you did. Good commit messages make it easy for other students (and future you) to understand the history at a glance.

**Staged the wrong file?** Unstage it before you commit:

```bash
git restore --staged <file>
```

This only removes the file from the staging area. Your edits to the file are kept, so nothing is lost. Run `git status` to confirm it's back under "Changes not staged for commit."

### 5. Push Your Branch

```bash
git push origin yourname/your-change
```

> 💡 **What this command does:** Uploads your local branch and its commits to the remote repository on GitHub (`origin`). Until you push, your commits only exist on your machine. Pushing makes them visible to other club members and enables you to open a Pull Request.

### 6. Open a Pull Request

Go to the repository on GitHub and open a Pull Request from your branch to `main`. Write a clear title and description.

> 💡 **Why:** A Pull Request (PR) is a request to merge your changes into `main`. It gives other club members a chance to look over your work, leave feedback, and catch issues before the changes become part of the shared project.

### 7. Review and Merge

- Request a review from a club eBoard member.
  - Peter Hajj's GitHub username is `phajj`.
- Address any feedback.
- Once approved, merge and delete your branch.

> 💡 **Why:** Reviews give you a second set of eyes on your changes, and they're a friendly way to learn from each other. Deleting the branch after merging keeps the repository tidy and signals the work is complete.
>
> ⚠️ **Class projects:** Never delete a branch in a class project repo. Your instructor may use it for grading.

### 8. Pull the Latest Main

Keep your local `main` up to date after a merge:

```bash
git checkout main
git pull
```

> 💡 **What these commands do:**
> - `git checkout main`: Switches back to your local `main` branch.
> - `git pull`: Downloads and merges the newly merged changes (including your PR) from the remote into your local `main`, so you are ready to branch off again for the next piece of work.

## Exercises

Work through each exercise in order:

1. [Clone and Edit](exercises/exercise-01-clone-and-edit.md)
2. [Branching](exercises/exercise-02-branching.md)
3. [Commit and Push](exercises/exercise-03-commit-and-push.md)
4. [Pull Requests](exercises/exercise-04-pull-request.md)
5. [Merge Conflicts](exercises/exercise-05-merge-conflict.md)
6. [Documentation Update](exercises/exercise-06-documentation-update.md)

## Tips

- Commit often and in small increments.
- Read error messages carefully. Git's output is usually very helpful.
- When in doubt, `git status` and `git log --oneline` are your best friends.

## Getting Help

- Ask questions in our Discord server: https://discord.gg/A4DV423ryu
- Contact Peter Hajj, club president, at hajjp@merrimack.edu, or reach out to any other eBoard member.
