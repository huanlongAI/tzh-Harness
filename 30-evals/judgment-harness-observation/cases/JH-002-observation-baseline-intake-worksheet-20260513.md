# JH-002 Observation-Only Baseline Intake Worksheet - 2026-05-13

> Case: JH-002 / 美人计智能体
> Status: UNSIGNED_DRAFT - not signed baseline
> Tracker: https://github.com/huanlongAI/tzh-Harness/issues/15
> Accepted boundary source: https://github.com/huanlongAI/tzh-Harness/issues/15#issuecomment-4428892028
> Accepted grill source: https://github.com/huanlongAI/tzh-Harness/issues/15#issuecomment-4438289822

This worksheet prepares the next signed source: an observation-only Judgment
Harness baseline. It is draft scaffolding only.

It is not a signed source, not a product baseline, and not authorization for
`hl-scene-app` product-code work. The evidence pack baseline section must remain
`TBD - requires signed source` until Founder or an authorized human signs a
baseline source in `tzh-Harness#15` or links an equivalent durable source.

## Hard Boundaries

- Keep this baseline observation-only.
- Do not confirm a complete product plan, business strategy, user data, pricing,
  provider, real provider integration, or new code implementation.
- Do not promote unsigned cross-conversation drafts, AI outputs, chats, or
  process notes into evidence.
- Do not expose secrets, token material, private customer data, or credential
  prefixes.
- Do not use NODE-R for the current lane.
- Do not open `hl-scene-app` product-code work unless a future signed baseline
  explicitly creates a concrete engineering acceptance target.
- Keep PR #40 dahuizi/Codex Runner audit output rejected/inconclusive unless a
  future signed source explicitly changes that handling.

## Source Dependencies

| Source | Status | Link |
|---|---|---|
| Boundary | accepted | https://github.com/huanlongAI/tzh-Harness/issues/15#issuecomment-4428892028 |
| Grill G-001 to G-003 | accepted | https://github.com/huanlongAI/tzh-Harness/issues/15#issuecomment-4438289822 |
| Grill G-004 to G-006 | unsigned draft | `JH-002-grill-intake-worksheet-20260513.md` |

## Candidate Observation-Only Baseline

Founder may sign this as-is, edit it, or replace it with another durable signed
baseline source.

| Field | Candidate value | Source / note |
|---|---|---|
| Baseline version | `observation-baseline-v1-20260513` | Draft value; requires signed source. |
| Goal | Observe and verify whether Judgment Harness prevents goal, fact, judgment-responsibility, and execution-input drift in JH-002. | From signed boundary. |
| Non-goals | Do not confirm a full product plan, business strategy, user data, pricing, provider, real provider integration, or new code implementation. | From signed boundary and grill G-002. |
| Audience / users | NODE-M / tzh-Harness observation lane only. | Observation-only scope from grill G-002. |
| Constraints | Use `tzh-Harness#15`, tzh-Harness observation files, GitHub PR/issue/commit/CI evidence, and future durable sources explicitly signed or linked by Founder. Exclude unsigned cross-conversation drafts, AI outputs, chats, process files, secrets, tokens, and private customer data. | From signed boundary. |
| Key judgments | G-001 = sign grill first; G-002 = observation-only baseline, not product baseline; G-003 = no `hl-scene-app` product-code work before signed baseline, governance/evidence docs may continue. | From signed grill. |
| Dependencies / upstream truth sources | Boundary source, grill source, observation log, PASS readiness ledger, GitHub issue/PR/commit/CI evidence. | Durable sources only. |
| Downstream deliverables | Governance/evidence documents only: update evidence pack, PASS readiness ledger, and observation log. | Does not authorize product code. |
| Acceptance criteria | Baseline source is signed; baseline remains observation-only; facts/assumptions/judgments/preferences stay separated; no unsigned source promotion; no product-code PR is opened from this baseline alone. | Draft criteria for signing. |
| Forbidden zones | Product baseline, customer/private data, secrets/token material, provider credentials, real provider binding, new code implementation, PR #40 audit rehabilitation without a new signed source. | From boundary/grill. |

## Suggested Signed Comment

```text
Signed JH-002 source

Scope: baseline
Source URL or commit: https://github.com/huanlongAI/tzh-Harness/blob/main/30-evals/judgment-harness-observation/cases/JH-002-observation-baseline-intake-worksheet-20260513.md
Signer: Founder / tongzhenghui
Timestamp: <ISO timestamp>

Baseline version: observation-baseline-v1-20260513
Goal: Observe and verify whether Judgment Harness prevents goal, fact, judgment-responsibility, and execution-input drift in JH-002.
Non-goals: Do not confirm a full product plan, business strategy, user data, pricing, provider, real provider integration, or new code implementation.
Audience / users: NODE-M / tzh-Harness observation lane only.
Constraints: Use durable signed sources only; exclude unsigned cross-conversation drafts, AI outputs, chats, process files, secrets, tokens, and private customer data.
Key judgments: G-001=A, G-002=A, G-003=A from the accepted grill source.
Dependencies / upstream truth sources: accepted boundary source, accepted grill source, observation log, PASS readiness ledger, and GitHub PR/issue/commit/CI evidence.
Downstream deliverables: governance/evidence document updates only; no product-code work.
Acceptance criteria: baseline remains observation-only; facts/assumptions/judgments/preferences stay separated; no unsigned source promotion; no product-code PR is opened from this baseline alone.
Forbidden zones: product baseline, customer/private data, secrets/token material, provider credentials, real provider binding, new code implementation, PR #40 audit rehabilitation without a new signed source.

I confirm this JH-002 observation-only baseline version as the signed basis for downstream observation/review. Unsigned cross-conversation content remains excluded unless explicitly linked above as a signed source.
```

## Non-Acceptance Notice

Until a human signs a baseline source:

- This worksheet does not fill `Signed baseline source`.
- This worksheet does not fill `Human sign-off`.
- This worksheet does not make JH-002 `PASS`.
- This worksheet does not authorize product-code work.
