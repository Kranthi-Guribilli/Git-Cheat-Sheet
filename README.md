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
## Stash
* Git stash is a command in git that allows developers to temporarily save changes they have made to their code.
* The changes can be saved temporarily, and later, can be retrieved when needed. This is especially useful when the developer needs to switch to a different branch or work on a different feature but doesn't want to commit the changes to the repository.
* Stashing is a convenient way to save changes that are not yet ready to be committed, but also not ready to be discarded.
* This feature can be used to save the untracked files and work and come back to it later.
* Can be used to save bothe staged and unstaged changes.
* **Git stash commands**

  ```
  git stash
  ```
* By default, Git stash will save both staged and unstaged changes. If you want to save only staged changes, you can use the --keep-index option:
    ```
    git stash --keep-index
    ```
* The git stash save command is similar to the git stash command. The only difference is that it allows developers to add a message describing the changes made to the stash.
    ```
    git stash save "message"
    ```
* If you want to give the stash a name(stash label), you can use the -m option:
    ```
    git stash save -m "My stash name"
    ```
* Once you have stashed your changes, you can switch to a different branch or work on a different feature. When you're ready to retrieve your stashed changes, you can use the Git stash apply option:
    ```
    git stash apply
    ```
* This will retrieve the most recent stash commit in the current working directory. To apply a specific or selected stash, you can use the Git stash apply command followed by the stash reference:
    ```
    git stash apply stash@{1}
    ```
* If you have more than one stash listing, you can use the Git stash list command to view them simultaneously:
    ```
    git stash list
    ```
* If you want to completely remove a stash from the current working directory, you can use the Git stash drop command:
    ```
    git stash drop stash@{1}
    ```
* If you want to apply a stash and remove it from the git stash branch at the same time, you can use the Git stash pop command:
    ```
    git stash pop
    ```
* The git stash pop will apply the most recent stash and remove it from the stash list.
    ```
    git stash branch branch_name stash_id
    ```
* The git stash branch command is used to create a new branch from a stash entry. This command applies the stash entry to the new branch, allowing developers to continue working on the changes.
    ```
    git stash drop stash_id
    ```
* This command is used to remove a stash entry from the stash list. It permanently deletes the stash entry, and stash history and cannot be undone.

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
   
