# Cowork Toolkit（引用声明）

> **Layer 2 真源**: tzh-ppr-skills.plugin（`_governance/tzh-ppr-skills.plugin`）
> **Layer 1 状态**: 规划中（tzhos-toolkit 插件尚未实现）

本目录不存放 SKILL.md 原文。Skill 定义随插件包或 tzh-agent-configs 仓库分发。

## Session Skill（Layer 1 · 规划中）

| Skill | 状态 | 说明 |
|-------|------|------|
| session-init | 规划中 | Cowork session 初始化 |
| cowork-healthcheck | 规划中 | 环境诊断 |
| codex-bridge | 规划中 | 宿主机 CLI 派发桥（依赖宿主机通信） |
| failure-log | 规划中 | 结构化失败归档 |

## 审计协议（Layer 2）

GGP 审计协议的 canonical 定义已迁移至：
`~/Workspace/01_Repos/_infra/tzh-agent-configs/skills/audit/ggp/SKILL.md`

Cowork 插件的 ggp skill 是该协议的 Cowork 适配层。

**SSOT 规则**：所有引用 GGP 审计模型名称和版本的位置（如 slice-execute Phase 5），
必须指向 canonical 定义，不得内联硬编码模型版本。参见 `20-standards/README.md §4`。

**相关但独立的审计工具**：
- `hl-factory/harnesses/cross-audit/` — 模块级全量审计（独立模型配置，非 GGP 分支）

## Cowork 独立 Skill（.skill 包）

| Skill | 功能 | 日志写入 |
|-------|------|---------|
| session-retrospective | 会话回顾与方法论沉淀 | ✅ Step 5 |
| claude-md-audit | CLAUDE.md 文档健康检查 | ✅ Step 5 |
| hl-dispatch | 唤龙团队协作调度 | ✅ 使用日志段 |

## 使用追踪

Skill 使用日志仍在本仓库维护：
`30-evals/toolkit-usage/logs/usage-log.jsonl`

---
依据：SKILL-GOVERNANCE v1.0 §4.1 + 20-standards §3/§4
