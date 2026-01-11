---
title: Working locally with git
toc:
  max_depth: 2
---

# Working Locally with Git

This article focuses only on working with Git on your local machine.  
No remote repositories. No GitHub.

The goal is to understand how Git behaves locally and how history is created.

---

## Initializing a repository

Create a new directory and initialize Git.

```bash
mkdir git-local-demo
cd git-local-demo
git init
````

`git init` creates a `.git` directory.
This directory contains the entire Git repository.

---

## Checking repository state

```bash
git status
```

Shows:

* current branch
* staged changes
* unstaged changes
* untracked files

Run this command often.
It tells you exactly where you are.

---

## Creating and tracking a file

Create a file.

```bash
echo "first line" > file.txt
```

Check status.

```bash
git status
```

The file appears as **untracked**.
Git sees the file but is not tracking it yet.

---

## Staging changes

```bash
git add file.txt
```

Moves the file to the staging area.
Staging means “include this in the next commit”.

Check status again.

```bash
git status
```

The file is now staged.

---

## Committing changes

```bash
git commit -m "add initial file"
```

Creates a commit.
A commit records the current state of staged files.

Commits are permanent history entries.

---

## Viewing commit history

```bash
git log
```

Shows:

* commit hash
* author
* date
* commit message

For a compact view:

```bash
git log --oneline
```

---

## Modifying a tracked file

Edit the file.

```bash
echo "second line" >> file.txt
```

Check status.

```bash
git status
```

Git shows the file as **modified**.

---

## Viewing changes before committing

```bash
git diff
```

Shows differences between:

* working directory
* last committed version

This command helps you review changes before staging.

---

## Staging and committing modifications

```bash
git add file.txt
git commit -m "add second line"
```

The new version of the file is now part of history.

---

## Understanding the three areas

Git works with three areas:

* Working directory: files you edit
* Staging area: files prepared for commit
* Repository: committed history

Changes always move in this order:
working → staging → commit

---

## Creating a branch

```bash
git branch feature
```

Creates a new branch called `feature`.

Branches are pointers to commits.
They are lightweight and cheap.

---

## Switching branches

```bash
git checkout feature
```

Moves you to the `feature` branch.

Your files now reflect the state of this branch.

---

## Creating and switching in one step

```bash
git checkout -b experiment
```

Creates a new branch and switches to it.

---

## Making commits on a branch

```bash
echo "branch work" > branch.txt
git add branch.txt
git commit -m "add branch file"
```

This commit exists only on the current branch.

---

## Merging a branch

Switch back to main.

```bash
git checkout main
```

Merge the feature branch.

```bash
git merge feature
```

This combines feature branch changes into main.

If main has not moved, Git performs a fast-forward merge.

---

## Rebasing a branch

Rebase rewrites history to make it linear.

Switch to the branch.

```bash
git checkout feature
```

Rebase onto main.

```bash
git rebase main
```

This moves feature commits on top of main.

Rebase creates new commit hashes.

---

## Key rule for rebase

Rebase only local branches.
Do not rebase branches that others are using.

---

## Comparing merge and rebase locally

* Merge preserves branch history
* Rebase creates a clean, linear history

Both are valid.
The choice depends on team workflow.

---

## Viewing branch history graph

```bash
git log --oneline --graph --all
```

Shows:

* branches
* merges
* commit order

This is the best command to understand Git history.

---

## Summary of local workflow

Typical local workflow:

1. edit files
2. check status
3. review diff
4. stage changes
5. commit

All of this works without internet.

---

This article covers only local Git behavior.
Remote repositories and GitHub come next.

```
