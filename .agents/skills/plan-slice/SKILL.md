---
name: plan-slice
description: Plan one bounded feature or fix and its executable proof without editing application code; usable by Claude Code and Codex.
---

Read `AGENTS.md`, `docs/project-profile.md`, `docs/features/README.md`, the
relevant index row and feature. Inspect nearby code/callers, canonical contracts,
and accepted ADRs before asking ordinary repository questions. Use the feature
template to state observable behavior, meaningful edges/exclusions, rationale,
and proof per important requirement. Check that proposed setup reaches the
behavior and assertions distinguish a plausible broken result.

If the profile is `uninitialized`, do not convert an exploratory project-brief
conversation into feature planning or repository edits. Continue read-only
discussion until the owner explicitly starts `initialize-project`; normal feature
planning begins after `bootstrap-ready`.

For public-boundary changes, name the canonical contract and needed ADR/authored
case under `contracts/README.md`. Record a few outcome-oriented tasks and real
dependencies; entry files are hints, not a prescribed edit list. Keep branch/base,
scope, unresolved decisions and Next action sufficient for a fresh session. Index
new features. Do not put client/model selection in task records.

Stop with the concrete plan. Planning alone does not authorize application
implementation, commits or publishing. If important behavior/proof rests on an
unresolved decision, leave it open and use the harness escalation handoff. When a
request is too large for one reviewable proof and diff, split it into several
observable slices with indexed feature files, real dependencies and separate
handoffs. Escalate if the boundary itself cannot be settled from available
evidence; do not disguise a large request as one oversized task.
