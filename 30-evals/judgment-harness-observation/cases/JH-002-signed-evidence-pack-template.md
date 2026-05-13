# JH-002 Signed Evidence Pack Template

> Status: PARTIAL-EVIDENCE-PACK - boundary and grill accepted; baseline unsigned
> Case: JH-002 / 美人计智能体
> Upstream method source: `tzhOS/ai/JUDGMENT-HARNESS.md`
> Observation asset: `tzh-Harness/30-evals/judgment-harness-observation/`
> Tracker: https://github.com/huanlongAI/tzh-Harness/issues/15
> Accepted boundary source: https://github.com/huanlongAI/tzh-Harness/issues/15#issuecomment-4428892028
> Accepted grill source: https://github.com/huanlongAI/tzh-Harness/issues/15#issuecomment-4438289822

This evidence pack tracks the minimum durable evidence needed before JH-002 can be considered for `PASS`.

It is not a product baseline. Do not fill business, product, customer, strategy, pricing, provider, credential, or private cross-conversation content here unless the content already exists in a signed durable source and is linked as evidence.

## Hard Boundaries

- Do not promote unsigned cross-conversation drafts, AI outputs, process files, or instant messages into decisions.
- Do not treat `hl-scene-app` engineering cleanup evidence as the JH-002 product baseline.
- Do not expose API keys, access tokens, private keys, cookies, credential prefixes, private callback URLs, or unreleased customer data.
- Do not use NODE-R for the current dahuizi audit lane.
- Do not open a new `hl-scene-app` product-code PR unless a signed baseline creates a concrete code task.
- Leave unknown fields as `TBD - requires signed source`.

## Source Ledger

| Item | Required | Value |
|---|---:|---|
| Case ID | yes | JH-002 |
| Case name | yes | 美人计智能体 |
| Method version | yes | `v0.1.3` |
| Evidence pack version | yes | `grill-v1-20260513` |
| Founder sign-off source | yes | `TBD - requires signed baseline / human sign-off source` |
| Signed baseline source | yes | `TBD - requires signed source` |
| Boundary source | yes | https://github.com/huanlongAI/tzh-Harness/issues/15#issuecomment-4428892028 |
| Grill trace source | yes | https://github.com/huanlongAI/tzh-Harness/issues/15#issuecomment-4438289822 |
| Evidence source | yes | `TBD - requires signed source` |
| Observation log source | yes | `30-evals/judgment-harness-observation/logs/observation-log.jsonl` |

## 1. Boundary Card

Boundary is valid only when each material input is classified as durable source, signed decision, draft, process note, chat, AI output, or forbidden material.

| Field | Value | Source / status |
|---|---|---|
| Task in one sentence | JH-002 / 美人计智能体 Judgment Harness 实战观察。 | Signed boundary source |
| Current background | Boundary source was submitted in `tzh-Harness#15` and accepted only for boundary intake. | GitHub issue comment created at 2026-05-12T08:56:17Z |
| Target user / operator | `TBD - requires signed source` | Not specified by boundary source |
| Initial goal | 只观察和验证 Judgment Harness 方法是否能防止目标、事实、判断责任和执行输入漂移。 | Signed boundary source |
| Explicit non-goals | 不在这里确认完整产品方案、商业策略、用户数据、定价、供应商、真实 provider 接入或新代码实现。 | Signed boundary source |
| Known constraints | `hl-scene-app` green CI and PR evidence are engineering evidence only; PR #40 dahuizi/Codex Runner rejected/inconclusive output is not accepted sign-off; current lane does not use NODE-R; NODE-M may not expand this boundary into a signed baseline. | Signed boundary source |
| Available materials | `tzh-Harness#15`; `tzh-Harness` observation files; GitHub PR/issue/commit/CI evidence; future durable sources explicitly signed or linked by Founder. | Signed boundary source |
| Forbidden materials / zones | 未签署的跨对话草稿、AI 输出、即时聊天、过程文件、密钥、token、私有客户资料。 | Signed boundary source |
| Open judgments | Signed baseline, evidence lite/full, and human sign-off remain missing; `hl-scene-app#21` and `tech-cofounder-bot#2` remain external blockers. | Observation log and readiness ledger |
| Expected output | NODE-M may update this Boundary Card from the signed source, but must not extend it into signed baseline. | Signed boundary source |
| Review window | 24h / 72h / 7d | tzhOS Judgment Harness method |

