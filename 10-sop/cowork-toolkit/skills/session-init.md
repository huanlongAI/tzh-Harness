# session-init — Cowork 会话初始化

> 版本: v1.0 | 日期: 2026-03-19
> 角色: Orchestrator | 适用: 每次 Cowork 会话启动

## 定位

Session Protocol S-1（启动协议）的 Cowork 适配版。
Claude Code CLI 通过读取 CLAUDE.md 中的 S-1 规则自动执行；
Cowork 模式下通过本 Skill 实现等价行为。

## 触发词

「开始工作」「session init」「初始化」「启动协议」
或由 Cowork 会话的第一个用户消息自动触发。

## 执行步骤

### Step 1: 读取交接文件

按时间降序查找最新的交接文件：
```
huanlong/COWORK-HANDOFF-*.md
```
如果找到，读取并提取：阶段状态、阻塞项、下一步建议。

### Step 2: 读取 PROGRESS.json

扫描所有仓库根目录的 `PROGRESS.json`，提取：
- `current_session.status` — 上次会话状态
- `in_progress.task` — 未完成任务
- `next_up` — 建议的下一步
- `known_issues` — 已知问题

### Step 3: 最近变更历史

对活跃仓库执行 `git log --oneline -5`，理解最近做了什么。

### Step 4: 向创始人汇报

输出格式：
```
## Session Init 汇报

**上次完成**: [从 PROGRESS.json 和 HANDOFF 提取]
**当前阻塞**: [从 HANDOFF 阻塞项提取]
**建议本次做**: [从 next_up + 创始人优先级推断]

等待创始人确认后开始工作。
```

### Step 5: 可选——调用 healthcheck

如果距离上次 healthcheck 超过 24h 或创始人要求，
自动调用 cowork-healthcheck Skill 执行仓库状态扫描。

## 与 Session Protocol 的关系

| Session Protocol 规则 | CLI 实现 | Cowork 实现（本 Skill） |
|------------------------|----------|-------------------------|
| S-1 启动协议 | CLAUDE.md 自动加载 | session-init Skill |
| S-2 Plan-Before-Code | plan.md 文件 | Cowork TodoWrite + AskUser |
| S-3 结束协议 | PROGRESS.json 更新 | session-retrospective Skill |
| S-4 编辑警戒 | CLAUDE.md 自检 | Cowork 内建 |
| S-5 失败归档 | failure-log.jsonl | session-retrospective Skill |

## 注意事项

- 不自动开始工作，必须等创始人确认
- 如果 HANDOFF 文件不存在，从 PROGRESS.json 直接恢复
- 如果两者都不存在，执行 healthcheck 作为兜底
