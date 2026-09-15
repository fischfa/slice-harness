---
name: verify
description: Select focused checks while building and run the initialized scope-appropriate final gate after independent review and accepted fixes.
---

Read `docs/project-profile.md` for **actual commands** and
`docs/guide/verification.md` for check selection, log audit and blocked-check
handling. During building, choose the cheapest discriminating proof, then affected
callers and real boundaries where needed. After review/fixes, run the profile's
scope gate on the reviewed/fixed tree once. Confirm checks actually executed and
warnings/errors are explained; record command, result and tree identity.

If the profile is `uninitialized` or a command cannot run, state it as pending.
For `bootstrap-ready`, the first code slice must exercise the application gate
against a failing required check and a zero-selection run, confirm both are
rejected, then pass it with real selected checks before completion. Do not
substitute a generic command
or count a skipped check as green.
