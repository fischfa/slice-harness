# Contracts and evidence

This blueprint contains no public contract. Initialization identifies the actual
boundaries—API, schema, event, file format, command protocol, UI behavior, or
another externally relied-on interface—and names **one canonical description per
boundary** in `docs/project-profile.md`. Choose a format clients and tests can
check. Do not invent a contract for a private implementation detail.

Describe new public surface in its canonical contract before application code,
with the governing ADR or feature cited as the project's policy requires. Add
authored behavioral cases before code where contract examples or replay are the
cheapest discriminating proof. A contract is an expectation, not a test result;
verification must check implementation and consumers against it when applicable.

If the project has evidence recorded from an external system, legacy behavior,
or source dataset, identify its provenance and freeze policy during initialization.
Recorded evidence is an observation; authored evidence states intended behavior.
Mark their origins distinctly. Never rewrite a recording to match implementation.
An intentional behavior change requires the governing decision first, an explicit
supersede link to the old bytes/provenance, and a visible manifest diff if the
project uses a checksum manifest. Preserve the retired claim in version history.
The reviewer checks origin, supersede, and manifest changes against the task base.

Do not create an empty manifest, hook, corpus runner, or golden tree simply to
imitate another project. When controls are needed, initialize them with actual
files and exercise both allowed and refused/failure paths. A hook covers only the
client actions it intercepts; shell writes and other clients may bypass it. A
writable checksum manifest alone is not a security boundary. Verification and
review must inspect the manifest **and its diff from the base**.
