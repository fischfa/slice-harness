# Verification policy

`docs/project-profile.md` must define real commands for this project. This page
defines how to choose and report checks; it is not a substitute for an executable
gate.

During implementation, start with the cheapest test that catches a plausible
failure. Expand to affected callers and a real boundary when assembly, state,
transactions, compatibility, or dependency direction makes a small test
insufficient. Confirm selected tests actually ran; zero selected tests or skipped
checks are pending, not green. Save full logs where useful and record concise
command, result, revision/tree, warnings, and meaningful gaps in Built.

After independent review and accepted fixes, run the profile's final command for
the changed scope once on the reviewed/fixed tree. A no-code initialize-project
slice closes on its real documentation/config bootstrap gate; application commands
stay “defined, not yet exercised.” Before its review handoff, the first code slice
must run the application gate in an isolated disposable validation copy with a
deliberately failing required check and with no required tests/checks selected.
Both runs must be
rejected; a pipe or CI `continue-on-error` that masks failure is a defect. Restore
the intended tree before review. After review/fixes, pass the gate with real
selected checks on the reviewed/fixed tree before done and set profile status to
`initialized`. Record the exact commands, exits and selection evidence. Repeat
only if a later change
could invalidate it. A gate already run on the same relevant tree may be reused
with its identity and result. Documentation-only changes validate their artifacts,
links, and executable claims. Changes to hooks or verification tooling prove both
allow and reject/failure behavior and run the gate they affect.

Green means exit success, required checks actually executed, and no unexplained
warnings/errors. Do not silence diagnostics, weaken assertions, regenerate frozen
evidence, or relax architecture rules to clear a failure. Follow the contract and
ADR process for intentional changes. Environment failures have an environment
fix; blocked checks remain explicitly pending.

The initializer records a scope-to-command table with prerequisites and expected
log behavior. No universal build command, proof level name, coverage threshold,
or test framework is assumed here.