Boundary acceptance:

- [x] Truth sources are listed.
- [x] Draft/process/chat/AI-output materials are explicitly separated from truth sources.
- [x] Forbidden materials are named.
- [x] Questions that cannot be guessed are listed.
- [x] Founder or authorized human has confirmed the boundary.

## 2. Grill Decision Tree

Each row is one decision question. Do not merge unrelated judgments into one confirmation.

Accepted grill source: https://github.com/huanlongAI/tzh-Harness/issues/15#issuecomment-4438289822

The comment body timestamp field used a placeholder, so audit timing uses the
durable GitHub comment timestamp: 2026-05-13T07:10:25Z /
2026-05-13T15:10:25+08:00.

| ID | Question | Why it matters | Risk if wrong | Candidate options | Recommended option | Human choice | Source / status |
|---|---|---|---|---|---|---|---|
| G-001 | What is the next signed source type for JH-002? | The current state had accepted boundary only; the next source must not be guessed by NODE-M. | Skipping the intended source type can turn an AI draft or process note into apparent evidence. | A: sign grill first. B: link/sign an already durable baseline directly. C: pause intake and keep JH-002 `NOT_READY_FOR_PASS`. | A, unless Founder already has a durable baseline source ready. | A - sign grill first, do not jump to baseline. | Signed grill source |
| G-002 | What kind of baseline is allowed for the current JH-002 lane? | The accepted boundary excludes confirming a full product plan, provider integration, user data, pricing, or new code implementation. | A product baseline could be inferred from engineering evidence or cross-conversation context, violating the signed boundary. | A: observation-only Judgment Harness baseline. B: product baseline only if a separate durable source is signed. C: no baseline yet; classify as evidence gap. | A or C; do not select B without a separate signed durable product source. | A - current lane only allows observation-only Judgment Harness baseline, not product baseline. | Signed grill source |
| G-003 | Does any downstream `hl-scene-app` product-code work become authorized before a signed baseline exists? | The boundary says green CI and PR evidence are engineering evidence only, not a product baseline. | Engineering could continue under an assumed product direction, creating execution-input drift. | A: no product-code work. B: governance/evidence docs only. C: product-code work only after a signed baseline creates a concrete acceptance target. | A plus B for governance/evidence files only. | A - no downstream `hl-scene-app` product-code work before signed baseline; governance/evidence docs may continue. | Signed grill source |

Unsigned worksheet rows G-004 to G-006 remain draft only. They are not accepted
grill rows unless Founder signs them in a future durable source.

Grill acceptance:

- [x] Each accepted row has a discrete question.
- [x] Each accepted row records rationale and failure risk.
- [x] Recommended options are clearly marked as recommendations, not decisions.
- [x] Human choices are recorded with source links.
- [x] Scope changes trigger a new grill entry instead of silent baseline drift.

## 3. Signed Baseline

This section is not a baseline until a human sign-off source is linked.

| Field | Value | Source / status |
|---|---|---|
| Baseline version | `TBD - requires signed source` | `TBD` |
| Signer | `TBD - requires signed source` | `TBD` |
| Sign-off timestamp | `TBD - requires signed source` | `TBD` |
| Goal | `TBD - requires signed source` | `TBD` |
| Non-goals | `TBD - requires signed source` | `TBD` |
| Audience / users | `TBD - requires signed source` | `TBD` |
| Constraints | `TBD - requires signed source` | `TBD` |
| Key judgments | `TBD - requires signed source` | `TBD` |
| Dependencies / upstream truth sources | `TBD - requires signed source` | `TBD` |
| Downstream deliverables | `TBD - requires signed source` | `TBD` |
| Acceptance criteria | `TBD - requires signed source` | `TBD` |
| Forbidden zones | `TBD - requires signed source` | `TBD` |

