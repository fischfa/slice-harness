# Shared slice agreement

- User instructions take precedence. Planning stops before application edits;
  implementation builds one bounded task; independent review reports findings.
- One writer per active slice. Claude Code and Codex may perform different phases
  of that slice, or work concurrently on disjoint slices in separate checkouts.
  Parallel work inside one slice is bounded read-only investigation or consultation;
  never create parallel writers or automatic review/fix loops. The human starts
  independent review and escalation.
- Before concurrent building starts, the human records each slice's writer and
  checkout/branch in an index version visible to every participating checkout.
  Use a specific person or working-session ID, never just a client/model name.
  A branch-local claim is not coordination; serialize starts when a common claim
  cannot be established.
- Read `docs/features/README.md`, then the relevant index row and feature only.
  Keep requirements, proof, handoff, Built, and Review in that document. Old slices
  are searchable history, not default context.
- Inspect branch, base, and dirty/untracked state before edits. Preserve user
  changes. Use a named task branch for new work unless the user chooses otherwise;
  do not switch a dirty checkout to unrelated work. Do not automatically commit,
  merge, push, or publish.
- Describe important behavior and executable proof before application code. Check
  relevant callers before changing shared behavior. Use the cheapest proof that
  catches a plausible broken implementation. Never weaken tests, contracts,
  recorded evidence, architecture checks, or warnings merely to pass a gate.
- `docs/project-profile.md` names this project's stack, canonical contracts,
  evidence sources, focused checks, and final gate. `uninitialized` means commands
  and conventions are unset. `bootstrap-ready` permits the first code slice after
  the documentation/config gate passes; application gates remain defined but
  unexercised. The first code slice must prove the gate rejects a failing check
  and zero-selection run, then pass it with real selected checks before done.
- When the profile is `uninitialized` and the user is discussing the project
  brief, stay read-only: do not invoke slice roles or write repository files merely
  from that discussion. Explicit user requests for an artifact still apply.
  Normal feature planning/building starts after `bootstrap-ready`; the user
  explicitly starts `initialize-project` when architecture choices are settled.
- Durable public-boundary or architecture decisions follow `docs/adr/README.md`.
  Contract changes follow `contracts/README.md`. Recorded evidence, if configured,
  is preserved and intentional supersedes are explicit; a matching editable
  checksum alone does not prove integrity. Inspect its diff from the task base.
- Ready for review is still **building**. Done requires human-started independent
  review, disposition of substantive findings, and the scope's final gate. Record
  actual commands/results and gaps; never call author inspection independent review.

Read [the harness](docs/guide/harness.md) for transitions and stop conditions.
Plan with `.agents/skills/plan-slice/SKILL.md`, implement with
`.claude/skills/build-slice/SKILL.md`, review with `docs/guide/review.md`, and
verify with `.claude/skills/verify/SKILL.md`. Project-specific conventions live in
`docs/project-profile.md` and linked references, not in client-specific prompts.
