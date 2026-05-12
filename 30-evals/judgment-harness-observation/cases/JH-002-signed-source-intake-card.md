# JH-002 Signed Source Intake Card

> Case: JH-002 / 美人计智能体
> Tracker: https://github.com/huanlongAI/tzh-Harness/issues/15
> Status: INTAKE_FORM

This card is the minimal form for submitting a signed JH-002 source. It is
not a product baseline and does not itself sign any field.

Use this only for durable sources that a human is explicitly authorizing for
JH-002 evidence intake.

## Copy-Paste Form

```text
Signed JH-002 source

Scope: <boundary | grill | baseline | evidence | human sign-off>
Source URL or commit: <durable GitHub issue, PR, comment, commit, or artifact link>
Signer: <human / role>
Timestamp: <ISO timestamp>

I confirm this source may be used for JH-002 evidence intake. Unsigned cross-conversation content remains excluded unless explicitly linked above as a signed source.
```

## Required Checks

Before a source can fill any JH-002 evidence-pack field:

- [ ] The source is durable: GitHub issue, PR, comment, commit, or equivalent signed artifact.
- [ ] The signer is a human or authorized role, not an AI-generated summary.
- [ ] The scope is explicit: boundary, grill, baseline, evidence, or human sign-off.
- [ ] The linked content does not expose secrets, token material, private keys, cookies, private callback URLs, or unreleased customer data.
- [ ] The linked content does not silently import unsigned cross-conversation drafts, process notes, chats, or AI outputs.
- [ ] The source can be cited from `JH-002-signed-evidence-pack-template.md`.

## Field Mapping

| Scope | Evidence pack section it can fill | Still required after submission |
|---|---|---|
| `boundary` | Boundary Card | Verify all material inputs are classified and forbidden zones are named. |
| `grill` | Grill Decision Tree | Verify each decision question has rationale, risk, recommendation, and human choice. |
| `baseline` | Signed Baseline | Verify goal, non-goals, users, constraints, key judgments, deliverables, and acceptance criteria are explicit. |
| `evidence` | Evidence Lite / Full | Verify facts, assumptions, judgments, and preferences are separated. |
| `human sign-off` | Human Sign-off | Verify signer, timestamp, signed artifact, scope, and revisit trigger are present. |

## What This Card Cannot Do

- It cannot convert green CI into a JH-002 product baseline.
- It cannot rehabilitate the rejected PR #40 dahuizi/Codex Runner audit outputs.
- It cannot close `hl-scene-app#21` or `tech-cofounder-bot#2`.
- It cannot authorize new `hl-scene-app` product-code work.
- It cannot make JH-002 `PASS` without all required signed inputs and observations.
