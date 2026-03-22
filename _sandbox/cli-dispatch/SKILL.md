---
name: cli-dispatch
version: 0.2.0
last_verified: "2026-03-22"
status: blocked
blocked_reason: "依赖 Desktop Commander osascript，Cowork sandbox 无宿主机通信能力"
description: >
  Cowork ↔ CLI 双向任务派发与同步。在 Cowork 中规划任务，通过 osascript 自动派发到
  macOS Terminal 中的 Claude Code CLI 执行，CLI 完成后回写结果文件供 Cowork 读取。
  当用户提到「派发任务」「发到 CLI」「让 CLI 执行」「查看 CLI 进度」「检查结果」
  「写任务文件」或任何涉及 Cowork 与 CLI 协同的场景时，使用此 skill。
  也适用于用户说「下一个任务」「继续开发」等暗示需要创建并派发任务的场景。
---

# CLI Dispatch — Cowork ↔ CLI 双向协同

Cowork 负责思考和决策，CLI 负责编码和执行，通过共享任务文件双向通信。

## 工作流

```
用户在 Cowork 提需求 → 写任务文件 → osascript 派发到 Terminal
→ CLI 执行 + 写结果文件 + commit + push → Cowork 读取结果
```

## 操作步骤

### Step 1: 确定任务编号

读取目标仓库的 `.claude/tasks/` 目录，找最大已有编号，+1 得到新编号。
编号格式：三位数字（如 `005`）。

如果 `.claude/tasks/` 或 `CONVENTION.md` 不存在，先创建它们——参见 `references/convention-template.md`。

### Step 2: 写任务文件

路径：`<仓库>/.claude/tasks/NNN-简短描述.md`

```markdown
# Task NNN: 标题

> 来源: 用户需求 / 审计发现 / Phase X.Y 等

## 背景
上下文和为什么要做。CLI 是独立会话，没有 Cowork 的上下文，所以背景要充分。

## 要求
1. 具体可执行的事项
2. 避免含糊描述

## 验收标准
- [ ] 可验证的条目
- [ ] 所有现有测试仍通过
```

### Step 3: 派发到 CLI

使用 `mcp__Control_your_Mac__osascript` 工具：

```applescript
tell application "Terminal"
    activate
    do script "cd '<仓库绝对路径>' && claude '读取 .claude/tasks/CONVENTION.md 了解结果文件格式，然后读取并执行 .claude/tasks/NNN-xxx.md。完成后：1) 按 CONVENTION.md 格式将结果写入 .claude/tasks/NNN-result.md；2) git add 变更文件和结果文件；3) git commit 并写清晰的 commit message；4) git push'"
end tell
```

路径用单引号包裹（可能含空格）。指令中必须包含读取 CONVENTION.md 的要求。

### Step 4: 告知用户

- Terminal 已弹出，CLI 正在启动
- 请切到终端确认执行
- 完成后回来说「查看进度」

### Step 5: 读取结果

用户询问进度时读取 `.claude/tasks/NNN-result.md`：

| 文件状态 | 含义 | 建议 |
|---------|------|------|
| 存在且 ✅ | CLI 已完成 | 汇报摘要，提议下一个任务 |
| 存在且 ❌ | CLI 执行失败 | 分析备注，写修复任务 |
| 不存在 | CLI 还在执行 | 建议稍等或切终端查看 |

### 全局进度查看

扫描 `.claude/tasks/` 目录，列出所有任务及状态（未派发 / 进行中 / 已完成 / 失败）。

## 仓库路径

工作区根目录：`~/Workspace/01_Repos/`（PPR DIRECTORY-SPEC 四域结构）

> 仓库清单以 REPO-MAP.md v1.0 为准。常用派发目标：

| 仓库 | 路径 | 场景 |
|------|------|------|
| tzhOS-App | `_platform/tzhOS-App` | iOS 生命终端开发 |
| super-founder | `_platform/super-founder` | macOS 事业中枢开发 |
| guanghe | `_infra/guanghe` | 光合设计系统（GHKit） |
| hl-platform | `huanlong/hl-platform` | Kotlin 后端 |
| hl-console-native | `huanlong/hl-console-native` | SwiftUI 控制台 |

用户未指定仓库时，根据内容推断目标仓库。
