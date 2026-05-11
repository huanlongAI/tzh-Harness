# JH-002 PR #32 Engineering-Anchor D7 Checklist

> Case: JH-002 / 美人计智能体
> Scope: engineering-anchor D7 observation for `hl-scene-app` PR #32.
> Due time: 2026-05-12T15:38:32+08:00.
> Status before due time: pending.

This checklist prepares the D7 observation only. It is not a signed JH-002
business baseline and must not import unsigned cross-conversation content.

## Anchor

| Field | Value |
|---|---|
| Anchor PR | `huanlongAI/hl-scene-app#32` |
| Anchor title | `feat: add P1.5 neutral LLM gateway boundary` |
| Merged at | `2026-05-05T07:38:32Z` / `2026-05-05T15:38:32+08:00` |
| Merge commit | `fddaff30edb58f4fe57d9debc942f0f25f04cc3d` |
| D7 due | `2026-05-12T15:38:32+08:00` |

## Observe Only After Due Time

Do not mark the PR #32 engineering-anchor D7 checkpoint observed before
`2026-05-12T15:38:32+08:00`.

At or after the due time, refresh evidence before writing a new observation:

```bash
git -C /Users/tzh/Workspace/01_Repos/_governance/tzh-Harness fetch --prune origin
git -C /Users/tzh/Workspace/01_Repos/huanlong/hl-scene-app fetch --prune origin
git -C /Users/tzh/Workspace/01_Repos/_governance/tzhOS fetch --prune origin
git -C /Users/tzh/Workspace/01_Repos/_governance/tzh-Harness status --short --branch
git -C /Users/tzh/Workspace/01_Repos/huanlong/hl-scene-app status --short --branch
gh pr view 32 --repo huanlongAI/hl-scene-app --json number,title,state,mergedAt,mergeCommit,statusCheckRollup
gh pr view 40 --repo huanlongAI/hl-scene-app --json number,title,state,mergedAt,mergeCommit,statusCheckRollup
gh api 'repos/huanlongAI/hl-scene-app/pulls?state=open' --jq '.[] | {number,title,head:.head.ref,base:.base.ref,updated_at,author:.user.login}'
gh run list --repo huanlongAI/hl-scene-app --branch main --limit 10 --json databaseId,displayTitle,conclusion,status,createdAt,updatedAt,headSha,workflowName,url
gh issue view 15 --repo huanlongAI/tzh-Harness --json number,title,state,updatedAt,comments,url
gh issue view 21 --repo huanlongAI/hl-scene-app --json number,title,state,updatedAt,comments,url
gh issue view 2 --repo huanlongAI/tech-cofounder-bot --json number,title,state,updatedAt,comments,url
```

## Minimum D7 Questions

- Has `hl-scene-app` `main` remained clean and synchronized with `origin/main`?
- Are the latest observable `main` checks green, especially Flutter analyze/test and Consistency Sentinel?
- Were new PRs merged after PR #40 that change the P1.5 LLM gateway boundary?
- Did `tzh-Harness#15` receive any signed boundary, grill, baseline, evidence, or human sign-off source?
- Did `hl-scene-app#21` receive operator confirmation for the credential-scope criteria?
- Did `tech-cofounder-bot#2` receive evidence that NODE-C/dahuizi can run Flutter locally?
- Did the rejected PR #40 dahuizi audit lane receive a valid replacement artifact, or is it still inconclusive?

## Evidence That Can Count

- Git commit SHAs and merge timestamps from GitHub.
- GitHub Actions status for PR #32, PR #40, and current `main`.
- GitHub issue comments or commits that explicitly sign or link durable sources.
- Dispatch receipts and arbitration summaries that include accepted structured audit evidence.
- Local repository status after fresh fetch.

## Evidence That Cannot Count

- Unsigned cross-conversation drafts.
- AI-generated summaries that are not linked to durable signed sources.
- Private chat, screenshots, or operator claims without a durable issue/comment/commit record.
- The rejected PR #40 dahuizi/Codex Runner outputs as accepted sign-off.
- Green CI as a substitute for signed JH-002 product baseline evidence.

## Expected Observation Result

Use `WARN` only if engineering evidence is stable but signed baseline evidence is still missing.
Use `INSUFFICIENT_EVIDENCE` if required GitHub or issue evidence cannot be refreshed.
Use `FAIL` only if durable evidence shows boundary violation, unsigned-source promotion, or accepted baseline drift.

Do not use `PASS` unless all Judgment Harness PASS gate inputs are present:

- signed boundary card
- signed grill decision tree
- signed baseline
- evidence lite/full
- human sign-off
- 24h / 72h / 7d observations
- no unsigned source promotion
