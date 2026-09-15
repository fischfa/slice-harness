# <observable behavior>

**Status:** planned | building | done<br>
**Started:** YYYY-MM-DD

## What it does

Observable outcomes, important edge cases and exclusions. Give an independent
reviewer enough to judge correctness without the original conversation.

## Why

Only rationale that changes implementation judgment.

## What proves it

- Requirement → named test/case/check and the property it distinguishes.
- Meaningful proof gaps and practical limits; a listed gap is not automatically
  acceptable for an important requirement.

## Decisions

Durable constraints and governing ADR links. Ordinary local choices need no ADR.

## Execution

**Branch / base:** actual branch and base revision<br>
**Writer / checkout:** specific person or working-session ID and checkout when
concurrent slices are active; omit for sequential work<br>
**Scope / exclusions:** bounded permitted work

| Task | Outcome | Proof | Depends on | State |
|---|---|---|---|---|
| T1 | Observable result | Named check | — | pending |

Task states: pending, active, blocked, complete. Omit the table for one obvious
outcome. Task completion is not slice completion.

**Next action:** exact task, human-started review, or smallest unresolved decision<br>
**Review handoff:** neutral packet from `docs/guide/review.md`

## Open questions

Only questions/assumptions that materially change behavior, architecture, scope,
or proof. Stop dependent work on unsupported load-bearing assumptions.

---

## Built

Compact result, deviations, requirement-to-proof links, actual commands/results,
tested revision or working-tree identity, assumptions and unverified work. No
chronological transcript or model diary.

## Review

Pending until human-started independent review. Record reviewed scope/date,
outcome, substantive finding IDs, dispositions and fix proof. Distinguish PASS
from a pending final gate.
