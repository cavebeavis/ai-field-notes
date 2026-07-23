---
title: "AI should leave behind capability"
status: note
created: 2026-07-23
updated: 2026-07-23
topics:
  - agents
  - rag
  - inference-cost
  - durable-computation
summary: "Repeated AI reasoning should produce reusable code, indexes, policies, or other durable artifacts instead of being discarded and regenerated."
related:
  - "cavebeavis/orseg-inbox#30"
---

# AI should leave behind capability

## Trigger

Ad hoc AI assistance is worth paying for when the question is genuinely new, ambiguous, or urgent. The waste appears when the system repeatedly solves the same procedural problem from scratch.

A common example is asking an AI system to inspect GitHub issues and report some condition. The model may repeatedly discover pagination, generate a Python script, normalize the responses, apply the same filters, produce the answer, and then discard the script. The next session pays for substantially the same reasoning again.

## Observation

Current AI workflows commonly behave like disposable interpreters:

1. Read the same or similar input.
2. Reconstruct the same understanding.
3. Generate the same procedure or code.
4. Execute it once.
5. Throw away the capability.
6. Repeat the process later using more inference.

This is rational for novel work. It is wasteful for deterministic or recurring work.

## Interpretation

AI systems should recognize when reasoning has produced a reusable procedure and leave behind a durable artifact. That artifact might be:

- a command or script;
- a tested API adapter;
- a query or filter definition;
- a classification policy;
- an index or materialized view;
- extracted metadata and provenance;
- fixtures and tests;
- assumptions and conditions that determine when the artifact is still valid.

Later executions should prefer the deterministic artifact. Fresh inference should re-enter when the inputs fall outside its validated envelope, its assumptions no longer hold, or the user is asking a materially different question.

## RAG implication

RAG is often treated as repeated reconstruction: retrieve raw chunks and ask a model to infer the same stable facts, relationships, and classifications on every query.

A stronger design would compile durable knowledge infrastructure:

1. Ingest sources.
2. Normalize them.
3. Classify and extract entities or relationships.
4. Persist derived metadata, claims, summaries, and provenance.
5. Version the model and policy that produced those artifacts.
6. Incrementally refresh only what changed.
7. Invoke synthesis when the question actually requires interpretation.

The index is then not merely a vector lookup table. It is a versioned intermediate representation of the knowledge that has already been paid for.

## Work classes

### Deterministic work

Pagination, filtering, joins, counts, status checks, diffing, validation, and known transformations should become ordinary code.

### Compiled intelligence

Classifications, extracted entities, embeddings, summaries, semantic anchors, inferred relationships, and retrieval metadata should be persisted, versioned, and incrementally refreshed.

### Irreducible interpretation

Novel questions, incomplete requirements, conflicting evidence, tradeoffs, and judgment remain appropriate uses of fresh inference.

## Why it matters

The failure is larger than token cost. Systems that continually regenerate procedures fail to accumulate operational capability. They appear intelligent during a session while remaining structurally amnesiac across sessions.

A useful principle is:

> Never pay twice for reasoning that could have become durable computation.

An even broader formulation is:

> AI should leave behind capability, not merely consume tokens.

## Counterpoints

Not every generated artifact deserves preservation. Some are trivial, brittle, unsafe, tied to temporary credentials, dependent on unstable schemas, or more expensive to maintain than regenerate.

The system therefore needs an explicit disposal decision rather than a rule that every generated script must become permanent software.

## Questions

- How can a system detect that a newly generated procedure repeats prior work?
- What evidence is required before generated code becomes trusted tooling?
- How should assumptions and freshness conditions be attached to retained artifacts?
- Who owns maintenance of code generated incidentally during another task?
- How should avoided inference and artifact reuse be measured?
- What vendor incentives oppose systems that reduce future token usage?

## Next step

Develop this into a sourced paper about disposable inference, compiled retrieval, and the difference between conversational memory and accumulated computational capability. The Orseg-specific architectural implications are tracked separately in `cavebeavis/orseg-inbox#30`.
