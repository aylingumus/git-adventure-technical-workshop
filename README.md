# 🛠 Git Adventure Workshop Manual for Beginners

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
    - [👀 `git diff`](#-git-diff)
  - [7. Git Branch Naming Conventions](#7-git-branch-naming-conventions)
  - [8. Practicing Basic Git Commands](#8-practicing-basic-git-commands)
  - [9. Merge Conflicts: What & Why](#9-merge-conflicts-what--why)
  - [10. 🔥 CHAOS MODE: Practicing Merge Conflicts](#10--chaos-mode-practicing-merge-conflicts)
  - [11. Bonus Topics](#11-bonus-topics)
    - [`.gitignore`](#gitignore)
    - [Undoing changes](#undoing-changes)
    - [GitHub Desktop](#github-desktop)
    - [Git Fork](#git-fork)
    - [Conventional Commits](#conventional-commits)
  - [12. Resources](#12-resources)

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
- 👯 **Collaborate easily:** Work with others without overwriting each other's code.
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

Retrieves updates from the remote repository but doesn't change your working files.

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

### 👀 `git diff`

Shows the differences between files, commits, or branches.

**See unstaged changes:**
```bash
git diff
```

**See staged changes:**
```bash
git diff --staged
```

**Compare two branches:**
```bash
git diff main..feature-branch
```

**Compare specific files:**
```bash
git diff filename.txt
```

**Example output:**
```diff
- This line was removed
+ This line was added
  This line stayed the same
```

---

## 7. Git Branch Naming Conventions

Good branch names make collaboration easier and projects more organized!

### Common Patterns

**Feature branches:**
```bash
feature/user-authentication
feature/shopping-cart
feat/add-payment-integration
```

**Bug fixes:**
```bash
bugfix/login-error
fix/header-alignment
hotfix/critical-security-patch
```

**Experiments:**
```bash
experiment/new-ui-design
spike/performance-testing
```

**Releases:**
```bash
release/v1.2.0
release/2024-spring-update
```

### Best Practices

✅ **DO:**
- Use lowercase letters
- Use hyphens to separate words
- Be descriptive but concise
- Include ticket numbers if you have them: `feature/PROJ-123-user-profile`

❌ **DON'T:**
- Use spaces: `feature/new feature` ❌
- Use special characters: `feature/new@feature` ❌
- Make them too long: `feature/this-is-a-very-long-branch-name-that-describes-everything` ❌

---

## 8. Practicing Basic Git Commands

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

## 9. Merge Conflicts: What & Why

A merge conflict happens when Git can't automatically merge changes. This usually occurs when:

- Two people edit the same line of a file.
- A file is deleted in one branch and edited in another.

You'll see conflict markers in the file:

```text
<<<<<<< HEAD
This is your change
=======
This is the incoming change
>>>>>>> branch-name
```

You must manually choose or combine the correct content, then stage and commit the file.

---

## 10. 🔥 CHAOS MODE: Practicing Merge Conflicts

Time to embrace the chaos! We'll create some fun merge conflicts on purpose.

### The "This is Fine" Meme Exercise

We'll create a collaborative story about our favorite "This is Fine" dog meme, where everyone contributes different versions of what's happening in the burning room.

![This is fine meme](images/this-is-fine-meme.jpg)

### What You'll Do

1. **Follow instructor guidance** to create branches and make changes
2. **Experience merge conflicts** in a safe environment
3. **Learn to resolve conflicts** step by step
4. **Practice using git diff** to understand what changed

### During the Exercise

Your instructors will guide you through:
- Creating properly named branches
- Making conflicting changes to the same files
- Using `git diff` to see what's different
- Resolving conflicts when they occur
- Understanding conflict markers like:

```text
<<<<<<< HEAD
Your changes
=======
Someone else's changes
>>>>>>> branch-name
```

### Remember

- Conflicts are learning opportunities, not disasters!
- Take your time to understand what's happening
- Ask questions if you're unsure
- Every developer deals with merge conflicts regularly

---

## 11. Bonus Topics

### `.gitignore`

Prevents tracking of certain files (e.g., log files, node_modules). You can add a .gitignore file to your code.

### Undoing changes

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

### Git Fork

**What is a Fork?**
A fork is your own copy of someone else's repository on GitHub. Think of it like making a photocopy of a book so you can write notes in it without affecting the original.

**Why do we fork?**
- You want to contribute to someone else's project
- You don't have direct write access to the original repository
- You want to experiment with changes safely
- You want to use someone's project as a starting point for your own

**How to fork:**
1. Go to the repository on GitHub
2. Click the "Fork" button in the top-right corner
3. GitHub creates a copy in your account
4. Clone your forked version to work locally

```bash
git clone https://github.com/YOUR_USERNAME/forked-repo.git
```

GitHub Desktop is a graphical user interface (GUI) for Git that makes it easier for beginners to use Git without needing to type commands in the terminal.

#### Key Features
- Clone repositories with a click
- View changes and commits visually
- Drag-and-drop file staging
- Resolve merge conflicts with an interface

### GitHub Desktop
**How to Get Started:**
GitHub Desktop is a graphical user interface (GUI) for Git that makes it easier for beginners to use Git without needing to type commands in the terminal.

#### Key Features
- Clone repositories with a click
- View changes and commits visually
- Drag-and-drop file staging
- Resolve merge conflicts with an interface

How to Get Started:
- Download: [desktop.github.com](https://desktop.github.com/download/) (Available for macOS and Windows)
- Install and log in with your GitHub account

### Conventional Commits

Conventional Commits is a specification for commit messages that makes them more readable and useful for automation.

#### Format
```
<type>[optional scope]: <description>

[optional body]

[optional footer(s)]
```

#### Types
- `feat:` - A new feature
- `fix:` - A bug fix
- `docs:` - Documentation only changes
- `style:` - Changes that don't affect code meaning (formatting, etc.)
- `refactor:` - Code change that neither fixes a bug nor adds a feature
- `test:` - Adding missing tests
- `chore:` - Changes to build process or auxiliary tools

#### Examples
```bash
git commit -m "feat: add user authentication"
git commit -m "fix: resolve login button alignment issue"
git commit -m "docs: update README with installation steps"
git commit -m "style: format code according to prettier rules"
```

#### Benefits
- Easier to read commit history
- Automatic changelog generation
- Easier to understand what changed
- Better collaboration in teams

---

## 12. Resources

[Git Official Documentation](https://git-scm.com/doc)

[GitHub Docs](https://docs.github.com/en)

[Learn Git Branching (interactive)](https://learngitbranching.js.org/)

[Oh My Git! – Git card game](https://ohmygit.org/)

[FreeCodeCamp Git Guide](https://www.freecodecamp.org/news/git-and-github-for-beginners/)

[Git Diff Command Guide](https://www.freecodecamp.org/news/git-diff-command/)

[Atlassian Git Tutorials](https://www.atlassian.com/git/tutorials/using-branches/merge-conflicts)

[Git Branch Naming Conventions](https://medium.com/@abhay.pixolo/naming-conventions-for-git-branches-a-cheatsheet-8549feca2534)

[Conventional Commits](https://medium.com/@BradleyOThompson/conventional-commits-ffad83dfe561)