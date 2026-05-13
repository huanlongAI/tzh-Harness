# JH-002 Grill Intake Worksheet - 2026-05-13

> Case: JH-002 / 美人计智能体
> Status: UNSIGNED_DRAFT - not evidence, not baseline
> Tracker: https://github.com/huanlongAI/tzh-Harness/issues/15
> Accepted boundary source: https://github.com/huanlongAI/tzh-Harness/issues/15#issuecomment-4428892028

This worksheet converts the accepted boundary into discrete grill questions that
Founder can answer or replace in the signed intake ledger.

It is not a signed source. It must not be copied into the evidence pack as a
grill trace until Founder or an authorized human signs the selected question
rows in `tzh-Harness#15` or links an equivalent durable signed source.

## Hard Boundaries

- Do not treat this worksheet as a JH-002 product baseline.
- Do not import unsigned cross-conversation drafts, AI outputs, chats, or
  process notes.
- Do not expose secrets, token material, private customer data, or credential
  prefixes.
- Do not use NODE-R for this lane.
- Do not open `hl-scene-app` product-code work unless a future signed baseline
  creates a concrete engineering acceptance target.
- Keep PR #40 dahuizi/Codex Runner audit output rejected/inconclusive unless a
  future signed source explicitly changes that handling.

## How To Sign

Founder may sign one row, several rows, or a replacement grill tree by posting a
new comment in Issue #15 using this shape:

```text
Signed JH-002 source

Scope: grill
Source URL or commit: https://github.com/huanlongAI/tzh-Harness/blob/main/30-evals/judgment-harness-observation/cases/JH-002-grill-intake-worksheet-20260513.md
Signer: Founder / tongzhenghui
Timestamp: <ISO timestamp>

Signed grill rows:
- G-001: Human choice = <A/B/C/...>; notes = <optional>
- G-002: Human choice = <A/B/C/...>; notes = <optional>

I confirm this source may be used for JH-002 evidence intake. Unsigned cross-conversation content remains excluded unless explicitly linked above as a signed source.
```

## Recommended First Grill Bundle

Judgment Harness says grill should be one question at a time by default, with
related subquestions capped at three. The recommended first bundle is G-001 to
G-003 because these decide whether a baseline may be accepted at all.

| ID | Question | Why it matters | Risk if wrong | Candidate options | Recommended option | Human choice | Source / status |
|---|---|---|---|---|---|---|---|
| G-001 | What is the next signed source type for JH-002? | The current state has accepted boundary only; the next source must not be guessed by NODE-M. | Skipping the intended source type can turn an AI draft or process note into apparent evidence. | A: sign grill first. B: link/sign an already durable baseline directly. C: pause intake and keep JH-002 `NOT_READY_FOR_PASS`. | A, unless Founder already has a durable baseline source ready. | `TBD - requires signed source` | Draft question from accepted boundary and Issue #15 request. |
| G-002 | What kind of baseline is allowed for the current JH-002 lane? | The accepted boundary excludes confirming a full product plan, provider integration, user data, pricing, or new code implementation. | A product baseline could be inferred from engineering evidence or cross-conversation context, violating the signed boundary. | A: observation-only Judgment Harness baseline. B: product baseline only if a separate durable source is signed. C: no baseline yet; classify as evidence gap. | A or C; do not select B without a separate signed durable product source. | `TBD - requires signed source` | Draft question from accepted boundary non-goals. |
| G-003 | Does any downstream `hl-scene-app` product-code work become authorized before a signed baseline exists? | The boundary says green CI and PR evidence are engineering evidence only, not a product baseline. | Engineering could continue under an assumed product direction, creating execution-input drift. | A: no product-code work. B: governance/evidence docs only. C: product-code work only after a signed baseline creates a concrete acceptance target. | A plus B for governance/evidence files only. | `TBD - requires signed source` | Draft question from accepted boundary and PASS ledger non-actions. |

## Remaining Grill Queue

These rows should be signed separately or in a later bundle if still relevant.

| ID | Question | Why it matters | Risk if wrong | Candidate options | Recommended option | Human choice | Source / status |
|---|---|---|---|---|---|---|---|
| G-004 | How should PR #40 dahuizi/Codex Runner audit evidence be handled? | PR #40 is merged and CI-green, but the dahuizi audit artifact was rejected/inconclusive. | Counting it as accepted sign-off would corrupt the evidence chain; ignoring it entirely may hide residual audit risk. | A: keep rejected/inconclusive. B: retry only with schema precheck or different executor. C: accept CI-only evidence with explicit concerns. D: request remediation/rollback. | A until Founder selects B, C, or D in a signed source. | `TBD - requires signed source` | Draft question from observation log and PASS ledger. |
| G-005 | Do `hl-scene-app#21` and `tech-cofounder-bot#2` block JH-002 PASS, or only block external readiness? | Both blockers remain open and affect credential/runtime confidence, but neither supplies a signed product baseline. | PASS could be claimed while external readiness or audit reproducibility remains unresolved. | A: they block PASS unless resolved or explicitly waived. B: they are tracked separately and do not block baseline intake. C: split into separate follow-up after signed baseline. | A for PASS; B may be acceptable for continuing signed intake. | `TBD - requires signed source` | Draft question from current external blocker state. |
| G-006 | What is the minimum evidence record required after grill but before baseline sign-off? | The evidence pack still has `TBD` in facts, assumptions, judgments, and preferences. | Baseline could be signed without separating facts from assumptions or human judgments from preferences. | A: evidence lite only. B: evidence full for any external claims. C: defer evidence until baseline draft exists. | A, with B triggered for external facts. | `TBD - requires signed source` | Draft question from evidence pack acceptance criteria. |

## Non-Acceptance Notice

Until a human signs the chosen row(s), this worksheet has only draft status:

- It does not fill `Grill trace source`.
- It does not change `Signed baseline source`.
- It does not authorize product-code work.
- It does not change the current verdict: `NOT_READY_FOR_PASS - boundary accepted, baseline unsigned`.
