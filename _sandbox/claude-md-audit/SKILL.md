---
name: claude-md-audit
version: 0.2.0
last_verified: "2026-03-22"
description: >
  CLAUDE.md 文档健康检查。扫描工作区所有仓库的 CLAUDE.md 和 README.md，
  检查冗余指令、冗长措辞、与用户记忆重叠的内容、过时信息，输出改进建议。
  当用户说「检查文档」「审计 CLAUDE.md」「文档瘦身」「优化 AI 指令」
  或任何涉及 CLAUDE.md / README.md 质量维护的场景时，使用此 skill。
  建议在大规模文档改动后（如本地化、重构）运行一次。
  仓库清单来源：REPO-MAP.md v1.0。
---

# CLAUDE.md Audit — 文档健康检查

CLAUDE.md 是 AI 协作的核心配置——冗余浪费 token，遗漏导致错误行为，过时内容误导 AI。

## 检查流程

### Step 1: 收集文档

> 仓库清单对齐 REPO-MAP.md v1.0（2026-03-14）。如清单变更，以 REPO-MAP.md 为准。

扫描工作区所有活跃仓库的 CLAUDE.md 和 README.md：

**tongzhenghui 个人账户（`01_Repos/`）**：
- `_governance/tzhOS/` — 治理 SSOT
- `_governance/tzh-Harness/` — Harness 方法论
- `_platform/tzhOS-App/` — iOS 生命终端
- `_platform/super-founder/` — macOS 事业中枢
- `_infra/guanghe/` — 光合设计系统
- `_infra/tzh-dotfiles/` — 环境同构配置
- `_infra/tzh-evals/` — 评测基准
- `_infra/tzh-agent-configs/` — Agent Skills 配置

**huanlongAI 组织账户**：
- `huanlong/hl-contracts/` — 契约法典
- `huanlong/hl-platform/` — Kotlin 后端
- `huanlong/hl-framework/` — 公司框架
- `huanlong/hl-console-native/` — SwiftUI 控制台
- `huanlong/hl-dispatch/` — 协作调度
- `huanlong/hl-factory/` — AI-Ops 超级工厂

**已归档（跳过）**：
- ~~tzhos-server~~（R-0071）、~~hl-ai-ops~~、~~hl-federation~~、~~hl-factory-console~~、~~hl-prd~~、~~hl-agent-os~~、~~tzhos-console~~、~~tzh-sase~~

### Step 2: 5 项检查

**① 冗余指令** — 文件内/跨文件的语义重复
**② 冗长措辞** — 能一句说清却用一段、可删的填充词
**③ 记忆重叠** — 跨项目通用偏好应移至 ~/.claude/memory
**④ 过时信息** — 不存在的路径、废弃的命令、过期 URL
**⑤ AI/人类可读性** — 结构清晰度、关键信息位置、快速浏览性

### Step 3: 分级报告

```
### 🔴 需修复（影响 AI 行为）
1. 文件:行号 — 问题 — 建议

### 🟡 建议优化（减少 token 浪费）
1. 文件 — 问题 — 建议

### 🟢 可选改进
1. 文件 — 问题 — 建议

### 📊 统计
总文件 | 总行数 | 冗余 N 处 | 冗长 N 处 | 过时 N 处
```

### Step 4: 确认后执行

问用户：「修复全部 / 只修红色 / 只看不改？」
修改时展示 diff 让用户确认。

## 文件路径

工作区: `~/Workspace/01_Repos/`（PPR DIRECTORY-SPEC 四域结构）

> 参考：`_governance/tzhOS/40-PPR/REPO-MAP.md` 为仓库清单唯一权威来源。

## 运行频率

- 大规模文档改动后：立即运行
- 每 5 个 Task 完成后：运行一次
- AI "不听话"时：优先检查 CLAUDE.md
