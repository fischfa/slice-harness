# Architecture Decision Records

One numbered file per durable decision. Preserve history; mark superseded records
and link replacements. Write for a developer outside the original conversation:
decision, evidence and constraints, real alternatives, consequences, and how to
verify it. Use [0000-template.md](0000-template.md).

During initialization, agree which boundaries demand an ADR and record the
project-specific criteria in `docs/project-profile.md`. Useful defaults are
new or changed public contract behavior, compatibility changes, dependencies,
durable architecture/security/data decisions, and deliberate changes to recorded
evidence. Restoring already-specified behavior usually needs no new record.
Ordinary local choices, task decomposition, and client/model routing do not.

Do not create a decision merely to justify making a gate green. A wrong executable
architecture rule changes separately with its reason. Intentional evidence
supersedes follow `contracts/README.md`. Link governing ADRs from the feature and
contract where they affect interpretation.

## Index

| # | Decision | Status |
|---|---|---|
