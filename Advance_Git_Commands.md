
# Advanced Git Commands

A collection of advanced Git commands for fine-grained control, debugging, and history manipulation.

---

## 1. `git add -p`
Stages specific portions of changes interactively.

```bash
git add -p
```

- Allows you to review changes hunk by hunk and decide which parts to stage.
- Options include staging (`y`), skipping (`n`), or splitting hunks (`s`).

---

## 2. `git commit --fixup`
Creates a "fixup" commit tied to a specific earlier commit.

```bash
git commit --fixup <commit-hash>
```

- Creates a commit labeled as a fix for `<commit-hash>`.
- Combine with `git rebase -i --autosquash` to automatically squash fixup commits during rebasing.

---

## 3. `git rebase -i` (Interactive Rebase)
Rewrites commit history interactively.

```bash
git rebase -i HEAD~5
```

- Lets you squash, edit, or reorder commits.
- Use to clean up commit history before sharing.

---

## 4. `git bisect`
Finds the commit that introduced a bug via binary search.

```bash
git bisect start
git bisect bad # Mark current commit as bad
git bisect good <commit-hash> # Mark earlier commit as good
```

- Git will check out commits one by one; test and mark them as `good` or `bad`.

---

## 5. `git stash -p`
Stashes specific portions of changes interactively.

```bash
git stash -p
```

- Similar to `git add -p`, but for stashing hunks.

---

## 6. `git cherry-pick -n`
Applies a commit to the current branch without automatically committing it.

```bash
git cherry-pick -n <commit-hash>
```

- Useful when you want to include changes from another branch but modify them before committing.

---

## 7. `git log -S`
Searches commit history for a specific string in changes.

```bash
git log -S "specificFunctionName"
```

- Finds commits where the given string was added, removed, or modified.

---

## 8. `git reflog`
Displays a log of all actions (including detached head changes).

```bash
git reflog
```

- Great for recovering lost commits or branches.

---

## 9. `git checkout -p`
Checks out specific parts of changes interactively.

```bash
git checkout -p
```

- Useful to discard or undo parts of your changes without affecting the rest.

---

## 10. `git range-diff`
Compares two sets of commits.

```bash
git range-diff A...B
```

- Highlights the differences between two branches or ranges.

---

## 11. `git worktree`
Creates multiple working directories tied to a single repository.

```bash
git worktree add ../new-branch-dir new-branch
```

- Useful for working on multiple branches simultaneously without the need for constant branch switching.

---

## 12. `git blame -L`
Shows line-by-line attribution for a specific range in a file.

```bash
git blame -L 10,20 file.txt
```

- Finds who modified specific lines in a file.

---

## 13. `git diff --color-words`
Shows word-level differences in changes.

```bash
git diff --color-words
```

- Easier to identify specific word changes within a line.

---

## 14. `git bundle`
Creates or applies a bundle (archive) of Git changes.

```bash
git bundle create my-bundle.bundle main
git bundle verify my-bundle.bundle
```

- Useful for offline code sharing.

---

## 15. `git fsck`
Performs a consistency check on the repository.

```bash
git fsck
```

- Identifies corruption, dangling objects, and missing commits.

---

## 16. `git grep`
Searches for text across the entire repository.

```bash
git grep "TODO"
```

- Useful for finding TODOs or debugging references.
