# Independent slice review

The human starts review in a fresh context without the implementation/advice
conversation. If you authored or advised on this slice, decline the independent
role. Review only: no source or task edits, fixes, staging, commits, or delegation.
The implementer records the returned findings and dispositions.

## Neutral handoff

Keep this packet in the feature's Execution section or the response for a tiny fix.
Both clients consume it unchanged.

```text
Task: <original request and feature path; task IDs if useful>
Scope: <branch, exact base/head revisions, included paths and exclusions>
Working tree: <none, or staged/unstaged/untracked paths and snapshot identity>
Evidence: <Built/check results and tested scope; pending gates>
Questions: <Open questions, assumptions, or none>
Review only: follow docs/guide/review.md against requirements, proof,
repository invariants and actual diff. Return PASS / FIX / ESCALATE; no edits.
```

For Git work, freeze and identify the actual bytes. Hash the output of
`git diff --no-ext-diff --no-textconv --binary --full-index <base> -- <paths>`
and `git diff --cached --no-ext-diff --no-textconv --binary --full-index -- <paths>`;
also hash the bytes and paths of included untracked files. Record both digests,
exact base/path selection and “no staged changes” where applicable. These flags
prevent user text conversion/external diff settings or omitted binary bytes from
changing the identity. Do not stage or commit just to create an identity.

For non-Git projects, use the byte-accurate file/scope snapshot command recorded
in `docs/project-profile.md`: include every reviewed file's path and content hash,
including binary files, plus the file count and a digest of the sorted manifest.
Name exclusions. The reviewer checks the identity at entry and before reporting;
scope drift needs a refreshed handoff. A missing profile snapshot command is a
review gap, not permission to guess one.

## Assess the scope and proof

Read the original task, feature behavior/proof, profile, relevant contract and
accepted ADRs. Load profile-linked conventions/references for the changed area.
Establish base/head plus staged, unstaged, and untracked scope where Git applies;
never substitute the last commit for actual work. Inspect relevant callers and
the actual diff. The implementer's packet is navigation, not correctness evidence.

For a resumed review, identify prior reviewed scope and findings, then establish
the new scope before assessing fixes. For each important requirement, trace the
proof's setup through the exercised
branch and its assertions. Name a plausible broken result that would escape a
weak test. Check edge cases, error semantics, architecture, compatibility, and
state/failure paths where relevant. Green tests alone are not a verdict. For a
race, proof must reach the contested interval; for storage, a correct result alone
may not prove bounded work. Inspect recorded-evidence and contract changes against
the base, including manifest/origin/supersede changes. Check that warning or
architecture gates were not relaxed to look green.

For harness/configuration work, check instruction precedence, skill discovery,
consistency between clients, transition control, and whether executable claims
match the files. Distinguish failures actually observed from reasoned concerns;
name the evidence that would settle a concern.

Run targeted checks only when they settle a review question. State actual reruns,
inspected logs, blocked checks, and pending final gate separately. A sandbox that
blocks a needed check creates a named verification gap. An incomplete
review cannot PASS unexamined important scope.

Return **PASS** for no substantive findings in examined scope, **FIX** for bounded
defects or proof gaps, or **ESCALATE** for design uncertainty/deeper
misunderstanding. Each finding names file/line, trigger or escaping broken
behavior, violated requirement/decision, impact, and proof that would settle it.
No quota or confidence score. Focused re-review checks the finding and new diff;
the human starts a full review if the design or scope changed materially.
