---
name: session-retrospective
version: 0.2.0
last_verified: "2026-03-22"
description: >
  会话回顾与方法论沉淀。回顾当前 Cowork 会话的全过程，提取学习、踩坑记录、
  skill 改进建议和 Pattern 候选，输出为 PLAYBOOK Case Note 和可执行的改进项。
  当用户说「回顾」「总结」「沉淀」「提炼」「写 Case Note」「今天学到了什么」
  「session 结束」或任何暗示需要回顾本次会话的场景时，使用此 skill。
  建议在每次 Cowork 深度工作会话结束前主动触发。
---

# Session Retrospective — 会话回顾与方法论沉淀

从每次实践中提取学习，让方法论有机生长。
这是 AI Playbook Track 1 核心流程的最后一步：「提炼回写 PLAYBOOK.md」的自动化实现。

## 回顾流程

### Step 1: 扫描会话，提取 5 类信息

**① 完成的任务** — Task 编号、功能、测试结果、首次/迭代
**② 踩过的坑** — 错误、解决路径、是否可复用
**③ 工作流改进** — 摩擦点、新工具/脚本/skill
**④ Pattern 候选** — 至少 2 个场景出现过的可复用模式
**⑤ Skill 改进建议** — 遗漏场景、新 skill 需求、指令优化

### Step 2: 结构化呈现

向用户展示提取结果，每类用简洁格式：

```
### 完成任务
- Task 005: WebSocket 通知联动（49/49 测试通过）

### 踩坑记录
1. [问题] gh CLI 未安装 → git push 失败
   [解决] brew install gh && gh auth login
   [可复用] 是 — 加入新机器初始化清单

### 工作流改进
- 新建 cli-dispatch skill，零粘贴派发

### Pattern 候选
- 「双轮审计收敛」：首轮 N 问题 → 修复 → 二轮 ≤ N/3

### Skill 改进建议
- cli-dispatch: 增加批量派发
```

### Step 3: 用户确认

问用户三个问题：
1. 哪些写入 PLAYBOOK Case Notes？
2. 有 Pattern 候选成熟到可正式提炼吗？
3. Skill 改进现在执行还是记录待办？

### Step 4: 写入 PLAYBOOK

确认后写入 `tzhOS/ai/PLAYBOOK.md`。先读取获取最大 CN/PAT 编号。

**Case Note 格式**：
```markdown
**CN-NNN · YYYY-MM-DD · 标题**
- **闭环路径**: 需求 → 执行 → 审计 → 修复
- **观察 N**: 发现
- **已抽象**: 否
```

**Pattern 格式**（需 ≥2 个实践案例）：
```markdown
PAT-NNN · 模式名称
场景: 什么时候用
做法: 怎么做
注意事项: 边界条件
来源: CN-NNN
```

## 文件路径

PLAYBOOK: `_governance/tzh-Harness/20-playbook/PLAYBOOK.md`（待建）
工作区: `~/Workspace/01_Repos/`（PPR DIRECTORY-SPEC 四域结构）

> 注：原 `tzhOS/ai/PLAYBOOK.md` 路径已废弃。PLAYBOOK 应归属 Harness 方法论仓库，目录待首次使用时创建。

## 原则约束

- P3: 从实践中提炼，不从理论推演
- P5: 最小结构，有机生长
- Pattern 需 ≥2 个案例支撑，否则标「候选」
- 回顾要诚实，不美化未完成的事项
