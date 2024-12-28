# Comprehensive Git Notes

## 1. **Git Basics**

### Common Git Commands
- **`git init`**: Initialize a new Git repository in your directory.
  ```bash
  git init
  ```

- **`git clone <repository>`**: Clone an existing remote repository.
  ```bash
  git clone https://github.com/user/repo.git
  ```

- **`git status`**: Check the current state of the working directory and staging area.
  ```bash
  git status
  ```

- **`git add <file>`**: Stage a file for the next commit.
  ```bash
  git add file.txt
  ```

- **`git commit -m "message"`**: Save changes to the local repository with a descriptive message.
  ```bash
  git commit -m "Initial commit"
  ```

- **`git log`**: View commit history.
  ```bash
  git log
  ```

---

## 2. **Branching and Merging**

### Branching
- **`git branch`**: List all branches or create a new branch.
  ```bash
  git branch        # List branches
  git branch feature-1 # Create new branch
  ```

- **`git checkout <branch>`**: Switch to another branch.
  ```bash
  git checkout feature-1
  ```

- **`git switch <branch>`**: Alternative to `checkout` for switching branches.
  ```bash
  git switch feature-1
  ```

- **`git branch -d <branch>`**: Delete a branch.
  ```bash
  git branch -d feature-1
  ```

### Merging
- **Fast-Forward Merge**:
  ```bash
  git checkout main
  git merge feature-branch
  ```

- **Three-Way Merge**:
  Occurs when branches have diverged. A new merge commit is created.
  ```bash
  git checkout main
  git merge feature-branch
  ```

---

## 3. **Rebase**

### Concept
Rebase rewrites the commit history by applying commits from one branch onto another.

### Commands
- **Interactive Rebase**:
  ```bash
  git rebase -i main
  ```

- **Rebase and Continue**:
  ```bash
  git rebase main
  ```

- **Abort Rebase**:
  ```bash
  git rebase --abort
  ```

### Use Case
- To create a cleaner commit history.
- Use rebase in personal feature branches.

---

## 4. **Undoing Changes**

### Stash
- Temporarily save changes without committing.
  ```bash
  git stash
  ```
- Apply stashed changes:
  ```bash
  git stash pop
  ```

### Reset
- Reset the current branch to a specific commit.
  ```bash
  git reset <commit>
  ```

- **Modes**:
  - `--soft`: Keeps changes staged.
  - `--mixed` (default): Unstages changes.
  - `--hard`: Deletes changes.

### Revert
- Undo a specific commit without altering history.
  ```bash
  git revert <commit>
  ```

---

## 5. **Collaboration**

### Remote Repositories
- **Add a Remote**:
  ```bash
  git remote add origin <repository-url>
  ```

- **Push Changes**:
  ```bash
  git push origin main
  ```

- **Pull Changes**:
  ```bash
  git pull origin main
  ```

- **Fetch Changes**:
  ```bash
  git fetch origin
  ```

### Resolving Merge Conflicts
- During a merge conflict:
  1. Edit conflicting files.
  2. Mark resolutions.
  3. Commit changes.

---

## 6. **Advanced Git Commands**

### Cherry-Pick
- Apply a specific commit to another branch.
  ```bash
  git cherry-pick <commit>
  ```

### Bisect
- Find the commit that introduced a bug.
  ```bash
  git bisect start
  ```

### Squash Commits
- Combine multiple commits into one:
  ```bash
  git rebase -i HEAD~n
  ```

### Git Tags
- Add a tag to a commit:
  ```bash
  git tag -a v1.0 -m "Release version 1.0"
  ```

---

## 7. **Common Git Workflows**

### Feature Branch Workflow
1. Create a new branch.
   ```bash
   git checkout -b feature-1
   ```
2. Commit changes to the feature branch.
3. Merge back to `main`:
   ```bash
   git checkout main
   git merge feature-1
   ```

### Rebase Workflow
1. Rebase the feature branch onto `main`:
   ```bash
   git checkout feature-1
   git rebase main
   ```
2. Fast-forward merge to main:
   ```bash
   git checkout main
   git merge feature-1
   ```

### Gitflow Workflow
- Branches:
  - `main`: Stable production code.
  - `develop`: Integration branch for features.
  - `feature`, `hotfix`, `release`: Specific purposes.

---

## 8. **Troubleshooting**

### Undo Last Commit
- Undo while keeping changes:
  ```bash
  git reset --soft HEAD~1
  ```
- Undo and discard changes:
  ```bash
  git reset --hard HEAD~1
  ```

### View Logs and Diffs
- **View Commit History**:
  ```bash
  git log
  ```
- **View Changes**:
  ```bash
  git diff
  ```

### Recover Deleted Branch
- List all references:
  ```bash
  git reflog
  ```
- Restore a branch:
  ```bash
  git checkout -b <branch> <commit>
  ```

---

This guide provides a solid foundation for using Git effectively in individual and team projects. Regularly practice and adapt workflows to fit your project needs!


