#### Let's play a game:

- You might know how to create a feature branch, commit changes, and make a pull request.
- But let's try something a bit challenging:
  - **Phase one:**
  - There are no external tools like GitLab on your favourite IDE. Just the terminal. This applies to all other phases, too.
  - **Phase Two:**
  - Split your changes into 5 commits using only two files. And don't copy-paste changes to prepare each commit.
  - **Phase Three:**
  - After pushing commits 1 to 5, your reviewer asks you to:
    - Change something in commit 2
    - Reorder commits 1 and 3
    - Merge commit 2 into 4
    - Change the commit message for commit 5
    - Rebase your branch to master
  - **Phase Four:**
  - You made a mistake in Phase Three. You need to recover and start again, but a force pull from the origin won't work since you already pushed your changes.
  - **Phase Five:**
  - A bug was introduced into the codebase. Use Git to find the commit that started it.


------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

## **Phase One: Setting Up a Feature Branch**
1. Create a new branch for your feature:
   ```bash
   git checkout -b feature-branch
   ```
2. Make changes in two files.
3. Stage your changes:
   ```bash
   git add file1.txt file2.txt
   ```

---

## **Phase Two: Split Changes into 5 Commits**
1. Unstage changes:
   ```bash
   git reset
   ```
2. Use interactive staging to split the changes:
   ```bash
   git add -p
   ```
   - Select hunks for the first commit (`y` to stage, `n` to skip).
3. Create the first commit:
   ```bash
   git commit -m "First chunk of changes"
   ```
4. Repeat for the next chunks until all changes are split into 5 commits.

---

## **Phase Three: Modify Commits**
### 1. Edit Commit 2
   ```bash
   git rebase -i HEAD~5
   ```
   - In the editor, change `pick` to `edit` for the second commit.
   - Save and exit.
   - Make your changes to the code.
   - Amend the commit:
     ```bash
     git commit --amend
     ```
   - Continue the rebase:
     ```bash
     git rebase --continue
     ```

### 2. Reorder Commits 1 and 3
   - In the same rebase editor, move the lines corresponding to commits 1 and 3 to reorder them.

### 3. Merge Commit 2 into 4
   - Mark commit 2 as `squash` instead of `pick` in the editor for rebase.

### 4. Change Commit Message for Commit 5
   - Change `pick` to `reword` for commit 5.
   - Edit the message when prompted.

### 5. Rebase onto Master
   ```bash
   git fetch origin
   git rebase origin/master
   ```

---

## **Phase Four: Recover from Mistakes**
1. If you mess up the rebase:
   ```bash
   git rebase --abort
   ```
   - This will return your branch to its state before the rebase.

2. If you need to reset to the last pushed state:
   ```bash
   git reset --hard origin/feature-branch
   ```

3. If you've force-pushed and need to recover:
   ```bash
   git reflog
   ```
   - Find the commit hash of the desired state and reset to it:
     ```bash
     git reset --hard <commit-hash>
     ```

---

## **Phase Five: Debugging the Bug**
1. Start **Git Bisect**:
   ```bash
   git bisect start
   git bisect bad
   git bisect good <commit-hash>
   ```
   - Test each checked-out commit to determine if it's good or bad.

2. Mark each commit as you test:
   - For good commits:
     ```bash
     git bisect good
     ```
   - For bad commits:
     ```bash
     git bisect bad
     ```

3. Git will eventually identify the commit that introduced the bug. Once done:
   ```bash
   git bisect reset
   ```

---
