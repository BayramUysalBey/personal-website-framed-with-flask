# Bug Explanations

| Date | Bug Title | Context | Symptom | Cause | Fix | Lesson Learned |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 2025-12-22 | Git Push Conflict (Non-fast-forward) | Project developed on Replit, then repo cloned locally, modified (Dockerized), and pushed back to GitHub. | `git push` rejected with `[rejected] main -> main (non-fast-forward)` error. | Local branch history was missing the remote's "Initial commit" (or divergence occurred), making it behind the remote branch tip. | Pulled remote changes and initiated rebase, resolved conflict in `README.md`, and continued rebase before pushing. | Always pull or rebase remote changes before pushing if you've initialized or modified the repository from different environments like Replit. |
