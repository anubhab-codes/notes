---
title: What is Git?
toc:
  max_depth: 2
---

# Git Introduction

Git is a version control system.  
It tracks changes to files over time and records how a codebase evolves.

Instead of storing only the latest version of a file, Git keeps a history of changes.
This history allows teams to understand what changed, when it changed, and who changed it.

Before version control, teams shared code by copying folders such as:
`project`, `project_final`, `project_final_v2`.

This approach breaks very quickly in real work.
Files get overwritten, changes are lost, and parallel work becomes unsafe.

Git exists to solve this problem in a structured and repeatable way.

---

## What Git actually tracks

Git does not track projects or folders as a single unit.  
It tracks individual files and their state at specific points in time.

At those points, Git takes a snapshot of the files and stores it.
Each snapshot is called a **commit**.

A commit contains:
- the exact state of files at that moment
- the author of the change
- the time the change was recorded
- a reference to the previous commit

Commits are linked together in order.
This linked structure forms the complete history of the project.

---

## Git is not GitHub

Git and GitHub are often treated as the same thing.  
They are not.

Git is a tool.
GitHub is a service.

Git runs on your local machine and manages file history.
GitHub runs on remote servers and hosts Git repositories.

You can use Git without GitHub.
You cannot use GitHub without Git.

If GitHub is unavailable, your local Git repository continues to work normally.

---

## Why Git was needed

Before Git, centralized tools like SVN were widely used.

In a centralized version control system:
- one central server stores the full history
- developers work with a partial copy
- most actions require network access

If the server is slow or unavailable, development slows down or stops.
This model does not scale well for large or distributed teams.

Git was created to remove this dependency on a central server.

---

## Why Git is called a distributed version control system

Git is distributed because every clone is a full repository.

When you clone a Git repository, you receive:
- all commits
- all branches
- the complete history

Your local machine is not just a client.
It holds the same information as the remote repository.

Remote repositories are simply additional copies used for sharing and collaboration.

---

## What distributed means in real work

Because every developer has the full history locally:
- you can commit changes without internet access
- you can inspect past changes at any time
- you can experiment without affecting others

Local work is a first-class concept in Git.
Network access improves collaboration, but it is not required to work.

---

## A very short history of Git

Git was created by Linus Torvalds in 2005 to manage the Linux kernel.

The Linux kernel has thousands of contributors working in parallel.
Existing tools were too slow and fragile to handle this scale.

Git was designed with clear priorities:
- speed for common operations
- reliability and data integrity
- support for parallel development

These design decisions still shape how Git behaves today.

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
- enables collaboration
- adds features such as pull requests and reviews

GitHub does not change how Git works internally.
It builds collaboration tools on top of Git.

---

## Why this distinction matters

Many Git problems come from confusing Git with GitHub.

Common examples include:
- rebasing branches that others already use
- force-pushing without understanding the impact
- assuming project history exists only on GitHub

Understanding Git first avoids these mistakes.

Git manages history.  
GitHub manages collaboration.
