# Project profile

**Status:** uninitialized

Allowed values: `uninitialized`, `bootstrap-ready`, `initialized`.

`bootstrap-ready` means initialization closed on a real documentation/config
gate while no application code existed. Application gates are defined, not yet
exercised. The first code slice must prove the application gate rejects a failing
check and a zero-selection run, then pass it with real selected checks before done
and set this profile to `initialized`.

Run `.agents/skills/initialize-project/SKILL.md` with the project owner before
application implementation. Replace this page with observed project facts and
explicit answers; do not infer a stack, gate, or source of truth from this blueprint.

| Topic | Decision to record |
|---|---|
| Product and repository | Goal, existing/new code, main components and owners |
| Source brief | Stable path or preserved original target definition and accepted decision handoff |
| Technologies | Languages, frameworks, runtimes, package/build tools, supported versions |
| Boundaries | Public APIs, schemas, protocols, files, events, UI behavior, compatibility |
| Canonical contracts | One named source of truth per boundary; format and location |
| Evidence | Existing recordings/snapshots, provenance, fixture policy, or none |
| Proof levels | Fast focused check, real-boundary check, end-to-end check if needed |
| Final gates | Exact commands by changed scope; included checks and log policy |
| Bootstrap gate | Exact documentation/config command, meaningful artifact checks and observed result while no application code exists |
| Application gate state | Defined/not yet exercised at bootstrap; first-code-slice failure and zero-selection exercises, then verified pass with real selected checks |
| Configuration | Local/CI environment, secrets policy, startup validation |
| Architecture | Dependency boundaries and executable rules, if useful |
| Conventions and references | Project-specific style, domain and design guides; when build/review must load each |
| ADR criteria | Which durable changes require a record or amendment in this project |
| Review snapshot | Git command or non-Git byte-hash command, included scope and exclusions |
| Delivery | Authorized commit/review/release path and protected environments |

For each command, record where it runs, what it selects, prerequisites, expected
success output, known warnings, and how to detect a zero-test or skipped-check pass.
Do not claim an application gate is verified until it has failed on a deliberately
failing required check, rejected a run selecting no required tests/checks, and
passed with real selected checks on the actual project. Record the exact commands,
observed exits and selected-check counts; “defined” is not “verified.”
