Git
====

## Table of Contents
- [Git Docs - Learning](#git-docs---learning)
- [Markdown - Learning](#markdown---learning)
- [Git Config](#git-config)
- [Git Login](#git-login)
- [Git Init](#git-init)
- [Git Log](#git-log)
- [Git Status](#git-status)
- [Git Add](#git-add)
- [Git Commit](#git-commit)
- [Git Branch](#git-branch)
- [Git Switch](#git-switch)
- [Git Checkout](#git-checkout)
- [Difference between git switch and git checkout](#difference-between-git-switch-and-git-checkout)
- [Git Merge](#git-merge)
- [Git Rebase](#git-rebase)
- [Git Cherry-pick](#git-cherry-pick)
- [Git Diff](#git-diff)
- [Git Stash](#git-stash)
- [Git Restore](#git-restore)
- [Git Reset](#git-reset)
- [Git Revert](#git-revert)
- [Git Clone](#git-clone)
- [Git Remote](#git-remote)
- [Git Push](#git-push)
- [Git Fetch](#git-fetch)
- [Git Pull](#git-pull)
- [Difference between git pull and git fetch](#difference-between-git-pull-and-git-fetch)
- [Git Tag](#git-tag)
- [Semantic Versioning](#how-semantic-versioning-works)
- [Git Reflog](#git-reflog)
- [Git Bisect](#git-bisect)
- [Other Git Commands](#other-git-commands)
- [Git Aliases](#git-aliases)
- [Git Blame](#git-blame)
- [Git Clean](#git-clean)
- [Git Submodule](#git-submodule)
- [Git Archive](#git-archive)

### [Git Docs - Learning](https://git-scm.com/docs)
### [Markdown - Learning](https://www.markdownguide.org/basic-syntax/)
### [Markdown - More Information](https://daringfireball.net/projects/markdown/)

## Git Config
[Config Git](https://git-scm.com/docs/git-config)
```bash
git config --list # List all git configurations
git config --global --list # List all global git configurations
git config --local --list # List all local git configurations
git config --global core.editor "code --wait" # Set the default editor
git config --global core.pager "less" # Set the default pager
git config --global core.autocrlf true # Set the default line ending
git config --global core.ignorecase true # Set the default case sensitivity
git config --global core.excludesfile ~/.gitignore_global # Set the default global gitignore file
git config --global color.ui true # Set the default color
git config --global alias.st "status" # Set the default alias
git config --global alias.co "checkout" # Set the default alias
git config --global alias.ci "commit" # Set the default alias
git config --global alias.br "branch" # Set the default alias
```

## Git Login
```bash
git config --global user.name "Your Name" # Set user name
git config user.name # Get user name

git config --global user.email "" # Set user email
git config user.email # Get user email
```

## Git Init
- [git-init](https://git-scm.com/docs/git-init)
```bash
git init # Initialize a git repository

```

## Git Log
[Git Log - Learning](https://git-scm.com/docs/git-log)
```bash
git log # Show commit logs
git log --oneline # Show commit logs in one line
git log --oneline --graph # Show commit logs in one line with graph
git log --abbrev-commit # Show commit logs with abbreviated commit
```

## Git Status
[Git Status - Learning](https://git-scm.com/docs/git-status)
```bash
git status # Show the working tree status
git status -s # Show the working tree status in short format
git status -sb # Show the working tree status in short format with branch
git status -sb -u # Show the working tree status in short format with branch and untracked files
```

## Git Add
[Git Add - Learning](https://git-scm.com/docs/git-add)
```bash
git add . # Add all files to the staging area
git add <file> # Add a file to the staging area
git add <file1> <file2> # Add multiple files to the staging area
git add <dir> # Add a directory to the staging area
git add -A # add all files to the staging area -A is equivalent to --all
git add -f # Add files to the staging area interactively -f is equivalent to --force
```

## Git Commit
[Git Commit - Learning](https://git-scm.com/docs/git-commit)
```bash
git commit -m "Message" # Commit changes with a message
git commit -am "Message" # Add all files to the staging area and commit changes with a message
git commit --amend # Amend the last commit
git commit --amend -m "New Message" # Amend the last commit with a new message
```

## Git Branch
[Git Branch - Learning](https://git-scm.com/docs/git-branch)
```bash
git branch # List all branches
git branch -a # List all branches including remote branches
git branch -r # List all remote branches
git branch <branch> # Create a new branch
git branch -d <branch> # Delete a branch
git branch -m <branch> # Rename a branch
git branch -u <branch> <remote/branch> # Set up a tracking branch
git branch -vv # Show tracking branches

# Rename a branch
git branch -m <old-branch> <new-branch>
git branch -m <new-branch>
git branch -v # Show the last commit on each branch
```

## Git Switch
[Git Switch - Learning](https://git-scm.com/docs/git-switch)
```bash	
git switch <branch> # Switch to a branch
git switch -c <branch> # Create a new branch and switch to it
git switch -d <branch> # Delete a branch
git switch -c <branch> <remote/branch> # Create a new branch and switch to it with a tracking branch
git switch -c <branch> <remote/branch> --force # Create a new branch and switch to it with a tracking branch and force

# Delete a branch
git switch -d <branch> # Delete a branch
git switch - return to the previous branch
git switch -D <branch> # Delete a branch with force
git switch -D -r <branch> # Delete a remote branch with force
git switch -D -a <branch> # Delete a branch and its tracking branch with force
git switch -d -a -r -f <branch> # Delete a remote branch and its tracking branch with force
```

## Git Checkout
[Git Checkout - Learning](https://git-scm.com/docs/git-checkout)
```bash
git checkout <branch> # Switch to a branch
git checkout -b <branch> # Create a new branch and switch to it
git checkout -b <branch> <remote/branch> # Create a new branch and switch to it with a tracking branch
git checkout -b <branch> <remote/branch> --force # Create a new branch and switch to it with a tracking branch and force
git checkout -d <branch> # Delete a branch
git checkout HEAD~1 # Switch to the previous commit
git checkout HEAD <file> # Discard changes in a file
git checkout -- <file> # Discard changes in a file
git checkout --track <remote/branch> # Create a new branch and switch to it with a tracking branch
git checkout <tag> # Switch to a tag
```

### Difference between git switch and git checkout
```markdown
The `git switch` command was introduced in Git 2.23 as a simpler and more intuitive way to switch branches compared to `git checkout`. Here are the key differences:

- **Purpose**:
    - `git switch`: Specifically designed for switching branches.
    - `git checkout`: A more general-purpose command that can switch branches, restore working tree files, and more.

- **Syntax**:
    - `git switch <branch>`: Switches to the specified branch.
    - `git checkout <branch>`: Switches to the specified branch.

- **Creating a New Branch**:
    - `git switch -c <branch>`: Creates a new branch and switches to it.
    - `git checkout -b <branch>`: Creates a new branch and switches to it.

- **Tracking Branch**:
    - `git switch -c <branch> <remote/branch>`: Creates a new branch, sets up tracking, and switches to it.
    - `git checkout -b <branch> <remote/branch>`: Creates a new branch, sets up tracking, and switches to it.

- **Safety**:
    - `git switch` is considered safer and less error-prone for branch switching operations.
    - `git checkout` can be more complex and is often used for other purposes, which can lead to mistakes.

In summary, `git switch` is recommended for branch switching operations due to its simplicity and clarity, while `git checkout` remains a versatile command for various tasks.
```

## Git Merge
[Git Merge - Learning](https://git-scm.com/docs/git-merge)
```bash
git merge <branch> # Merge a branch into the current branch
git merge remotes/origin/<branch> # Merge a remote branch into the current branch
git merge --abort # Abort the merge
git merge --continue # Continue the merge after resolving conflicts
git merge --no-ff <branch> # Merge a branch into the current branch with a merge commit
git merge --squash <branch> # Merge a branch into the current branch with a single commit
git merge --squash --no-commit <branch> # Merge a branch into the current branch with a single commit without committing
git merge -X theirs FETCH_HEAD # Merge changes from FETCH_HEAD with theirs strategy, remote changes will be kept in case of conflict
git merge -X ours FETCH_HEAD # Merge changes from FETCH_HEAD with ours strategy, local changes will be kept in case of conflict
```

## Git Rebase
[Git Rebase - Learning](https://git-scm.com/docs/git-rebase)
- as an alternative to `git merge`
- as a cleanup tool
- List types of rebase
  - `git rebase -i` - Interactive rebase
  - `git rebase -i --autosquash` - Interactive rebase with autosquash
  - `git rebase -i --root` - Interactive rebase with root
  - `git rebase -i --autosquash --root` - Interactive rebase with autosquash and root

```bash
git rebase <branch> # Rebase the current branch onto a branch
git rebase --continue # Continue the rebase after resolving conflicts
git rebase --abort # Abort the rebase
git rebase --skip # Skip the current commit during rebase
git rebase -i <commit> # Rebase interactively
git rebase -i HEAD~3 # Rebase the last 3 commits interactively
git rebase -i --root # Rebase the initial commit interactively
git rebase -i --autosquash <branch> # Rebase interactively with autosquash
git rebase -i --autosquash HEAD~3 # Rebase the last 3 commits interactively with autosquash
git rebase -i --autosquash --root # Rebase the initial commit interactively with autosquash
```

## Git Cherry-pick
[Git Cherry-pick - Learning](https://git-scm.com/docs/git-cherry-pick)
- Apply the changes introduced by some existing commits
- The commit is applied to the current branch as a new commit
```bash
git cherry-pick <commit> # Apply the changes introduced by a commit
git cherry-pick --continue # Continue the cherry-pick after resolving conflicts
git cherry-pick --abort # Abort the cherry-pick
```

## Git Diff
[Git Diff - Learning](https://git-scm.com/docs/git-diff)
```bash
git diff # Show changes between commits, commit and working tree, etc
git diff HEAD # Show changes between commits, commit and working tree, etc
git diff --cached # Show changes between commits, commit and index, etc
git diff --staged # Show changes between commits, commit and index, etc
git diff <commit> <commit> # Show changes between commits
```

## Git Stash
[Git Stash - Learning](https://git-scm.com/docs/git-stash)
```bash
git stash # Stash changes in the working directory
git stash list # List all stashes
git stash apply # Apply the latest stash
git stash apply <stash> # Apply a stash
git stash pop # Apply the latest stash and remove it from the stash list
git stash drop # Remove the latest stash from the stash list
git stash drop <stash> # Remove a stash from the stash list
git stash clear # Remove all stashes from the stash list
```

## Git Restore
[Git Restore - Learning](https://git-scm.com/docs/git-restore)
```bash
git restore <file> # Restore a file in the working directory
git restore --source <commit> <file> # Restore a file from a commit
git restore --staged <file> # Unstage a file
git restore --source <commit> --staged <file> # Unstage a file from a commit
```

## Git Reset
[Git Reset - Learning](https://git-scm.com/docs/git-reset)
- reflogs rescue you from losing your work.
```bash
git reset # Reset the current HEAD to the last commit
git reset --soft <commit> # Reset the current HEAD to a commit and keep changes
git reset --mixed <commit> # Reset the current HEAD to a commit and unstage changes
git reset --hard <commit> # Reset the current HEAD to a commit and discard changes
```

## Git Revert
[Git Revert - Learning](https://git-scm.com/docs/git-revert)
```bash
git revert <commit> # Revert a commit
git revert --no-commit <commit> # Revert a commit without committing
git revert --no-edit <commit> # Revert a commit without editing the commit message
```

## Git Clone
[Git Clone - Learning](https://git-scm.com/docs/git-clone)
```bash
git clone <url> # Clone a repository into a new directory
git clone <url> <directory> # Clone a repository into a specific directory
git clone <url> --branch <branch> # Clone a specific branch
git clone <url> --depth <depth> # Clone a shallow copy with a specific depth
git clone <url> --bare # Clone a bare repository
```

## Git Remote
[Git Remote - Learning](https://git-scm.com/docs/git-remote)
```bash
git remote # List all remote repositories
git remote -v # List all remote repositories with URLs
git remote add <name> <url> # Add a new remote repository
git remote remove <name> # Remove a remote repository
git remote rename <old-name> <new-name> # Rename a remote repository
git remote set-url <name> <new-url> # Change the URL of a remote repository
```

## Git Push
[Git Push - Learning](https://git-scm.com/docs/git-push)
```bash
git push # Push changes to a remote repository
git push <remote> <branch> # Push changes to a remote branch
git push <remote> <branch>:<branch> # Push changes to a remote branch and set up tracking
git push -u <remote> <branch> # Push changes to a remote branch and set up tracking
git push --force # Force push changes to a remote repository
git push --force-with-lease # Force push changes to a remote repository with lease
git push --delete <remote> <branch> # Delete a remote branch
```

## Git Fetch
[Git Fetch - Learning](https://git-scm.com/docs/git-fetch)
```bash
git fetch # Fetch changes from a remote repository
git fetch <remote> # Fetch changes from a specific remote repository
git fetch --all # Fetch changes from all remote repositories
git fetch --prune # Fetch changes and remove remote branches that no longer exist
```

## Git Pull
- git pull = git fetch + git merge FETCH_HEAD 
[Git Pull - Learning](https://git-scm.com/docs/git-pull)
```bash
git pull # Fetch changes from a remote repository and merge them into the current branch
git pull <remote> <branch> # Fetch changes from a remote branch and merge them into the current branch
git pull --rebase # Fetch changes from a remote repository and rebase them into the current branch
git pull --ff-only # Fetch changes from a remote repository and fast-forward merge them into the current branch
```
### Difference between `git pull` and `git fetch`

| Feature                | `git pull`                                                                 | `git fetch`                                                                 |
|------------------------|----------------------------------------------------------------------------|-----------------------------------------------------------------------------|
| Purpose                | Fetches changes from a remote repository and merges them into the current branch | Fetches changes from a remote repository without merging them              |
| Command Combination    | Equivalent to `git fetch` + `git merge FETCH_HEAD`                         | Only fetches changes, does not merge them                                   |
| Usage                  | `git pull`                                                                 | `git fetch`                                                                 |
| Merge                  | Automatically merges fetched changes into the current branch               | Does not merge fetched changes, only updates remote-tracking branches       |
| Safety                 | Less safe, as it can introduce conflicts during the merge                  | Safer, as it allows reviewing changes before merging                        |
| Workflow               | Suitable for simple workflows where automatic merging is desired           | Suitable for more controlled workflows where changes are reviewed before merging |
| Usage               | Safe to do at anytime          | Not Recommended if you uncommited changes!, Can result in merge conflicts |


- how resolve conflict in pull request
```bash
git pull
# Resolve conflicts in the files
git add .
git commit -m "Resolved conflicts"
git push
```

```bash
# Main
git fetch origin main # Fetch changes from the remote branch
git pull origin main # Pull changes from the remote branch
# Feature
git switch <branch> # Switch to the branch example 
git merge main # Merge changes from the remote branch
git add . # Add changes to the staging area
git commit -m "Message" # Commit changes with a message
git push origin main # Push changes to the remote repository
```

## Git Tag
[Git Tag - Learning](https://git-scm.com/docs/git-tag)

```bash
git tag # List all tags
git tag -l "*beta*" # List tags matching a pattern
git tag <tag> # Create a tag
git tag -a <tag> -m "Message" # Create an annotated tag with a message
git tag -a <tag> <commit> -m "Message" # Create an annotated tag with a message at a specific commit
git tag  <tag> <commit> -f -m "Message" # Create an annotated tag with a message at a specific commit with force
git tag -d <tag> # Delete a tag
git tag -v <tag> # Verify a tag
git tag -s <tag> # Sign a tag
git tag -n <tag> # Show the message of a tag
```
### How Semantic Versioning Works
[Semantic - Learning](https://semver.org/)

```markdown
Semantic versioning is a versioning system that follows a specific format to indicate the nature of changes in a software release. The format consists of three numbers separated by dots: MAJOR.MINOR.PATCH.

Increment the MAJOR version when you make incompatible API changes.
Increment the MINOR version when you add functionality in a backward-compatible manner.
Increment the PATCH version when you make backward-compatible bug fixes.

Initial Release: typically the first release 1.0.0
Patch Release: normally do not contain new features orsignificant changes. backward-compatible bug fixes 1.0.1
Minor Release: Minor releases signify that new features or functionalityhave been added, but the project is still backwards backwardscompatible 1.1.0
Major Release: Major releases indicate that significant changes have been made, and the new version may not be backwards compatible 2.0.0
```

## Git Reflog
[Git Reflog - Learning](https://git-scm.com/docs/git-reflog)
- Git only keeps reflogs for 90 days by default
- reflog reference name@{quantity}
```bash
git reflog # Show the reference logs
git reflog show <branch> # Show the reference logs of a branch
git reflog expire --expire=now --all # Expire all reference logs
git reflog delete --expire=now --all # Delete all expired reference logs
```

## Git Bisect
[Git Bisect - Learning](https://git-scm.com/docs/git-bisect)
```bash
git bisect start # Start the bisect session
git bisect bad # Mark the current commit as bad
git bisect good <commit> # Mark a commit as good
git bisect reset # Reset the bisect session
git bisect run <script> # Run a script to automate the bisect process
```

## Other Git Commands
```bash
git hash-object -w <file> # Create a new object
git cat-file -p <hash> # Show the content of an object
```

## Git Aliases
[Alias - Example](https://github.com/GitAlias/gitalias)
[Alias - Advanced](https://www.durdn.com/blog/2012/11/22/must-have-git-aliases-advanced-examples/)
[Ultimate - Git alias](https://gist.github.com/mwhite/6887990)
```bash
git config --global alias.st "status" # Create an alias for the status command
```

## Git Blame
[Git Blame - Learning](https://git-scm.com/docs/git-blame)
```bash
git blame <file> # Show what revision and author last modified each line of a file
git blame -L <start>,<end> <file> # Show blame information for the specified line range
git blame <commit> <file> # Show blame information starting from a specific commit
```

## Git Clean
[Git Clean - Learning](https://git-scm.com/docs/git-clean)
```bash
git clean -f # Remove untracked files from the working directory
git clean -fd # Remove untracked files and directories from the working directory
git clean -n # Show what would be removed without actually removing anything
git clean -x # Remove ignored files as well
```

## Git Submodule
[Git Submodule - Learning](https://git-scm.com/docs/git-submodule)
```bash
git submodule add <repository> <path> # Add a new submodule
git submodule update --init --recursive # Initialize, fetch and checkout submodules
git submodule foreach <command> # Run a command in each submodule
git submodule deinit <path> # Deinitialize a submodule
```

## Git Archive
[Git Archive - Learning](https://git-scm.com/docs/git-archive)
```bash
git archive --format=zip --output=<file.zip> <commit> # Create a zip archive of a specific commit
git archive --format=tar --output=<file.tar> <commit> # Create a tar archive of a specific commit
```