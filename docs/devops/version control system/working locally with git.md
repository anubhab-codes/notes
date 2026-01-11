---
title: Working locally with git
toc:
  max_depth: 2
---

Perfect. You’re asking for the **right thing**.
Students need **“run → see → understand”**, not just commands.

Below is **Article 2 rewritten** as a **hands-on lab guide**.
Every command is followed by **what students will see** and **what it means**.

Same tone. More guidance. Still clean Markdown.

---

````md
# Working Locally with Git

This article is a hands-on guide to using Git on your local machine.
All commands work without internet or GitHub.

---

## Step 1: Create a new repository

Create a directory and initialize Git.

```bash
mkdir git-local-demo
cd git-local-demo
git init
````

What you see:

* Git prints: `Initialized empty Git repository`
* A hidden `.git` directory is created

What this means:

* This folder is now a Git repository
* All history will be stored inside `.git`

---

## Step 2: Check repository status

```bash
git status
```

What you see:

* Current branch name (usually `main`)
* Message saying there are no commits yet
* Working tree is clean

What this means:

* Git is active
* Nothing has been added or changed yet

---

## Step 3: Create a file

```bash
echo "first line" > file.txt
```

Run status again.

```bash
git status
```

What you see:

* `file.txt` listed as **untracked**

What this means:

* Git sees the file
* Git is not tracking it yet

---

## Step 4: Stage the file

```bash
git add file.txt
```

Check status again.

```bash
git status
```

What you see:

* `file.txt` under **Changes to be committed**

What this means:

* The file is in the staging area
* It will be included in the next commit

---

## Step 5: Commit the file

```bash
git commit -m "add first file"
```

What you see:

* A commit hash
* Commit message
* Number of files changed

What this means:

* Git recorded a snapshot of the file
* This snapshot is permanent history

---

## Step 6: View commit history

```bash
git log
```

What you see:

* Commit hash
* Author name
* Date
* Commit message

For a shorter view:

```bash
git log --oneline
```

What this means:

* Git is showing the commit history
* Newest commit appears first

---

## Step 7: Modify the file

```bash
echo "second line" >> file.txt
```

Check status.

```bash
git status
```

What you see:

* `file.txt` marked as **modified**

What this means:

* Git detects changes since the last commit
* Changes are not staged yet

---

## Step 8: View file changes

```bash
git diff
```

What you see:

* Lines added with `+`
* Lines removed with `-`

What this means:

* This is the difference between working directory and last commit
* Nothing here is staged yet

---

## Step 9: Stage and commit the change

```bash
git add file.txt
git commit -m "add second line"
```

What you see:

* Another commit created
* New commit hash

What this means:

* File history now has two snapshots

---

## Step 10: Understand Git areas

Git works with three areas:

* Working directory: files you edit
* Staging area: files ready to commit
* Repository: committed history

Files always move in this order.

---

## Step 11: Create a new branch

```bash
git branch feature
```

What you see:

* No output (this is normal)

Check branches.

```bash
git branch
```

What you see:

* `main`
* `feature`

What this means:

* A new branch pointer was created

---

## Step 12: Switch to the branch

```bash
git checkout feature
```

What you see:

* Message saying you switched branches

What this means:

* HEAD now points to `feature`
* Any new commits will belong to this branch

---

## Step 13: Make a commit on the branch

```bash
echo "branch work" > branch.txt
git add branch.txt
git commit -m "add branch file"
```

What you see:

* Commit created on `feature`

What this means:

* This commit exists only on the feature branch

---

## Step 14: Merge the branch

Switch back to main.

```bash
git checkout main
```

Merge feature.

```bash
git merge feature
```

What you see:

* Either a fast-forward message
* Or a merge commit message

What this means:

* Changes from feature are now part of main

---

## Step 15: Rebase the branch

Switch back to feature.

```bash
git checkout feature
git rebase main
```

What you see:

* Rebase completes without error
* Or Git pauses if there is a conflict

What this means:

* Feature commits are replayed on top of main
* Commit hashes change

---

## Step 16: View history as a graph

```bash
git log --oneline --graph --all
```

What you see:

* Commit lines
* Branch pointers
* Merge commits if any

What this means:

* This shows the true shape of history

---

## Key rule to remember

Rebase only local branches.
Never rebase a branch that others are using.

---
All of this works without GitHub.

```
