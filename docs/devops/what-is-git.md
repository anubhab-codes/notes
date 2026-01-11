---
title: What is Git?
toc:
  max_depth: 2
---

# Git Introduction

Git is a version control system.

It tracks changes to files over time.  
Not just the current version of the code, but how the code reached its current state.

Before version control, teams shared code by copying folders:
`project`, `project_final`, `project_final_v2`.

This approach breaks very quickly:
- Files get overwritten
- Changes get lost
- Multiple people edit the same file without knowing

Git exists to solve this problem in a structured and reliable way.

---

## What Git actually tracks

Git does not track projects or folders as a whole.  
It tracks individual files and their state.

At specific points in time, Git takes a snapshot of the files and stores it.  
Each snapshot is called a commit.

A commit contains:
- the state of files at that moment
- who made the change
- when the change was made
- a reference to the previous commit

Commits are linked together.  
This chain of commits represents the full history of the project.

---

## Git is not GitHub

This confusion causes many beginner mistakes.

Git is a tool.  
GitHub is a service.

Git runs on your local machine.  
GitHub runs on remote servers.

You can use Git without GitHub.  
You cannot use GitHub without Git.

If GitHub is unavailable, your local Git repository still works normally.

---

## Why Git was needed

Before Git, tools like SVN were widely used.

SVN is a centralized version control system.

In a centralized system:
- one central server stores the complete history
- developers get a working copy, not the full repository
- most operations require network access

If the server is slow or down, development slows down or stops.

Git was designed to remove this dependency.

---

## Why Git is called a distributed version control system

In Git, every clone is a full repository.

When you clone a Git repository:
- you get all commits
- you get all branches
- you get the complete history

Your local machine is not just a client.  
It is a complete and independent copy of the repository.

This is what distributed means in Git.

Remote repositories are just additional copies of the same repository.

---

## What distributed means in real work

Because every developer has the full history:
- you can commit changes without internet access
- you can inspect past changes locally
- you can experiment without affecting others

Local work is a first-class concept in Git.  
Network access is useful, but not mandatory.

---

## A very short history of Git

Git was created by Linus Torvalds in 2005.

It was built to manage the Linux kernel.

The Linux kernel has:
- thousands of contributors
- constant parallel development
- no single central gatekeeper for changes

Existing tools were too slow and fragile for this scale.

Git was designed to be:
- fast
- reliable
- resistant to corruption
- capable of handling parallel work

These design goals still influence Git today.

---

## Git vs GitHub

Git:
- is a version control system
- runs locally
- tracks file history
- works offline
- creates commits and branches

GitHub:
- hosts Git repositories
- provides a web interface
- enables collaboration between teams
- adds features like pull requests and reviews

GitHub does not change how Git works internally.  
It builds collaboration tools on top of Git.

---

## Why this distinction matters

Many problems happen when Git and GitHub are treated as the same thing.

Examples include:
- rebasing branches already shared with others
- force-pushing without understanding impact
- assuming history exists only on GitHub

Understanding Git first prevents these mistakes.

Git manages history.  
GitHub manages collaboration.
