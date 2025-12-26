## Master GIT from start to End.

### 0. What is Git and GitHub?

- **Git** is a distributed version control system to track changes in source code.
- **GitHub** is a web-based hosting service for Git repositories that supports collaboration.

### 1. Setting up Git

- **git config**

  - `git config --global user.name "Your Name"` Set the global user name
  - `git config --global user.email "your.email@example.com"` Set the global user email
  - `git config user.name "Your Name"` Set the user name for the current repository
  - `git config user.email "your.email@example.com"` Set the user email for the current repository

- **git init**

  - `git init` Initialize a new Git repository

- **git clone**
  - `git clone <repository_url>` Clone a remote repository

### 3. Basic Version Control

- **git status**

  - `git status` Check the status of the working directory

- **git add**

  - `git add <file>` Add a file
  - `git add .` Add all files

- **git commit**

  - `git commit -m "Commit message"` Commit changes
  - `git commit --amend` Amend the last commit to change the commit message and add more files ⭐

- **git diff**

  - `git diff` Show changes
  - `git diff --staged` Show staged changes

- **git restore**

  - `git restore <file>` Restore all changes from a file ⭐
  - `git restore --staged <file>` Restore staged changes ⭐

- **git log**

  - `git log` Show commit history
  - `git log --oneline` Show commit history in one-line format

- **git show**
  - `git show <commit>` Show commit details

### 4. Branching

- **git branch**

  - `git branch` List branches
  - `git branch <new_branch_name>` Create a new branch
  - `git branch -d <branch_name>` Delete a branch ⭐
  - `git branch -D <branch_name>` Delete a branch forcefully ⭐
  - `git branch -m <old_name> <new_name>` Rename a branch ⭐

- **git checkout**

  - `git checkout <branch_name>` Switch to a branch
  - `git checkout -b <new_branch_name>` Create and switch to a new branch
  - `git checkout -` Switch back to the previous branch ⭐

- **git switch**

  - `git switch <branch_name>` Switch to a branch
  - `git switch -` Switch back to the previous branch ⭐
  - `git switch -c <new_branch_name>` Create and switch to a new branch

- **git merge**

  - `git merge <branch_to_merge_into_current_branch>`
  - ⚠️ Merge conflicts may occur. Use `git status`, resolve conflicts, then `git add` and `git commit`.

- **git rebase**

  - `git rebase <base_branch>` Reapply all commits on top of the base branch ⭐
  - `git rebase -i HEAD~3` (Interactive)

- **git cherry-pick**

  - `git cherry-pick <commit_hash>` Cherry-pick picks specific commits and creates a commit onto the current branch

### 5. Working with Remotes

- **git remote add**

  - `git remote add <name> <url>` Add a remote repository

- **git remote -v**

  - `git remote -v` List remote repositories

- **git remote set-url**

  - `git remote set-url origin <new_url>` Update the URL of a remote repository ⭐

- **git remote remove**

  - `git remote remove <name>` Remove a remote repository ⭐

- **git push**

  - `git push` Push changes to a remote repository from just the current branch and only if the upstream branch exists
  - `git push <remote> <branch>` Push changes to a remote repository to specific origin and a specific branch
  - `git push -u origin <branch_name>` publish new branch to remote and set upstream branch ⭐
  - `git push origin --delete <branch_name>` Delete a branch on the remote repository ⭐
  - `git push --all origin` Push all local branches to the remote repository ⭐
  - `git push -f` Force push changes to a remote even if there are conflicts with remote, it will overwrite the remote branch ⭐

- **git pull**

  - `git pull <remote> <branch>` Pull changes from a specific remote origin and branch and merge them into the current branch ⭐
  - `git pull` Pulls changes from your current branch's upstream remote
  - `git pull --rebase` Pulls changes from your remote and rebase the current branch to maintain commit history

- **git fetch**
  - `git fetch <remote>` Fetch changes from a remote repository and does not merge them ⭐

### 6. Undoing Changes

- **git reset**

  - `git reset --soft <commit>` Undo commit, keep changes staged
  - `git reset --mixed <commit>` Undo commit, keep changes unstaged (mixed is default)
  - `git reset --hard <commit>` DANGER: Undo commit, discard everything

# File Operations:

- `git reset <file>` Unstage file
- `git checkout -- <file>` Discard file changes

# Recovery:

- `git reflog ` Find lost commits
- `git reset --hard <commit-sha>` Recover from reflog

- **git revert**
  - `git revert <commit>` Create a new commit that undoes a previous commit and also keep the commit history ⭐
  - `git revert -n <commit>` Undo all changes from a commit, keep the commit history but does not create a new commit ⭐

### 7. Miscellaneous Commands

- **git stash**

  - `git stash` Stash changes
  - `git stash pop` Pop stashed changes and remoeve from stash
  - `git stash apply` Apply stashed changes but does not remove from stash
  - `git stash list` List stashed changes
  - `git stash drop <stash_id>` Discard stashed changes
  - `git stash -u` Stash untracked files
  - `git stash clear` Discard all stashed changes

- **git tag**

  - `git tag <tagname>` adds to tag to that commit that stays with it permanently
  - `git tag -d <tagname>` delete tag
