# cowork-healthcheck — 会话启动健康检查

> 版本: v1.0 | 日期: 2026-03-19
> 角色: Verifier | 适用: Cowork 会话启动时

## 定位

Cowork 会话启动后的首个自动化检查步骤。扫描工作区所有 Git 仓库状态，
汇报未提交变更、未推送 commits、分支信息，帮助创始人快速了解工作区全貌。

## 触发词

「健康检查」「检查仓库」「工作区状态」「healthcheck」「repo status」
或在 Cowork 会话启动时由 session-init 自动调用。

## 执行步骤

### Step 1: 发现所有 Git 仓库

```bash
find /path/to/workspace -maxdepth 3 -name ".git" -type d | sort
```

### Step 2: 逐仓库扫描

对每个仓库执行：
1. `git branch --show-current` — 当前分支
2. `git status -s` — 未提交变更（计数 M/A/D/?? 各类别）
3. `git log --oneline origin/main..HEAD 2>/dev/null` — 本地领先远程的 commits
4. `git stash list` — 是否有 stash

### Step 3: 输出汇总表

```
| 仓库 | 分支 | 未提交 | 领先远程 | stash |
|------|------|--------|----------|-------|
```

标记颜色约定：
- 🟢 完全同步（无未提交、无领先）
- 🟡 有未提交变更但可继续工作
- 🔴 领先远程 3+ commits 需要推送

### Step 4: 给出建议

- 如果有 🔴 仓库，建议创始人先 push
- 如果有大量未追踪文件，建议 git add 或 .gitignore
- 如果远程不可达（DNS 失败），标注但不阻塞

## 注意事项

- Cowork VM 通常无法直接访问 GitHub（DNS 限制），远程状态基于缓存的 origin 判断
- 不执行 `git fetch`（可能失败），仅基于本地 origin 缓存
- 不修改任何仓库内容，纯只读操作
