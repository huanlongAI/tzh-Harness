# CONVENTION.md 模板

当目标仓库中没有 `.claude/tasks/CONVENTION.md` 时，创建此文件。

将以下内容写入 `<仓库>/.claude/tasks/CONVENTION.md`：

---

```markdown
# 任务协同规范 / Task Coordination Convention

## 文件结构

.claude/tasks/
├── CONVENTION.md          ← 本文件（规范说明）
├── 001-描述.md            ← 任务文件（Cowork 写入）
├── 001-result.md          ← 结果文件（CLI 回写）
└── ...

## 任务文件格式（Cowork → CLI）

# Task NNN: 标题
> 来源: 简述来源
## 背景
## 要求
## 验收标准

## 结果文件格式（CLI → Cowork）

文件名: NNN-result.md

# Result NNN: 标题
## 状态
✅ 成功 / ❌ 失败 / ⚠️ 部分完成
## 摘要
一句话概述。
## 变更文件
- path/to/file — 改动说明
## 测试结果
X/Y 测试通过
## Git
- commit: hash — message
- push: ✅ 已推送 / ❌ 未推送
## 备注
其他需要 Cowork 知道的信息。
```
