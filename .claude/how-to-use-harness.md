# Claude Code prompts

Start at the project root. `CLAUDE.md` points to `AGENTS.md`; the feature,
contracts, ADRs and project profile are shared with Codex. Choose a fresh
session for normal application implementation and a separate human-started review
session. Initialization may run in the existing discussion session. Neither
client is required to own every phase.

| Phase | Prompt |
|---|---|
| Discuss brief | `Discuss <project target> and architecture options over multiple turns; no skill or repository writes. Capture accepted decisions for handoff.` |
| Initialize | `/initialize-project Use <project brief> and our accepted technology/architecture decision handoff; initialize the blueprint and stop ready for review.` |
| Plan | `/plan-slice Plan <behavior> in docs/features/<behavior>.md; no application edits.` |
| Implement | `/build-slice Execute <task> in <feature-path>; stop ready for independent review.` |
| Advice | `/advise-slice Answer only <consultation packet>; read-only, no implementation.` |
| Independent review | `/review-slice Review <feature-path> using its neutral packet; no edits.` |
| Accepted fixes | `/build-slice Fix accepted findings <IDs> in <feature-path>; rerun affected proof and record dispositions.` |
| Focused re-review | `/review-slice Recheck <IDs> and the new identified diff; no fixes.` |
| Finalize | `Review is closed for <feature-path>. Read the verify skill; run the project's final gate and record actual results.` |
| Escalation | `Read <feature-path> Open questions. Investigate only <question>; report evidence and the smallest needed decision. No implementation.` |
| Resume after context loss | `/build-slice Resume <feature-path> from Next action. Inspect branch/base and actual diff; reuse recorded proof and complete only remaining work.` |

Review, advice and initialization skills are user-invocable only. The human starts
the independent reviewer with the original request and neutral
packet. Do not resume/fork the implementation or advisor conversation as review.
A reviewer never becomes the fixer. A PASS can leave the final gate pending.
Commit, merge, push and publishing follow existing authorization, not these prompts.
