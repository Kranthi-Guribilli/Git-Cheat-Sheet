# Git Commands

## Git Setup
* Create a <b>new Git repository</b> from an existing directory:

  ```
  git init [directory]
  ```
 * <b>Clone a repository</b> (local or remote via HTTP/SSH):
 
    ```
     git clone [repo/URL]
    ```
 * Clone a repository into <b>a specified folder</b> on your local machine:
 
   ```
   git clone [repo/URL] [folder]
   ```
   
## Git Configuration:
* Attach an <b>author name</b> to all commits that will appear in the version history:
  
  ```
  git config --global user.name "[your_name]"
  ```
* Attach an <b>email address</b> to all commits by the current user:

  ```
  git config --global user.email "[email_address]"
  ```
  
* Create a <b>shortcut (alias)</b> for a git command:

  ```
  git config -- global alias.[alias_name] [git_command]
  ```
  
## Managing Files:
* Show the **state of the current directory** (list staged, unstaged, and umtracked files):

  ```
  git status
  ```
* List the **commit history** of the current branch:

  ```
  git log
  ```
* List **all commits from all branches:**

  ```
  git log --all
  ```
* **Compare two branches** by showing which commits from the first branch are missing from the second branch:

  ```
  git log [branch1]..[branch2]
  ```
* Examine the difference between the **working directory and the index:**

  ```
  git diff
  ```
* Examine the difference between the **last commit and the index**:

  ```
  git diff --cached
  ```
* See the difference between the **last commit and the working directory:**

  ```
  git diff HEAD
  ```

## Git Branches:
* List **all branches** in the repository:

  ```
  git branch
  ```
* List all **remote branches:**

  ```
  git branch -aa
  ```
* **Create a new branch** under a specified name:

  ```
  git brancch [branch]
  ```
* **Switch to a branch** under a specified name (if it doesn't exist, a new one will be created):

  ```
  git checkout [branch]
  ```
* **Delete a local branch**:

  ```
  git branch -d [branch]
  ```
* **Rename a branch** you are currently working in:  

  ```
  git branch -m [new_branch_name]
  ```
* Merge the specified branch with the current branch:

  ```
  git merge [branch]
  ```
  
## Making Changes
* **Stage changes** for the next commit:

  ``` 
  git add [file/directory]
  ```
* **Stage everything** in the directory for an initial commit:

  ```
  git add .
  ```
* **Commit staged snapshots** in the version history with a descriptive message included in the command:

  ```
  git commit -m "[descriptive_message]"
  ```

## Undoing Changes:
* **Undo changes** in a file or directory and create a new commit with the git revert command:

  ```
  git revert [file/directory]
  ```
* **Unstage a file** without overwriting changes:

   ``` 
   git reset [file]
   ```
* Unso any changes introduced **after the specified commit**:

  ```
  git reset [commit]
  ```
* Show untracked files which will be removed when you run git clean (do a dry run):

  ```
  git clean -n
  ```
* **Remove untracked files:**

   ```
   git clean -f
   ```

## Rewriting History
* **Replace the last commit** with a combination of the staged changes and the last commit combined:

  ```
  git commit --amend
  ```

* **Rebase the current branch** with the specified base (it can be a branch name, tag, reference to a HEAD, or a commit ID):

  ```
  git rebase [base]
  ```
* List **changes made to the HEAD** of the local repository:
  
  ```
  git reflog   
  ```
  
  Remote Repositories
Create a new connection to a remote repository (give it a name to serve as a shortcut to the URL):

git remote add [name] [URL]

Fetch a branch from a remote repository:

git fetch [remote_repo] [branch]

Fetch a repository and merge it with the local copy:

git pull [remote_repo]

Push a branch to a remote repository with all its commits and objects:

git push [remote_repo] [branch]
   
