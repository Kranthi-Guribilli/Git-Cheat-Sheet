
# Git Cheat Sheet

---

## 1. Git Basics

### Setting up Git
```bash
git config --global user.name "Your Name"     # Set the user name
git config --global user.email "you@example.com"   # Set the email
git config --list                             # View all config settings
git init                                      # Initialize a new repository
git clone <repo_url>                          # Clone an existing repository
```

### Working with Repositories
```bash
git status                                    # Check the current status
git add <file>                                # Stage a file
git add .                                     # Stage all changes
git commit -m "Message"                       # Commit staged files with a message
git log                                       # Show commit history
git diff                                      # Show changes in files
git show <commit_hash>                        # Show details of a specific commit
```

---

## 2. Branching and Merging

### Branching
```bash
git branch                                    # List all branches
git branch <branch_name>                      # Create a new branch
git checkout <branch_name>                    # Switch to a branch
git checkout -b <branch_name>                 # Create and switch to a new branch
git branch -d <branch_name>                   # Delete a branch locally
git push origin --delete <branch_name>        # Delete a remote branch
```

### Merging
```bash
git merge <branch_name>                       # Merge a branch into the current branch
git rebase <branch_name>                      # Reapply commits on top of another base
```

---

## 3. Git Remote

### Working with Remotes
```bash
git remote -v                                 # List remotes
git remote add origin <repo_url>              # Add a remote repository
git fetch <remote>                            # Fetch all changes from remote but don't merge
git pull                                      # Fetch and merge changes from the remote
git push                                      # Push changes to the remote
git push --set-upstream origin <branch_name>  # Push branch and track it
```

### Remote Operations
```bash
git pull origin <branch_name>                 # Pull changes from a specific branch
git fetch --all                               # Fetch all branches from all remotes
git push origin <branch_name>                 # Push the current branch to remote
```

---

## 4. Undoing Changes

### Unstaging Changes
```bash
git reset HEAD <file>                         # Unstage a file but keep changes
git reset --soft <commit_hash>                # Reset to a commit, keep changes staged
git reset --hard <commit_hash>                # Reset to a commit and remove changes
```

### Undoing Commits
```bash
git revert <commit_hash>                      # Revert a specific commit
git commit --amend                            # Amend the last commit message
```

---

## 5. Stashing

### Saving Work Temporarily
```bash
git stash                                     # Stash current changes
git stash list                                # List all stashes
git stash apply                               # Apply the latest stash
git stash pop                                 # Apply and remove the latest stash
git stash drop                                # Remove a specific stash
```

---

## 6. Git Logs & History

### Viewing Logs
```bash
git log --oneline                             # View short log summary
git log --graph                               # Visualize branch history as a graph
git log -p                                    # Show commits with diff
git log --author="<author_name>"              # Show commits from a specific author
git log --since="1 week ago"                  # Show commits from the last week
```

### Blame & Search
```bash
git blame <file>                              # Show who changed each line of a file
git grep <pattern>                            # Search for a text pattern in tracked files
```

---

## 7. Tagging and Releases

### Tagging Commits
```bash
git tag                                       # List all tags
git tag <tag_name>                            # Create a new tag
git tag -a <tag_name> -m "Message"            # Create an annotated tag
git show <tag_name>                           # Show tag details
git push origin <tag_name>                    # Push a tag to remote
git push origin --tags                        # Push all tags to remote
```

---

## 8. Advanced Git

### Cherry-Picking
```bash
git cherry-pick <commit_hash>                 # Apply a specific commit to the current branch
```

### Reflog
```bash
git reflog                                    # Show history of HEAD changes
```

### Interactive Rebase
```bash
git rebase -i <base_commit>                   # Rebase and interactively edit commits
```

### Squashing Commits
```bash
git rebase -i <commit>                        # Squash commits during an interactive rebase
git reset --soft <commit_hash> && git commit  # Squash last few commits into one
```

---

## 9. Git Aliases

### Common Git Aliases
```bash
git config --global alias.co checkout         # Shorten checkout to 'co'
git config --global alias.br branch           # Shorten branch to 'br'
git config --global alias.cm "commit -m"      # Shorten commit to 'cm'
git config --global alias.st status           # Shorten status to 'st'
git config --global alias.hist "log --oneline --graph --decorate"
                                              # Alias for a good history view
```

---

## 10. Handling Conflicts

### Conflict Resolution
```bash
git merge <branch>                            # Merge branch into the current one
# If conflict occurs, Git will mark conflicts in the files
git status                                    # Identify conflicted files
# Edit the files to resolve conflicts
git add <file>                                # Mark conflict as resolved
git commit                                    # Finalize the merge after resolving
```

---

## 11. Cleaning Up

### Removing Untracked Files
```bash
git clean -n                                  # Preview untracked files and directories to be removed
git clean -f                                  # Remove untracked files
git clean -fd                                 # Remove untracked files and directories
```

