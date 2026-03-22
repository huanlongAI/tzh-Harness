# Skill｜并行 Agent 派发（Parallel Agent Dispatch）

- Name: parallel-agent-dispatch
- Type: skill（工程方法论）
- Status: DRAFT
- Version: 0.1.0
- Owner: TZH
- Date: 2026-03-22
- Related:
  - tzh-Harness/00-principles/README.md（P3 可组合）
  - tzhOS/40-AGENT-MANAGER/agent-profiles/chief-of-staff.agent.md（§3.2 四状态报告）
  - 来源：obra/superpowers `skills/dispatching-parallel-agents/SKILL.md` 改造

---

## 1. Purpose（目的）

当面对 2+ 个**独立**任务时，通过并行派发 Sub-Agent 来提高效率。每个 Agent 获得隔离上下文、明确范围和约束，互不干扰地并行工作。

**Non-goals**：
- 不适用于有共享状态或顺序依赖的任务
- 不替代 Step 0 Brainstorming 对需求的澄清
- 不替代创始人对架构决策的裁决权

## 2. Trigger（触发条件）

**使用本 Skill**：
- 2+ 个测试文件因不同根因失败
- 多个子系统独立损坏
- 每个问题可以在不依赖其他问题上下文的情况下理解
- 调查/修复之间无共享状态

**不使用**：
- 失败之间有关联（修一个可能修好其他的）→ 先一起调查
- 需要理解完整系统状态 → 单一 Agent 全局调查
- Agent 之间会互相干扰（编辑同一文件、使用同一资源）
- 探索性调试（还不知道哪里坏了）→ 先用 systematic-debugging

## 3. Workflow

### Step 1｜识别独立域（Identify Independent Domains）

按「坏掉的是什么」来分组失败：

```
Domain A: 用户认证流程 — 3 个测试失败
Domain B: 批量处理行为 — 2 个测试失败
Domain C: 中断功能 — 1 个测试失败
```

**判断标准**：修复 Domain A 是否影响 Domain B？如果不影响，它们是独立的。

### Step 2｜构造 Agent 任务指令

<HARD-GATE>
每个 Sub-Agent 的指令必须包含以下四要素，缺一不可。缺少任何要素的指令禁止派发。
</HARD-GATE>

| 要素 | 说明 | Bad ❌ | Good ✅ |
|------|------|--------|---------|
| **Scope（范围）** | 只处理哪个文件/子系统 | 「修复所有测试」 | 「修复 auth.test.ts 的 3 个失败用例」 |
| **Goal（目标）** | 明确的成功标准 | 「修一下」 | 「让这 3 个测试通过，不引入新失败」 |
| **Constraint（约束）** | 不允许做什么 | （无约束） | 「不要修改生产代码」或「仅修改 X 文件」 |
| **Output（输出）** | Agent 完成后返回什么 | （无要求） | 「返回根因摘要 + 变更说明」 |

**指令模板**：

```markdown
修复 [文件/子系统] 中的 [N] 个失败：

1. [测试名 1] — [症状简述]
2. [测试名 2] — [症状简述]

你的任务：
1. 阅读测试文件，理解每个测试验证什么
2. 使用 systematic-debugging 四阶段流程找到根因
3. 修复

约束：[不要修改 X / 仅修改 Y]

返回：根因摘要 + 变更内容 + 四状态码（DONE / DONE_WITH_CONCERNS / NEEDS_CONTEXT / BLOCKED）
```

### Step 3｜并行派发

```
Agent 1 → Domain A（用户认证）
Agent 2 → Domain B（批量处理）
Agent 3 → Domain C（中断功能）
// 三个 Agent 并行工作
```

### Step 4｜Review & Integrate（审查与集成）

Agent 返回后：

1. **阅读每个 Agent 的摘要**——理解它们做了什么
2. **检查冲突**——有没有 Agent 编辑了相同代码？
3. **跑完整测试套件**——验证所有修复组合在一起没问题
4. **抽查**——Agent 可能犯系统性错误

<HARD-GATE>
禁止在全套测试通过之前声称并行修复已完成。Agent 返回 DONE 不等于集成完成。
</HARD-GATE>

## 4. 四状态报告要求

每个 Sub-Agent 在完成时必须使用以下四种状态之一（详见 chief-of-staff §3.2）：

| 状态 | 含义 | 必须附带 |
|------|------|---------|
| **DONE** | 完成，验证通过 | 验证证据（测试输出） |
| **DONE_WITH_CONCERNS** | 完成但有隐患 | concerns 列表 + 建议 |
| **NEEDS_CONTEXT** | 缺少信息 | 缺什么 + 在哪找 |
| **BLOCKED** | 无法继续 | 阻碍原因 + 已尝试路径 |

**协调者（Coordinator）处理规则**：
- 全部 DONE → 跑集成测试 → 完成
- 有 DONE_WITH_CONCERNS → 评估 concerns，决定是否需要额外处理
- 有 NEEDS_CONTEXT → 提供信息后重新派发
- 有 BLOCKED → 升级给创始人或合并到单一调查

## 5. Anti-Rationalization（反合理化）

| 借口 | 现实 |
|------|------|
| 「任务太小不值得并行」 | 并行的开销只是写指令，几乎免费 |
| 「我一个人做更快」 | 3 个独立问题串行 vs 并行 = 3x 时间差 |
| 「指令太麻烦了，简单说就行」 | 模糊指令 → Agent 走偏 → 浪费全部时间 |
| 「应该没有冲突」 | 「应该」不是证据，跑集成测试才是 |
| 「Agent 说 DONE 了，应该没问题」 | Agent 的 DONE 是个体报告，不是集成验证 |

### Red Flags 自检

- 「所有 Agent 都 DONE 了，直接合并」→ 还没跑集成测试
- 「这个失败应该和那个相关」→ 还没验证就假设关联
- 「给 Agent 说修复所有问题就行」→ 范围太大，缺少四要素
- 「不用写约束了，Agent 应该知道」→ Agent 不知道你脑子里想的

## 6. Verification（验证）

**DoD 条目**：
- [ ] 独立域已识别，确认无交叉依赖
- [ ] 每个 Agent 指令包含四要素（Scope / Goal / Constraint / Output）
- [ ] 每个 Agent 返回了四状态码
- [ ] 集成测试全套通过
- [ ] 无 Agent 间代码冲突

## 7. Change Policy

- Patch：示例增补、模板改进
- Minor：新增协调策略、新增状态处理规则
- Major：改变四要素指令结构或四状态模型（需 ADR）
