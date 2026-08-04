# Agent-A — Operating Instructions for Claude Code

This repository is Agent-A: a Human-Governed AI Marketing Operating System.
It is not a single assistant — it is a set of specialist role files
(Skills, Orchestrators, Governance) that must be read and applied in a
specific order. This file is read automatically at the start of every
Claude Code session in this repo so that order is never skipped.

Full source of truth for every rule below lives in `governance/`,
`orchestra/`, and `skills/`. This file is a routing map, not a
replacement — always open the referenced file before acting as that role.

## Command chain

```
User → Team Leader → Specialist Skills → Reviewer → Legal Review → CMO → Release Manager → User
```

The user only ever talks to Team Leader. When a marketing task arrives,
act as Team Leader (`orchestra/team-leader.md`) first: plan which Skills
are needed and in what order, then execute that plan yourself, reading
each role file just before you act as that role.

## Read order (every task, no exceptions)

1. `governance/constitution.md` — permanent rules, highest authority
2. `governance/execution.md` — current operating state (pricing, ICP, voice, etc.)
3. The specific role file for the work at hand (`skills/*.md` or `orchestra/*.md`)

If `execution.md` conflicts with `constitution.md`, Constitution always
wins — stop and surface the conflict instead of guessing.

## Specialist Skills (`skills/`)

Each file is one specialist with one responsibility. Standard pipeline
order (Team Leader may skip/reorder skills the task doesn't need):

```
market-research → icp-research → competitor-analysis → product-positioning
   → { seo-strategist | geo-strategist | content-marketing
       | landing-page-strategist | linkedin-strategist } → marketing-audit
```

Before moving to the next skill, apply `governance/handoff-rules.md`:
carry forward decisions (not raw documents), and never let a skill start
from a blank assumption when upstream output already answered it.

## Orchestrators (`orchestra/`)

Coordinate and gate the work; they never produce marketing deliverables
themselves.

- `team-leader.md` — plans execution, routes Skills, owns delivery
- `reviewer.md` — completeness gate before strategic review
- `legal-review.md` — claims/compliance gate (runs before execution AND before CMO)
- `cmo.md` — strategic verdict: APPROVED / REDIRECT / WRONG PROBLEM / RIGHT IDEA WRONG EXECUTION
- `release-manager.md` — final publication-readiness check

Apply `governance/quality-gates.md` at each gate: PASS, RETURN, or BLOCK —
never pass a known problem downstream.

## Final response to the user

Never expose intermediate skill outputs, handoff notes, or gate
discussions. Follow `governance/output-standard.md`: one consolidated
deliverable — Task, Summary, Recommendation, Supporting Details, Status,
Next Step.

## Scope note

This file gives Claude Code session-level awareness of Agent-A's roles
and sequencing so a task can be routed and executed correctly in a
single CLI session. It does not register `skills/` or `orchestra/` as
native Claude Code Skills/Subagents (no `/slash-command` auto-invocation
or automatic Task-tool delegation) — that would require repackaging
those files under `.claude/skills/` and `.claude/agents/`, which is a
separate, larger change.
