# Codex entry

`AGENTS.md` and the [harness](harness.md) own engineering rules. Codex role skills
are under `.agents/skills/`. Start a new session for normal application
implementation and a fresh,
independent session for human-started review. Skills do not switch models or
authorize a transition.

```text
Discuss brief: discuss <project target> and architecture options over multiple
turns; no skill or repository writes. Capture accepted decisions for handoff.
$initialize-project Initialize this blueprint from <project brief> and the accepted
technology/architecture decision handoff; stop ready for review.
$plan-slice Plan <behavior> in docs/features/<behavior>.md; no application edits.
$implement-slice Execute <task> in docs/features/<behavior>.md; stop ready for review.
$advise-slice Answer only <consultation packet>; read-only, no implementation.
$review-slice Review <feature> from its neutral packet; review only, no edits.
$implement-slice Fix accepted findings <IDs> in <feature>; rerun affected proof.
$review-slice Recheck <IDs> against prior and new snapshot identities; no fixes.
Review closed for <feature>: read .claude/skills/verify/SKILL.md, run the
project-profile final gate on the reviewed/fixed tree, and record results.
Investigate only <feature> Open question <question>; report evidence and the
smallest needed decision, without implementation or delegation.
$implement-slice Resume <feature> from Next action; inspect actual branch/diff.
```

Review, advice and initialization skills have explicit-only invocation metadata;
the human starts them. The human may choose Codex or Claude Code for any phase.
Share the same feature
path and neutral packet, not the writer's conversation. An optional consultation
answers one bounded read-only question; it cannot independently review the slice
it advised. Select model, effort, trust, permissions, and session transport in
the host rather than in feature records. Do not assume native discovery or a
client hook is active merely because files exist in this checkout. The shared
verify skill's location under `.claude/skills/` does not make its engineering
rules Claude-specific.
