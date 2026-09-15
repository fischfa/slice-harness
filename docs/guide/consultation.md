# Bounded consultation

The implementer inspects relevant code, tests, contracts and ADRs first. When one
material question remains inside accepted requirements, prepare a small packet:

```text
Question ID / scope: <feature, branch/base/head and relevant dirty state>
Goal: <one sentence>
Blocked question: <one answerable question>
Established facts: <source/test/contract/ADR locations and actual results>
Options: <what remains plausible and why>
Must remain true: <scope and invariant>
Requested answer: recommendation, fact versus inference, and proof implication;
say ESCALATE if this needs a new decision/design or missing evidence.
```

Pause only dependent edits. The advisor is read-only and answers the one question,
ordinarily in a few paragraphs. Return the ID, **ADVICE** or **ESCALATE**, evidence
locations, inference clearly marked, and proof needed before relying on it. Do
not implement, mutate source, review the slice, delegate, or choose successive
implementation steps. An answer is neither a test result nor scope approval.

The writer checks current evidence and supplies proof before using advice. A
session that advised this slice cannot independently review it. Native messaging
may be used only when the host actually supports delivery and reply observation;
otherwise the human relays the packet. A queued message, timeout or silence is
not an answer. Repeated need for direction or a new durable decision uses the
harness escalation path, controlled by the human.
