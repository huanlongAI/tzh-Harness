# Skill 编写 TDD 循环规范（Skill Writing as TDD）

- Name: skill-writing-tdd
- Type: standard
- Status: DRAFT
- Version: 0.1.0
- Owner: TZH
- Date: 2026-03-22
- Related:
  - tzh-Harness/00-principles/README.md（P7 封装为制品）
  - tzh-Harness/00-principles/anti-rationalization.md
  - 来源：obra/superpowers `skills/writing-skills/SKILL.md` 的 TDD 方法论改造

---

## 1. 核心理念

> **编写 Skill 就是为 Agent 行为编写测试。**
> SKILL.md 是 Spec（规格），Agent 的执行是 Implementation（实现），Eval 是 Test Suite（测试套件）。

这一类比来自 superpowers 框架的 "Writing Skills" 方法论：Skill 文档不是「说明书」，而是「行为契约」。如果 Agent 的行为不符合 SKILL.md 的描述，那就是一个 bug——修 Skill 或修 Agent 配置，而不是接受偏差。

---

## 2. RED-GREEN-REFACTOR 循环

### 2.1 RED — 发现行为偏差

1. **观察 Agent 实际行为**：运行 Skill，记录 Agent 的完整输出
2. **对照预期**：逐条对比 SKILL.md 中的规则 vs 实际输出
3. **标记失败**：
   - 缺失：Skill 规定了但 Agent 没做
   - 多余：Agent 做了但 Skill 没要求（YAGNI）
   - 偏差：做了但方式/格式/内容不符

**产出**：失败清单（每条含：规则引用 + 实际输出 + 期望输出）

### 2.2 GREEN — 修改 Skill 使行为符合预期

1. **诊断根因**：
   - Agent 不理解？→ 措辞不够清晰 / 缺少示例
   - Agent 理解但不遵守？→ 缺少 Authority（祈使句）/ 缺少 HARD-GATE
   - Agent 遵守但效果差？→ 规则本身需要调整
2. **修改 SKILL.md**：
   - 增加 Good/Bad 正反示例（最有效的改进手段）
   - 将「建议」改为「必须」（Authority 原则）
   - 为关键规则添加 `<HARD-GATE>` 阻断标记
   - 调整规则顺序（重要的放前面）
3. **重新运行**：验证修改后 Agent 行为是否对齐

**产出**：通过的 Skill 版本 + 验证证据

### 2.3 REFACTOR — 优化 Skill 结构

1. **精简**：合并重复规则，删除冗余指令
2. **重组**：按执行顺序排列规则（Agent 逐条执行效率最高）
3. **提取**：将通用模式提取到共享的 Harness 原则中
4. **CSO（Claude Search Optimization）**：优化关键术语的措辞，使 Skill 更容易被 Agent 精确理解

**产出**：更精简、更高效的 SKILL.md

---

## 3. Skill 文档结构规范

每个 SKILL.md 必须包含以下部分（Harness P7 要求）：

```
# Skill 名称
- Name / Type / Status / Version / Owner / Date / Related

## 1. Purpose（目的）
  - 一句话说清这个 Skill 解决什么问题
  - Non-goals（≥1 条）

## 2. Trigger（触发条件）
  - 什么情况下使用这个 Skill
  - 什么情况下不使用

## 3. Rules（规则）
  - 用祈使句（Authority 原则）
  - 关键规则用 <HARD-GATE> 标记
  - 每条规则配 Good/Bad 示例（至少关键规则）

## 4. Workflow（工作流）
  - 按步骤排列
  - 标注门禁点和检查点

## 5. Anti-Rationalization（反合理化）
  - 本 Skill 特有的常见借口反驳表
  - Red Flags 自检项

## 6. Verification（验证）
  - DoD 条目
  - 验证命令或手工检查步骤
```

---

## 4. 说服力写作原则

基于 Cialdini (2021) + Meincke et al. (2025) N=28,000 LLM 对话实验：

| 原则 | 应用方式 | 效果 |
|------|---------|------|
| **Authority（权威）** | 用「你必须」而非「建议你」 | 合规率显著提升 |
| **Commitment（承诺）** | 要求 Agent 宣告「我正在执行 [X] 流程」 | 宣告后违反更难合理化 |
| **Scarcity（紧迫）** | 用「在 X 之前」而非「在方便的时候」 | 创造执行紧迫感 |

**禁用**：Liking（讨好/认同）——产生谄媚而非纪律。

---

## 5. Eval 设计指引

每个 Skill 应配备至少一个 Eval：

1. **Golden Path Test**：给定标准输入，Agent 输出是否符合 DoD 全部条目
2. **Edge Case Test**：给定边界条件输入，Agent 是否正确触发门禁/拒绝/升级
3. **Anti-Pattern Test**：给定诱导 Agent 跳过规则的输入，Agent 是否仍然遵守

Eval 结果只有 PASS / FAIL，不接受「部分通过」。

---

## 6. Change Policy

- Patch：文案修订、示例增补
- Minor：新增规则条目、新增 Eval
- Major：改变 Skill 结构模板、改变 TDD 循环步骤（需 ADR）
