---
name: commit-and-push
description: Use when the user asks to commit and push the current project to the Gitee repository. Triggers on phrases like "提交项目", "commit and push", "推送到Gitee", "push to gitee".
---

# Commit and Push to Gitee

## Remote Repository

- URL: `https://gitee.com/wang-yuzhi1/gaojiwangyesheji`
- Branch: `master`

## Workflow

1. **Check status**: Run `git status` to see current state
2. **Stage all files**: Run `git add -A`
3. **Commit**: Run `git commit -m "提交项目：更新高级网页设计练习代码"`
4. **Add remote if needed**: Check with `git remote -v`. If the Gitee URL is not present, run:
   ```
   git remote add origin https://gitee.com/wang-yuzhi1/gaojiwangyesheji
   ```
5. **Push**: Run `git push -u origin master`

## Notes

- If the remote already exists with a different URL, update it with `git remote set-url origin https://gitee.com/wang-yuzhi1/gaojiwangyesheji`
- If push fails due to non-fast-forward, do NOT force push. Report the error to the user.
- After successful push, report the commit hash and confirm the push was successful.
