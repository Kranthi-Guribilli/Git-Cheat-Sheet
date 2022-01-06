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
  
   
