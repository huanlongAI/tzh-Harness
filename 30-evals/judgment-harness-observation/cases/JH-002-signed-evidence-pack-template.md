# JH-002 Signed Evidence Pack Template

> Status: PARTIAL-EVIDENCE-PACK - boundary, grill, baseline, and evidence accepted; sign-off missing
> Case: JH-002 / 美人计智能体
> Upstream method source: `tzhOS/ai/JUDGMENT-HARNESS.md`
> Observation asset: `tzh-Harness/30-evals/judgment-harness-observation/`
> Tracker: https://github.com/huanlongAI/tzh-Harness/issues/15
> Accepted boundary source: https://github.com/huanlongAI/tzh-Harness/issues/15#issuecomment-4428892028
> Accepted grill source: https://github.com/huanlongAI/tzh-Harness/issues/15#issuecomment-4438289822
> Accepted baseline source: https://github.com/huanlongAI/tzh-Harness/issues/15#issuecomment-4438727029
> Accepted evidence source: https://github.com/huanlongAI/tzh-Harness/issues/15#issuecomment-4439096599

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
| Evidence pack version | yes | `evidence-lite-v1-20260513` |
| Founder sign-off source | yes | `TBD - requires human sign-off source` |
| Signed baseline source | yes | https://github.com/huanlongAI/tzh-Harness/issues/15#issuecomment-4438727029 |
| Boundary source | yes | https://github.com/huanlongAI/tzh-Harness/issues/15#issuecomment-4428892028 |
| Grill trace source | yes | https://github.com/huanlongAI/tzh-Harness/issues/15#issuecomment-4438289822 |
| Evidence source | yes | https://github.com/huanlongAI/tzh-Harness/issues/15#issuecomment-4439096599 |
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
| Open judgments | Final human sign-off remains missing; `hl-scene-app#21` and `tech-cofounder-bot#2` remain external blockers. | Observation log and readiness ledger |
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

Accepted baseline source: https://github.com/huanlongAI/tzh-Harness/issues/15#issuecomment-4438727029

The comment body timestamp field used a placeholder, so audit timing uses the
durable GitHub comment timestamp: 2026-05-13T08:03:31Z /
2026-05-13T16:03:31+08:00.

| Field | Value | Source / status |
|---|---|---|
| Baseline version | `observation-baseline-v1-20260513` | Signed baseline source |
| Signer | Founder / tongzhenghui | Signed baseline source |
| Sign-off timestamp | 2026-05-13T08:03:31Z / 2026-05-13T16:03:31+08:00 | GitHub comment timestamp |
| Goal | Observe and verify whether Judgment Harness prevents goal, fact, judgment-responsibility, and execution-input drift in JH-002. | Signed baseline source |
| Non-goals | Do not confirm a full product plan, business strategy, user data, pricing, provider, real provider integration, or new code implementation. | Signed baseline source |
| Audience / users | NODE-M / tzh-Harness observation lane only. | Signed baseline source |
| Constraints | Use durable signed sources only; exclude unsigned cross-conversation drafts, AI outputs, chats, process files, secrets, tokens, and private customer data. | Signed baseline source |
| Key judgments | G-001=A, G-002=A, G-003=A from the accepted grill source. | Signed baseline source |
| Dependencies / upstream truth sources | Accepted boundary source, accepted grill source, observation log, PASS readiness ledger, and GitHub PR/issue/commit/CI evidence. | Signed baseline source |
| Downstream deliverables | Governance/evidence document updates only; no product-code work. | Signed baseline source |
| Acceptance criteria | Baseline remains observation-only; facts/assumptions/judgments/preferences stay separated; no unsigned source promotion; no product-code PR is opened from this baseline alone. | Signed baseline source |
| Forbidden zones | Product baseline, customer/private data, secrets/token material, provider credentials, real provider binding, new code implementation, PR #40 audit rehabilitation without a new signed source. | Signed baseline source |

Baseline acceptance:

- [x] The baseline has an explicit human sign-off for observation-only baseline scope.
- [x] The baseline distinguishes goals from non-goals.
- [x] The baseline is sufficient for downstream observation/review without re-asking the core direction.
- [x] The baseline does not contain or depend on unsigned source promotion.
- [x] Any engineering task derived from the baseline cites the signed baseline source.

## 4. Evidence Lite / Full

All JH-002 observations require at least evidence lite. Use evidence full only when external market, policy, competitor, technical, legal, or other unstable facts are being asserted.

Accepted evidence source: https://github.com/huanlongAI/tzh-Harness/issues/15#issuecomment-4439096599

Evidence level: lite.

The comment body timestamp field used a placeholder, so source timing uses the
durable GitHub comment timestamp: 2026-05-13T08:52:33Z /
2026-05-13T16:52:33+08:00.

