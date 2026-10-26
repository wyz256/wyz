---
name: commit-push-github
description: Use when the user asks to commit and push the whole project to GitHub. Triggers on phrases like "提交到github", "提交项目到github", "push to github", "推送到GitHub".
---

# Commit and Push to GitHub

## Remote Repository

- URL (SSH, public key auth): `git@github.com:wyz256/wyz.git`
- Remote name: `github` (the `origin` remote points to Gitee and must stay untouched)
- Branch: `master`

## Workflow

1. **Log the prompt first**: Append the current prompt to `wang_prompt.md` (never overwrite; UTF-8). In PowerShell use `Add-Content -Encoding UTF8`.
2. **Check status**: Run `git status` to review changes.
3. **Stage and commit**: `git add -A`, then `git commit -m "提交项目：<变更摘要>"`.
4. **Ensure remote**: Run `git remote -v`. If the `github` remote is missing, run:
   ```
   git remote add github git@github.com:wyz256/wyz.git
   ```
   If `github` exists with a different URL, update it: `git remote set-url github git@github.com:wyz256/wyz.git`
5. **Push**: Run `git push -u github master`.
6. **Report**: The commit hash and push result.

## Notes

- Use the SSH URL (not HTTPS) - the user has set up public key authentication.
- Port 22 is blocked on the user's network. `~/.ssh/config` contains a `Host github.com` block routing to `ssh.github.com:443` (set up 2026-10-26, verified with `ssh -T git@github.com` returning "Hi wyz256!"). Do not remove it; if SSH fails, check that block first.
- In PowerShell, chain commands with `;` instead of `&&`.
- If push fails due to non-fast-forward (e.g. the remote repo has an initial commit like a README), do NOT force push. Report the error to the user.
- If SSH authentication fails, report that the SSH key/agent is unavailable - do not silently switch to HTTPS.
