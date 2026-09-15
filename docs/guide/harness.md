# The development harness

One bounded slice has one writer. Repository files carry state between sessions.
Claude Code and Codex may be chosen independently for planning, implementation,
advice, and review. Both read the same feature, contract, ADR, and project profile.
Client prompts select a role; they do not create a second lifecycle.

| Home | Responsibility |
|---|---|
| `AGENTS.md` | Shared invariants and routing |
| `docs/project-profile.md` | Initialized technology and executable checks |
| Planning skill | Behavior, proof, bounded tasks; no application edits |
| Implementation skill | Proof first, focused change, review handoff |
| Review guide | Independent assessment, findings, proof quality |
| Verify skill | Focused ladder and final gate |
| Feature document | Slice requirements, decisions, state, evidence |
| Contracts and ADRs | Canonical public behavior and durable decisions |

## Transitions

Before initialization, the owner may explore a project brief over multiple turns
without a skill or repository writes. Keep accepted decisions in a short handoff.
`initialize-project` may run in that discussion session when the owner invokes it,
or in a fresh session with the handoff. The fresh-session instruction below is for
normal application implementation; independent review always starts fresh.

1. **Plan when needed.** Resolve ordinary uncertainty from project evidence.
   Specify observable behavior and proof, then stop. Planning alone does not
   authorize implementation.
2. **Implement in a fresh bounded session.** Inspect the relevant code and
   callers, write discriminating proof before application code, then build the
   smallest coherent result. Record branch/base, changed scope, commands/results,
   gaps, and the neutral review packet. Stop **building, ready for review**.
3. **Human starts independent review.** Use a fresh context with the original task,
   feature path, and exact diff/snapshot. The reviewer can be Claude Code or Codex,
   in any order relative to implementation. Freeze edits to the reviewed scope.
   A session that authored or advised on the slice cannot independently review it.
   Review is read-only and returns PASS, FIX, or ESCALATE.
4. **Human returns accepted findings.** The implementation owner repairs bounded
   findings and records disposition. The human starts focused re-review when
   correctness or proof needs reassessment; material design changes need a fresh
   full review. Cosmetic edits alone do not require it.
5. **Finalize.** After review closes, run the project profile's scope-appropriate
   final gate on the reviewed/fixed tree. A defect returns to implementation and
   appropriate review. Mark done only after review and gate close. Delivery follows
   its own existing authorization.

An instruction may explicitly authorize several named transitions. No instruction
creates an indefinite review/fix loop. One client may plan and the other implement;
they may work on different slices in parallel in isolated checkouts with disjoint
scope. For concurrent building, the human assigns a specific writer ID and
checkout/branch in a shared index version visible to all participants. A client
or model name alone is not a writer ID. A private branch claim is insufficient;
with Git, integrate the claim into the common base before concurrent writer
worktrees start. Serialize starts if coordination is unavailable. Do not switch a dirty
shared checkout under another writer.
Within one slice, parallel work is limited to bounded read-only questions with a
single writer. A child or advisor is optional and never an independent reviewer if
it has advised the implementation. The human controls review and escalation starts.

## Consultation and escalation

After inspecting local evidence, the writer may ask for bounded read-only advice
about one answerable question inside accepted requirements. Use the
[consultation packet](consultation.md) with either client. Pause dependent edits
while awaiting it. Advice neither widens scope nor replaces proof. Record accepted
engineering conclusions in the feature's Decisions or an ADR; keep model/session
choices out of engineering records.

Stop dependent implementation and expose a compact question when behavior
conflicts with evidence, accepted decisions conflict, important proof cannot be
made credible, correctness rests on unsupported state/compatibility/security
assumptions, or the required scope materially exceeds the agreed boundary. Stop
also after repeated unresolved attempts, pressure to weaken checks/evidence, or
review findings that share a deeper design misunderstanding. Give known facts,
relevant files, actual checks, attempts, and the smallest decision or missing
evidence. The human chooses investigation, a decision, or a reduced slice.

Instructions and hooks cannot guarantee compliance. Missing review or verification
remains visible pending work, never silently becomes done.
