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
