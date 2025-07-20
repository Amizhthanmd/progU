# Git Commands

This document covers essential Git commands, progressing from **basic** to **advanced** usage, along with useful explanations.

---

## Getting Started

- **Initialize Repository**

  - `git init`  
    _Start a new Git repository in the current directory._

- **Clone Repository**
  - `git clone <url>`  
    _Clone a remote repository into a new directory._

---

## Configuration

- **Set Username**

  - `git config --global user.name "Your Name"`

- **Set Email**

  - `git config --global user.email "you@example.com"`

- **List Configurations**
  - `git config --list`

---

## Basic Snapshotting

- **Check Status**

  - `git status`  
    _Show the working directory status._

- **Track New File**

  - `git add <file>`

- **Stage All Files**

  - `git add .` or `git add -A`

- **Commit Changes**

  - `git commit -m "commit message"`

- **Modify Last Commit**
  - `git commit --amend`

---

## Branching & Merging

- **List Branches**

  - `git branch`

- **Create New Branch**

  - `git branch <branchname>`

- **Switch Branch**

  - `git checkout <branchname>`
  - `git switch <branchname>` _(modern alternative)_

- **Create & Switch**

  - `git checkout -b <branchname>`
  - `git switch -c <branchname>`

- **Merge Branch**

  - `git merge <other-branch>`

- **Delete Branch**
  - `git branch -d <branchname>`

---

## Remote Repositories

- **Show Remotes**

  - `git remote -v`

- **Add Remote**

  - `git remote add origin <url>`

- **Push to Remote**

  - `git push origin <branchname>`

- **Push All Branches**

  - `git push --all origin`

- **Pull From Remote**

  - `git pull origin <branchname>`

- **Fetch Changes**
  - `git fetch`

---

## Stashing & Cleaning

- **Stash Current Changes**

  - `git stash`
  - `git stash save "description"`

- **List Stashes**

  - `git stash list`

- **Apply Stash**

  - `git stash apply`

- **Drop Stash**

  - `git stash drop`

- **Clean Untracked Files**
  - `git clean -f`
  - `git clean -fd` _(include directories)_

---

## History & Inspection

- **Show Commit Log**

  - `git log`
  - `git log --oneline --graph --all` _(compact, tree view)_

- **Show File History**

  - `git log <file>`

- **Show Diff**

  - `git diff` _(unstaged changes)_
  - `git diff --staged` _(staged changes)_

- **Show Blame**
  - `git blame <file>`  
    _Show authorship per line._

---

## Rewriting History

- **Interactive Rebase**

  - `git rebase -i HEAD~N`  
    _(modify last N commits interactively)_

- **Reset**

  - `git reset --soft <commit>`
  - `git reset --hard <commit>`  
    _(Dangerous: Erases local changes!)_

- **Revert Commit**
  - `git revert <commit>`

---

## Advanced Commands

- **Cherry-Pick Commit**

  - `git cherry-pick <commit>`

- **Squash Commits**

  - During interactive rebase, mark unwanted commits as `squash`.

- **Bisect: Debugging**

  - `git bisect start`
  - `git bisect good`
  - `git bisect bad`

- **Show Reflog**

  - `git reflog`  
    _Show history of branch HEADs and stash._

- **Submodules**
  - `git submodule add <url> <path>`
  - `git submodule update --init --recursive`

---

## Extra Tips

- **View Aliases**

  - `git config --get-regexp alias`

- **List Ignored Files**

  - `git ls-files --others -i --exclude-standard`

- **Patch Stage**
  - `git add -p`  
    _Interactively stage chunks of changed files._

---

For more details and the latest updates, consult the official Git documentation or use `git help <command>`.
