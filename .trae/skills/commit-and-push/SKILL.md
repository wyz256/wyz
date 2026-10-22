---
name: commit-and-push
description: Commits all changes and pushes master to the project Gitee repository. Use when the user says 提交项目, commit and push, 推送到Gitee, or push to gitee. Do not use for other git operations.
---

# Commit and Push to Gitee

## Remote Repository

- URL: `https://gitee.com/wang-yuzhi1/gaojiwangyesheji`
- Branch: `master`

## Workflow

1. **Check status**: Run `git status` to see the current state.
2. **Stage all files**: Run `git add -A`
3. **Commit**: Run `git commit -m "提交项目：<简要描述本次变更>"`. The message must start with the prefix `提交项目：` followed by a short summary of the actual changes (e.g. `提交项目：新增14-1 JavaScript基础练习及首页导航更新`). When no specific summary applies, use `提交项目：更新高级网页设计练习代码`.
4. **Verify remote**: Run `git remote -v`. If the Gitee URL is not present, run:
   ```
   git remote add origin https://gitee.com/wang-yuzhi1/gaojiwangyesheji
   ```
5. **Push**: Run `git push -u origin master`
6. **Report**: After a successful push, report the commit hash and confirm the push succeeded.

## Notes

- This environment runs PowerShell — chain commands with `;` instead of `&&`, or run them as separate calls.
- If the remote already exists with a different URL, run `git remote set-url origin https://gitee.com/wang-yuzhi1/gaojiwangyesheji`.
- If push fails due to non-fast-forward, do NOT force push. Report the error to the user and stop.
- If there is nothing to commit, skip to push; if there is nothing to push either, report that the repository is already up to date.