Baseline acceptance:

- [ ] The baseline has an explicit human sign-off.
- [ ] The baseline distinguishes goals from non-goals.
- [ ] The baseline is sufficient for downstream review or execution without re-asking the core direction.
- [ ] The baseline does not contain or depend on unsigned source promotion.
- [ ] Any engineering task derived from the baseline cites the signed baseline source.

## 4. Evidence Lite / Full

All JH-002 observations require at least evidence lite. Use evidence full only when external market, policy, competitor, technical, legal, or other unstable facts are being asserted.

### 4.1 Facts

| Fact | Source | Verification status |
|---|---|---|
| `TBD - requires signed source` | `TBD` | `TBD` |

### 4.2 Assumptions

| Assumption | Why acceptable | Expiry / trigger for recheck |
|---|---|---|
| `TBD - requires signed source` | `TBD` | `TBD` |

### 4.3 Judgments

| Judgment | Decider | Rationale | Source |
|---|---|---|---|
| `TBD - requires signed source` | `TBD` | `TBD` | `TBD` |

### 4.4 Preferences

| Preference | Owner | Constraint impact | Source |
|---|---|---|---|
| `TBD - requires signed source` | `TBD` | `TBD` | `TBD` |

Evidence acceptance:

- [ ] Facts, assumptions, judgments, and preferences are separated.
- [ ] Every fact has a durable source or is marked unverified.
- [ ] Every judgment has a human decider or remains pending.
- [ ] External facts use evidence full with source links and dates.
- [ ] No secret or private customer data is copied into the evidence pack.

## 5. Human Sign-off

| Field | Value |
|---|---|
| Signer | `TBD - requires signed source` |
| Timestamp | `TBD - requires signed source` |
| Signed artifact / comment / commit | `TBD - requires signed source` |
| Scope of sign-off | `TBD - requires signed source` |
| Expiry / revisit trigger | `TBD - requires signed source` |

Sign-off statement to use when ready:

```text
I confirm this JH-002 baseline version as the signed basis for downstream observation/review. Unsigned cross-conversation content remains excluded unless explicitly linked above as a signed source.
```

## 6. Observation Checkpoints

| Checkpoint | Due / observed at | Status | Pass signals | Drift signals | Founder intervention | Next action |
|---|---|---|---|---|---|---|
| 24h | `TBD` | `pending` | `TBD` | `TBD` | `TBD` | `TBD` |
| 72h | `TBD` | `pending` | `TBD` | `TBD` | `TBD` | `TBD` |
| 7d | `TBD` | `pending` | `TBD` | `TBD` | `TBD` | `TBD` |

Observation acceptance:

- [ ] 24h observation is written to `observation-log.jsonl`.
- [ ] 72h observation is written to `observation-log.jsonl`.
- [ ] 7d observation is written to `observation-log.jsonl`.
- [ ] Each observation cites durable evidence only.
- [ ] Verdict remains `INSUFFICIENT_EVIDENCE` until required signed inputs and timed observations exist.

## 7. PASS Gate Checklist

JH-002 may only be considered for `PASS` when all items are complete:

- [x] Boundary card exists and is signed or linked to a signed source.
- [x] Grill decision tree exists and is signed or linked to a signed source.
- [ ] Signed baseline version exists.
- [ ] Evidence lite/full records separate facts, assumptions, judgments, and preferences.
- [ ] 24h / 72h / 7d observations are complete.
- [ ] No unsigned source promotion occurred.
- [ ] No downstream engineering or dispatch crossed the signed baseline boundary.
- [ ] Product-as-Runtime / Mode B boundary remains stable or any change is separately signed.
