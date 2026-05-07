# JH-002 Signed Evidence Pack Template

> Status: TEMPLATE
> Case: JH-002 / 美人计智能体
> Upstream method source: `tzhOS/ai/JUDGMENT-HARNESS.md`
> Observation asset: `tzh-Harness/30-evals/judgment-harness-observation/`
> Tracker: https://github.com/huanlongAI/tzh-Harness/issues/15

This template defines the minimum durable evidence needed before JH-002 can be considered for `PASS`.

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
| Evidence pack version | yes | `TBD - requires signed source` |
| Founder sign-off source | yes | `TBD - requires signed source` |
| Signed baseline source | yes | `TBD - requires signed source` |
| Boundary source | yes | `TBD - requires signed source` |
| Grill trace source | yes | `TBD - requires signed source` |
| Evidence source | yes | `TBD - requires signed source` |
| Observation log source | yes | `30-evals/judgment-harness-observation/logs/observation-log.jsonl` |

## 1. Boundary Card

Boundary is valid only when each material input is classified as durable source, signed decision, draft, process note, chat, AI output, or forbidden material.

| Field | Value | Source / status |
|---|---|---|
| Task in one sentence | `TBD - requires signed source` | `TBD` |
| Current background | `TBD - requires signed source` | `TBD` |
| Target user / operator | `TBD - requires signed source` | `TBD` |
| Initial goal | `TBD - requires signed source` | `TBD` |
| Explicit non-goals | `TBD - requires signed source` | `TBD` |
| Known constraints | `TBD - requires signed source` | `TBD` |
| Available materials | `TBD - requires signed source` | `TBD` |
| Forbidden materials / zones | `Unsigned cross-conversation drafts, AI outputs, process files, instant messages, secrets, private customer data` | This template |
| Open judgments | `TBD - requires signed source` | `TBD` |
| Expected output | `TBD - requires signed source` | `TBD` |
| Review window | 24h / 72h / 7d | tzhOS Judgment Harness method |

Boundary acceptance:

- [ ] Truth sources are listed.
- [ ] Draft/process/chat/AI-output materials are explicitly separated from truth sources.
- [ ] Forbidden materials are named.
- [ ] Questions that cannot be guessed are listed.
- [ ] Founder or authorized human has confirmed the boundary.

## 2. Grill Decision Tree

Each row is one decision question. Do not merge unrelated judgments into one confirmation.

| ID | Question | Why it matters | Risk if wrong | Candidate options | Recommended option | Human choice | Source / status |
|---|---|---|---|---|---|---|---|
| G-001 | `TBD - requires signed source` | `TBD` | `TBD` | `TBD` | `TBD` | `TBD` | `TBD` |

Grill acceptance:

- [ ] Each key judgment has a discrete question.
- [ ] Each question records rationale and failure risk.
- [ ] Recommended options are clearly marked as recommendations, not decisions.
- [ ] Human choices are recorded with source links.
- [ ] Scope changes trigger a new grill entry instead of silent baseline drift.

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

- [ ] Boundary card exists and is signed or linked to a signed source.
- [ ] Grill decision tree exists and is signed or linked to a signed source.
- [ ] Signed baseline version exists.
- [ ] Evidence lite/full records separate facts, assumptions, judgments, and preferences.
- [ ] 24h / 72h / 7d observations are complete.
- [ ] No unsigned source promotion occurred.
- [ ] No downstream engineering or dispatch crossed the signed baseline boundary.
- [ ] Product-as-Runtime / Mode B boundary remains stable or any change is separately signed.
