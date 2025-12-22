# Bug Explanations

## 2025-12-22
### Git Push Conflict (Non-fast-forward)

**Description:**
A `git push` command was rejected with a `[rejected] main -> main (non-fast-forward)` error. This prevented local changes from being uploaded to the GitHub repository.

**Cause:**
The conflict arose because the project was initially pushed from **replit.com** to GitHub. When the repository was later opened on a local machine, Dockerized, and an attempt was made to push it back to GitHub, the local branch tip was behind its remote counterpart (likely due to the "Initial commit" on GitHub not being present in the local history or a mismatch in branch histories).

**Resolution:**
1.  Initiated a `git pull` or `git rebase` to integrate remote changes.
2.  Resolved a merge conflict in `README.md` by keeping the detailed local content.
3.  Completed the rebase process using `git rebase --continue`.
4.  Successfully pushed the updated local branch to GitHub using `git push -u origin main`.
