+++
title = "Git 101"
outputs = ["Reveal"]
+++

# Git 101

Version Control System Git Introduction

---

## Overview

- What is a version control system (VCS)?
- How to use git (basics)
- How to push code onto GitHub

---

## What is a Version Control System (VSC)?

---

## What is Git?

---

## Install Homebrew

[How to install Homebrew](https://brew.sh)

```sh
brew install git
```

---

## Configure Git Defaults

```sh
git config --global user.email "you@example.com"
git config --global user.name "Your Name"
```

---

## Initializing a Repository

```sh
mkdir sample-repository
cd sample-repository
git status
git init
git status
```

---

### Comitting Your First File

```sh
touch sample-file.txt
git status
git add sample-file.txt
git commit -m "Add blank sample file"
git status
git log
```

---

## How to Write a Good Commit Message

- Explain why your making the commit (the diff explains what)
- Make your title message concise
- Be consistent (come up with a writing style)

---

## How to Authenticate with GitHub

[GitHub Guide for SSH Key](https://help.github.com/en/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)

---

## How to Add Remote

```sh
git remote add origin {url}
git remote -v
git fetch --all
```

---

## How to Push/Pull

```sh
git push origin master
git pull origin master
```

---

# Q&A

---

# Done
