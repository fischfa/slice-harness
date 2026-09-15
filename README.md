# Slice framework

A technology-neutral starting point for one bounded feature at a time. Claude Code
and Codex can plan, implement, advise, or review using the same feature document,
contracts, ADRs, and verification rules. They may be used in either order or on
separate slices, but a slice has one writer and a human starts its independent
review. Client choice never changes the engineering record.

This repository is intentionally **uninitialized**. It contains no application
stack, test command, public contract, fixture, or recorded golden. Clone or copy it
into a new project and discuss your full project brief with an agent over as many
turns as needed; no skill invocation is required for that exploration. Once the
technology and architecture choices are settled, run `initialize-project` with
the brief and accepted findings. It writes the project profile, ADRs, real
verification commands, contract policy, and technology-specific conventions.
The discussion itself is read-only unless you explicitly request an artifact.
Do not treat placeholders as passed checks.

If you switch sessions, carry a short handoff: the original brief or stable path,
accepted choices and reasons, hard constraints, and material questions still open.
The initializer checks those findings against current evidence and asks only about
gaps that affect setup; it does not repeat the architecture discussion by default.

Start at [the documentation map](docs/README.md). The shared working agreement is
[AGENTS.md](AGENTS.md); [CLAUDE.md](CLAUDE.md) and the
[Codex guide](docs/guide/codex.md) are thin client entry points.

The blueprint ports the workflow and templates, not the originating service's
completed features, decisions, runtime contract, snapshots, hooks, test runner,
or model rankings. Initialization adds only the controls the new project can
actually execute and verify.
