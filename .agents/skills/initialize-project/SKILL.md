---
name: initialize-project
description: Turn an accepted project brief, technology and architecture decisions into project documentation, contracts, conventions and executable checks.
---

# Initialize a project

Use after the owner has explored the target and settled the material stack and
architecture choices, whether in this conversation or a prior one. Accept the
original brief (or stable repository path) and a concise decision handoff:
accepted choices, reasons, hard constraints, and remaining questions. Read `AGENTS.md`,
`docs/project-profile.md`, `docs/guide/harness.md`, contract and ADR guidance,
and inspect any existing repository before asking about facts already visible.
This is the first bounded slice; keep its requirements, proof, Built and Review in
`docs/features/initialize-project.md` and index it. The human starts independent
review after implementation, as for any other slice.

Preserve the accepted product target and source brief in the feature document or
a stable project-definition file when its size warrants one. Translate accepted
technology and architecture choices into the profile and governing ADRs; do not
silently replace them with the agent's preferred stack. Verify version/support and
other changeable claims against current primary evidence. If findings conflict
with the brief, repository or current facts, expose the smallest decision to the
owner before dependent setup.

An open question that affects technology, architecture, contracts, setup or proof
also stops the work that depends on its answer. Ask the owner and leave dependent
setup pending until the choice is made; continue only independent work. Do not
write an ADR or configure a gate as though an unanswered choice were accepted.

Resolve only remaining setup details: runtime/build tools and supported versions,
public boundaries and canonical contracts, authoritative evidence, local/CI
environment, focused proof levels, final commands by changed scope, warning/log
policy, version control and byte-accurate review snapshots, configuration and
secrets, project conventions and when to load them, project-specific ADR criteria,
and delivery/review authority. The owner decides or confirms runtime versions,
build tools and other technology choices; the agent may recommend and verify them,
but does not silently fill gaps. Ask only unresolved questions that change setup
or proof; do not restart a generic technology interview. Do not guess a
technology, build tool, test tool, contract format or gate. A named command is not
a verified gate.

Plan observable initialization outcomes first. Then, within the user's
authorization, write `docs/project-profile.md`, actual canonical contract files
or pointers, project-specific conventions/references, and runnable focused/final
checks. Set the profile's explicit status when initialization closes.
Keep shared role/lifecycle skills technology-neutral; link to the profile or add
small project references rather than copying commands through every skill. Add
source fixtures, frozen manifests or hooks only when real evidence and an
executable need exist. Test runnable commands for success **and**
failure/zero-selection behavior where applicable; record prerequisites, exact
invocations, observed results and warnings.
Do not scaffold application layers just to make a framework check appear green.

Stop building with a neutral review packet. The human starts a fresh independent
review of instruction precedence, both client routes, contracts, gate execution,
and actual changed files. For a no-code project, run a real documentation/config
bootstrap gate on the reviewed/fixed tree and mark the feature done with profile
status `bootstrap-ready`; record application gates as defined, not yet exercised.
The first code slice must first prove the application gate rejects a failing check
and a zero-selection run, then pass it with real selected checks before done.
Record those commands/results in the profile before advancing it to `initialized`.
If any material technology, architecture, boundary, environment or proof choice
remains open, keep the slice planned/building and state the smallest question;
never label a blocked check green.