### 4.1 Facts

| Fact | Source | Verification status |
|---|---|---|
| F-001: JH-002 boundary source is accepted for boundary scope only. | https://github.com/huanlongAI/tzh-Harness/issues/15#issuecomment-4428892028 | Signed evidence source accepted row F-001 |
| F-002: JH-002 grill rows G-001 to G-003 are accepted. | https://github.com/huanlongAI/tzh-Harness/issues/15#issuecomment-4438289822 | Signed evidence source accepted row F-002 |
| F-003: JH-002 observation-only baseline `observation-baseline-v1-20260513` is accepted. | https://github.com/huanlongAI/tzh-Harness/issues/15#issuecomment-4438727029 | Signed evidence source accepted row F-003 |
| F-004: `hl-scene-app#21` remains open for operator-side credential confirmation. | https://github.com/huanlongAI/hl-scene-app/issues/21 | Signed evidence source accepted row F-004; GitHub API rechecked open on 2026-05-15 |
| F-005: `tech-cofounder-bot#2` remains open for NODE-C Flutter runtime readiness. | https://github.com/huanlongAI/tech-cofounder-bot/issues/2 | Signed evidence source accepted row F-005; GitHub API rechecked open on 2026-05-15 |
| F-006: `hl-scene-app` PR #40 is merged, but its dahuizi/Codex Runner audit lane remains rejected/inconclusive in JH-002 evidence. | https://github.com/huanlongAI/hl-scene-app/pull/40 and observation log | Signed evidence source accepted row F-006; PR merged state rechecked on 2026-05-15 |

### 4.2 Assumptions

| Assumption | Why acceptable | Expiry / trigger for recheck |
|---|---|---|
| A-001: Durable GitHub issue comments from Founder or an authorized human are acceptable signed JH-002 sources. | Boundary, grill, baseline, and evidence intake all use Issue #15 as the signed evidence ledger. | Recheck if Founder changes intake ledger policy. |
| A-002: Evidence lite is sufficient for the current observation-only governance lane if no unstable external facts are asserted. | Accepted baseline excludes product plan, provider integration, market claims, pricing, customer data, and code implementation. | Switch to evidence full if external market, policy, legal, technical, competitor, or provider facts are asserted. |
| A-003: Current external blocker states must be rechecked before any future PASS decision. | Issue state can change after the worksheet and signed evidence comment. | Recheck immediately before final sign-off or PASS consideration. |

### 4.3 Judgments

| Judgment | Decider | Rationale | Source |
|---|---|---|---|
| J-001: JH-002 remains `NOT_READY_FOR_PASS` after baseline acceptance. | Founder / tongzhenghui | At signing time, evidence lite/full and final human sign-off remained missing; after intake, final human sign-off and external blocker resolution still remain missing. | Signed evidence source |
| J-002: No new `hl-scene-app` product-code PR is authorized by the accepted baseline alone. | Founder / tongzhenghui | The accepted baseline says downstream deliverables are governance/evidence document updates only; no product-code work. | Signed evidence source and accepted baseline source |
| J-003: PR #40 dahuizi/Codex Runner outputs cannot count as accepted sign-off without a new signed source or replacement audit artifact. | Founder / tongzhenghui | The accepted boundary and baseline forbid PR #40 audit rehabilitation without a new signed source. | Signed evidence source, boundary source, and baseline source |

### 4.4 Preferences

| Preference | Owner | Constraint impact | Source |
|---|---|---|---|
| P-001: Prefer signed evidence lite before final human sign-off. | Founder / tongzhenghui | Keeps evidence separation before any PASS decision. | Signed evidence source |
| P-002: Keep this lane in `tzh-Harness` governance/evidence documents only. | Founder / tongzhenghui | Prevents product-code scope creep while evidence remains incomplete. | Signed evidence source |

Evidence acceptance:

- [x] Facts, assumptions, judgments, and preferences are separated.
- [x] Every fact has a durable source or is marked unverified.
- [x] Every judgment has a human decider or remains pending.
- [x] External facts either use source links and dates or remain limited to GitHub evidence state; no evidence-full-only claim is asserted.
- [x] No secret or private customer data is copied into the evidence pack.

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
- [x] Signed baseline version exists.
- [x] Evidence lite/full records separate facts, assumptions, judgments, and preferences.
- [ ] 24h / 72h / 7d observations are complete.
- [x] No unsigned source promotion occurred.
- [x] No downstream engineering or dispatch crossed the signed baseline boundary.
- [ ] Final human sign-off exists.
- [ ] Product-as-Runtime / Mode B boundary remains stable or any change is separately signed.
