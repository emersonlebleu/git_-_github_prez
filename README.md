# Git & GitHub Overview

## Git

Documentation:  
[git Docs](https://git-scm.com/docs)

### Intro
Git is a **distributed version control system**.  
- **Repository (Repo)**: A directory tracked by Git, where files and their changes are recorded.  
- **Fast Features**  
  - Tracks changes to files over time.  
  - Facilitates collaboration among multiple contributors.  
  - Resolves conflicts when multiple people work on the same codebase or project.  

---

### `git init`
**Purpose**: Initialize a Git repository in a directory.  
- Creates a `.git` folder that stores all the information about the version control.  
- Use this to start tracking changes in your project.  

**Command**:
```bash
git init
```

---

### `.gitignore` & `README.md`
**.gitignore**: Specify files or directories that Git should ignore.  
- Prevents large, sensitive, or unnecessary files (e.g., `node_modules`, `.env`) from being tracked.  

**Example**:
```
node_modules/
.env
*.log
```
**README.md**: This will be the markdown page that people see at the root of your repo on github. 
- Typically used as background or as getting started documentation 

---

### **`git status`**
**Purpose**: Shows the current state of your working directory and staging area.  
- **What it displays**:
  - Tracked files with changes.
  - Untracked files.
  - Files staged for the next commit.
- **Use case**: To check what changes have been made and their current status.
- **Command**:
  ```bash
  git status
  ```
---

### `git add`
**Purpose**: Stage changes for the next commit.  
- Prepares specific files or changes to be saved into the Git history.

**Command**:
```bash
git add <file>      # Add a specific file
git add .           # Add all changes in the directory
```

---

### `git commit`
**Purpose**: Save a snapshot of the current state of your project.  
- Creates a record in the Git history.  

**Command**:
```bash
git commit -m "Your commit message"
```
---

### **`git diff`**
**Purpose**: Shows differences between files or commits.  
- **What it does**:
  - Displays changes that have not been staged (`git diff`).
  - Displays staged changes ready for commit (`git diff --staged`).
  - Can compare specific commits or branches.
- **Use case**:
  - To review changes before committing them.
  - To understand differences between branches or commits.
- **Commands**:
  ```bash
  git diff             # Unstaged changes
  git diff --staged    # Staged changes
  git diff <branch1> <branch2>  # Compare two branches
  ```
---