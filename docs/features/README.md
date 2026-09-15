# Features

One document per bounded slice: requirements and proof before application code,
Built and independent Review afterwards. [INDEX.md](INDEX.md) locates current
work and real dependencies. Read only the relevant row/document by default;
completed slices are searchable history. No second backlog.

When multiple isolated checkouts are active, the human assigns a writer and
checkout/branch in a shared index version before building. A private claim does
not reserve the slice; serialize starts if a common record is unavailable.

Use [TEMPLATE.md](TEMPLATE.md). Keep behavior, rationale, proof, decisions,
execution, gaps, Built, and Review concise. A few outcome tasks suffice; omit a
table for one obvious result. Tool/model choices do not belong here. Names should
describe behavior rather than ticket numbers. A tiny mechanical fix may use a
compact response handoff instead of a feature file unless it needs a durable
decision.

Planning alone does not authorize implementation. Ready for review remains
**building**. Done means independent review, substantive findings dispositioned,
and the profile's final gate passed. Keep file and index status aligned. The
[harness](../guide/harness.md) owns transitions and the
[review guide](../guide/review.md) owns the neutral handoff.
