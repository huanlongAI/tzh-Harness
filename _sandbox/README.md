# Sandbox 实验层

> 治理依据：SKILL-GOVERNANCE v1.0 §3.5
> 来源迁移：从 `01_Repos/_sandbox/`（无版本管理）迁入 tzh-Harness（2026-03-22）

实验性 skill，不纳入三层架构正式管理。满足 SKILL-GOVERNANCE P-4 拆分阈值时可晋升到 Layer 2（tzh-agent-configs/skills/）。

## 当前资产

| Skill | 状态 | 说明 |
|-------|------|------|
| session-retrospective | 保留 | 与 S-7 SESSION-SUMMARY 互补（SUMMARY 记"干了什么"，Retrospective 记"学到什么"） |
| cli-dispatch | 保留（blocked） | 依赖 Desktop Commander osascript，待 Cowork 支持宿主机通信后激活 |
| claude-md-audit | 保留 | 仓库列表已对齐 REPO-MAP.md v1.0（v0.2.0, 2026-03-22） |

## 晋升条件

Sandbox skill 满足以下任一条件时，可提交晋升到 Layer 2：
1. 被 ≥2 个项目实际使用
2. 属于 PPR 五系统角色的通用能力（Orchestrator/Executor/Verifier/Auditor）
3. 不依赖特定项目的 CLAUDE.md 参数即可运行
