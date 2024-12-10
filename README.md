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

### `git checkout` `git branch` `git switch`
**Purpose**: Work on different parts of the project without affecting the main codebase.  
- `git branch`: Create, list, or delete branches.  
- `git checkout` or `git switch`: Switch between branches.  

**Commands**:
```bash
git branch <branch_name>        # Create a new branch
git checkout <branch_name>      # Switch to the branch (legacy)
git switch <branch_name>        # Modern equivalent to checkout
```
---

## GitHub

Documentation:  
[github Docs](https://docs.github.com/en)

GitHub is a **cloud-based platform** for hosting Git repositories.  
- Allows collaboration by providing a central repository.  
- Includes additional tools like Issues, Pull Requests, and Project Boards.  

There are alternatives, such as [Bitbucket](https://bitbucket.org/product/).

---

### Create an Empty Repository

- To link an existing local repository, ensure the remote repository is created without any initial files (e.g., README, license, or .gitignore).

---

### `git remote add`
**Purpose**: Link a local repository to a remote repository.  

**Command**:
```bash
git remote add origin <repository_url>
```

**Explanation**:  
- `origin`: The default name for the remote repository. You can use a different name if desired.
- `<repository_url>`: The URL of the remote repository (e.g., HTTPS or SSH).

**Common Usage**:
- After creating a new repository locally, use this command to associate it with a remote repository.

**Verify**:
```bash
git remote -v
```
---

### `git push`
**Purpose**: Upload local changes to a remote repository.  

**Command**:
```bash
git push origin <branch>
```

---

### `git merge`

**Purpose**:  
Combines changes from one branch into another. Typically used to integrate changes from a feature branch into the main branch. Also can be used to merge another team member’s branch into your own to stay up-to-date.

1. Switch to the branch you want to merge into:
   ```bash
   git checkout main
   ```

2. Merge the other branch into it:
   ```bash
   git merge feature-branch
   ```

3. Push the changes to the remote repository:
   ```bash
   git push origin main
   ```

#### Conflict Resolution
   - If there are conflicting changes, Git will pause the merge and mark conflicts in the affected files.
   - You must manually resolve conflicts, then complete the merge with:
     ```bash
     git add <resolved_file>
     git commit
     ```

#### **Alternatives**
- **`git rebase`**: Rewrites commit history instead of creating a merge commit. Use it for linearizing history but avoid on shared branches.
- **`git cherry-pick`**: Use to pick specific commits from another branch instead of merging the entire branch.

---

### `git pull`
**Purpose**: Fetch changes from the remote repository and integrate them into the local repository.  

**Command**:
```bash
git pull origin <branch>
```

---

### `git clone`
**Purpose**: Copy a remote repository to your local machine.  

**Command**:
```bash
git clone <URL>
```
