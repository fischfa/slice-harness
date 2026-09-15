---
name: build-slice
description: Build one bounded feature or accepted review fix with proof before application code and a neutral handoff for human-started independent review.
---

Read `AGENTS.md`, `docs/project-profile.md`, the feature/task, and actual branch,
base and dirty state. For planning-only work, read the shared planning skill and
stop before application edits. The harness owns transitions and escalation.
If the profile is `uninitialized`, do not begin a normal application slice or
write setup files from exploratory discussion; the owner explicitly starts
initialization after material choices are settled.

Confirm bounded scope and relevant decisions. Inspect code and callers before
changing shared behavior. Load the profile's project conventions/references when
this task touches their area. If other checkouts build concurrently, confirm the
human's shared index assignment identifies this writer/checkout before editing.
Write proof before application code: reproduce a bug;
describe new public surface in its canonical contract and write an authored case
when useful; otherwise use the cheapest check that would fail for a plausible
broken solution. Validate that the setup reaches the required state and the
assertion distinguishes the property. Documentation/configuration changes need
artifact and executable-claim validation, not dummy application tests.

Implement the smallest coherent result. Use focused checks from the verify skill;
do not repeatedly run the full gate during building. Preserve evidence and
architecture rules. On the first code slice after bootstrap, prove the application
gate rejects a deliberately failing required check and a run selecting no required
tests/checks. Use an isolated disposable validation copy and restore the intended
tree before review. Record exact commands, selected counts and nonzero exits in
Built and the profile. Record changed behavior, requirement-to-proof links, actual
commands/results, assumptions and gaps in Built. Set Next action to human-started
review, include the neutral packet and dirty snapshot from `docs/guide/review.md`,
and leave status **building**. Do not start a reviewer automatically.

After the human returns accepted findings, repair bounded issues in the
implementation context, record disposition and rerun affected proof. The human
starts focused re-review when substantive correctness/proof needs reassessment.
A design/scope conflict uses the harness escalation handoff. After review closes,
run the project profile's final gate on the reviewed/fixed tree; mark done only
when both review and verification close. On the first code slice after bootstrap,
the final application gate must pass with real selected checks before setting the
profile to `initialized`. Delivery follows existing authorization.
