# 🛠 Git Workshop Manual for Beginners

## 📌 Table of Contents

  - [1. Installing Git](#1-installing-git)
  - [2. What is Git?](#2-what-is-git)
  - [3. Why is Git Important for Developers?](#3-why-is-git-important-for-developers)
  - [4. Terminal or Command Line Basics](#4-terminal-or-command-line-basics)
  - [5. What Are Branches?](#5-what-are-branches)
  - [6. Basic Git Commands](#6-basic-git-commands)
    - [✅ `git clone`](#-git-clone)
    - [📡 `git fetch`](#-git-fetch)
    - [🔄 `git pull`](#-git-pull)
    - [➕ `git add`](#-git-add)
    - [📝 `git commit`](#-git-commit)
    - [⬆️ `git push`](#️-git-push)
  - [7. Practicing Basic Git Commands](#7-practicing-basic-git-commands)
  - [8. Merge Conflicts: What \& Why](#8-merge-conflicts-what--why)
  - [9. Practicing Merge Conflicts](#9-practicing-merge-conflicts)
  - [10. Bonus:](#10-bonus)
    - [`.gitignore`](#gitignore)
    - [Undoing changes:](#undoing-changes)
    - [GitHub Desktop](#github-desktop)
  - [11. Resources](#11-resources)

---
## 1. Installing Git

Create an account on [Github.com](https://www.github.com).
To install Git, please go to [Git downloads](https://git-scm.com/downloads). 

---

## 2. What is Git?

**Git** is a version control system that tracks changes in your code and allows multiple people to collaborate on projects. It records what you did and when, so you can go back if needed.

Think of it like a **save system for your code** — with branching and multiplayer.

---

## 3. Why is Git Important for Developers?

- 🕒 **Track history:** Revert to previous versions.
- 👯 **Collaborate easily:** Work with others without overwriting each other’s code.
- 🌐 **Industry standard:** Used in nearly every professional software project.
- 🔁 **Branching and merging:** Test features without affecting the main project.

---

## 4. Terminal or Command Line Basics

### What is the Terminal?

The Terminal is a simple, text-based way to talk to your computer. Instead of clicking buttons, you type commands to tell it what to do, like opening files, running programs, or using tools like Git. 

### Opening the Terminal

- **macOS:** Use Spotlight → search "Terminal"
- **Windows:** Use Command Prompt, PowerShell, or Git Bash
- **Linux:** Press `Ctrl + Alt + T`

### Common Commands

| Command     | Description                        |
|-------------|------------------------------------|
| `pwd`       | Print working directory path       |
| `ls`        | List files and directories         |
| `cd`        | Change directory                   |
| `mkdir`     | Create a new directory             |
| `touch`     | Create a new empty file            |
| `rm`        | Remove a file or directory         |
| `clear`     | Clear the terminal screen          |

### Navigating the File System

- `cd folder_name` – move into a folder  
- `cd ..` – go back one directory  
- `ls -a` – list all files including hidden ones  
- Use `Tab` to auto-complete file and folder names

### Editing Files with CLI Tools

- `nano filename.txt` – open file in Nano text editor  
- `vim filename.txt` – open file in Vim (advanced)  
- `code .` – open current folder in VS Code (requires VS Code CLI installed)

---

## 5. What Are Branches?

![image](https://github.com/user-attachments/assets/2dce9460-c146-4da5-8b54-2c2197aaa174)

**Branches** are like alternate timelines of your project.

They let you:

- Work on features independently from the main code.
- Experiment without breaking the live version.
- Collaborate by giving each developer their own "playground."

### Example

You're working on a website and want to add a "Contact Us" page. You can create a branch:

```bash
git checkout -b contact-page
```

Now you're working in a separate version of the project. You can make changes, commit them, and merge them back into the main branch when you're ready.

### Common Branch Commands

Create and switch to a new branch:

```bash
git checkout -b new-feature
```

Switch between branches:

```bash
git checkout main
```

List all branches:

```bash
git branch
```

---

## 6. Basic Git Commands

### ✅ `git clone`

Copies a repository from a remote location to your local machine.

```bash
git clone https://github.com/example/repo.git
```

### 📡 `git fetch`

Retrieves updates from the remote repository but doesn’t change your working files.

```bash
git fetch
```

### 🔄 `git pull`

Fetches changes and merges them into your current branch.

```bash
git pull
```

### ➕ `git add`

Stages changes (adds them to the "to be committed" list).

```bash
git add file.txt

# or all files
git add .
```

### 📝 `git commit`

Saves your staged changes with a message.

```bash
git commit -m "Added new feature"
```

### ⬆️ `git push`

Sends your committed changes to the remote repository.

```bash
git push
```

---

## 7. Practicing Basic Git Commands

### Setup

Create a GitHub repository and clone it locally:

```bash
git clone https://github.com/YOUR_USERNAME/git-practice.git
cd git-practice
```

### Task

Create a new file: hello.txt

```bash
echo "Hello Git!" > hello.txt
```

Stage, commit, and push:

```bash
git add hello.txt
git commit -m "Add hello.txt"
git push
```

---

## 8. Merge Conflicts: What & Why

A merge conflict happens when Git can’t automatically merge changes. This usually occurs when:

- Two people edit the same line of a file.
- A file is deleted in one branch and edited in another.

You’ll see conflict markers in the file:

```text
<<<<<<< HEAD
This is your change
=======
This is the incoming change
>>>>>>> branch-name
```

You must manually choose or combine the correct content, then stage and commit the file.


---

## 9. Practicing Merge Conflicts

### Steps

1. Clone a shared repo or use a class repo.
2. Create a file:

```bash
echo "Hello from main" > greeting.txt
git add greeting.txt
git commit -m "Add greeting.txt"
git push
```

3. Create a new branch and change the file:

```bash
git checkout -b feature-branch
echo "Hello from feature" > greeting.txt
git commit -am "Change greeting in feature"
git push --set-upstream origin feature-branch
```

4. Go back to main and make a different change:

```bash
git checkout main
echo "Hello from main branch" > greeting.txt
git commit -am "Different change in main"
git push
```

5. Try to merge the feature branch:

```bash
git merge feature-branch
```

Git will show a conflict. Open the file, fix the conflict, and complete the merge:

```bash
git add greeting.txt
git commit -m "Resolve merge conflict"
```

---

## 10. Bonus:

Other Important Git Topics

### `.gitignore`

Prevents tracking of certain files (e.g., log files, node_modules). You can add a .gitignore file to your code.

### Undoing changes:

Discard local changes:

```bash
git checkout -- filename
```

Unstage files:

```bash
git reset HEAD filename
```

Revert commit:

```bash
git revert <commit-id>
```

Stashing work: Save unfinished work without committing.

```bash
git stash
git stash pop
```

Viewing history:

```bash
git log
```

See differences:

```bash
git diff
```

## GitHub Desktop

GitHub Desktop is a graphical user interface (GUI) for Git that makes it easier for beginners to use Git without needing to type commands in the terminal.

### Key Features
- Clone repositories with a click
- View changes and commits visually
- Drag-and-drop file staging
- Resolve merge conflicts with an interface

How to Get Started:
- Download: [desktop.github.com](https://desktop.github.com/download/) (Available for macOS and Windows)
- Install and log in with your GitHub account

---

## 11. Resources

[Git Official Documentation](https://git-scm.com/doc)

[GitHub Docs](https://docs.github.com/en)

[Learn Git Branching (interactive)](https://learngitbranching.js.org/)

[Oh My Git! – Git card game](https://ohmygit.org/)
