# Feature index

One row per feature document in this directory, excluding `README.md` and
`TEMPLATE.md`. Status is `planned`, `building`, or `done`, and matches the file.
Blocked by names a real dependency and why; an empty cell means independent work.
Order rows by useful execution order, not an invented dependency graph.

| Feature | Blocked by | Assigned writer ID / checkout | Status |
|---|---|---|---|

When isolated checkouts build concurrently, the human records one writer ID and
checkout/branch per slice in a version all participants can see. The ID names a
specific person or working session, not merely “Claude Code,” “Codex,” or a model.
A branch-local claim does not reserve work. With Git, integrate the assignment
into the common base before concurrent writer branches/worktrees start; that
commit follows human authorization. If no shared coordination record is available,
serialize starts. A single writer working sequentially needs no per-slice claim
commit. Integrate concurrent index status edits serially and resolve conflicts
before publishing.
