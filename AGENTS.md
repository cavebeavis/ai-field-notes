# AGENTS.md

Repository-wide guidance for AI tools and contributors working in `ai-field-notes`.

## Purpose

This repository preserves developing thought about artificial intelligence. It may contain rough notes, formal papers, code, benchmarks, diagrams, source trails, and publication copies. Do not force every contribution into the shape of a software project or an academic paper.

## Preserve epistemic status

Keep these categories distinct:

- **Observation** — something directly seen, measured, or documented.
- **Inference** — a conclusion drawn from observations.
- **Hypothesis** — an explanation or prediction that still needs testing.
- **Argument** — a reasoned position that may combine evidence and judgment.
- **Finding** — a conclusion supported by a described method and evidence.

Do not rewrite uncertainty into confidence. Do not make a document sound authoritative merely because polished prose is easier to produce.

## Preserve voice

Raw notes may be blunt, profane, skeptical, or incomplete. Do not sanitize them unless explicitly asked to prepare publication copy. Editing should improve clarity without replacing the author's actual position with generic professional language.

## File placement

- Put early thinking, observations, and questions in `notes/`.
- Put coherent, evidence-backed long-form work in `papers/`.
- Put executable tests, code, data, and measurements in `experiments/`.
- Put bibliographies, annotated references, and source trails in `sources/`.
- Put publication records or final snapshots in `published/`.
- Start from a file in `templates/` when practical.

Prefer updating an existing document when the new material advances the same thesis. Create a new document when the claim, scope, or intended publication is materially different.

Use lowercase kebab-case filenames. Dates use `YYYY-MM-DD`. Do not renumber existing files merely to make an index look cleaner.

## Document metadata

Notes and papers should normally include front matter containing at least:

- `title`
- `status`
- `created`
- `updated`
- `topics`
- `summary`

Add `sources`, `related`, `canonical_url`, or `supersedes` when applicable.

## Evidence and citations

Never invent a citation, quotation, measurement, benchmark, source date, or publication status.

For factual claims that may change, record the source and access date. Prefer primary sources for technical claims. Mark recollection and anecdote as such. Keep quotations short and preserve the original context.

Source notes should summarize and connect material rather than copy entire copyrighted works into the repository.

## Experiments and code

An experiment must explain:

- the question being tested;
- the method and environment;
- inputs and assumptions;
- how to reproduce it;
- observed results;
- limitations and likely failure modes.

Keep generated code only when it contributes to a durable, reproducible capability or supports a documented experiment. Do not accumulate unexplained one-off scripts.

## Promotion and publication

Do not silently move a note into `papers/` or mark it `published`. Promotion changes the implied quality bar and should be intentional.

Before publication, check:

- factual and citation accuracy;
- whether evidence supports the strength of the conclusion;
- whether counterarguments are represented fairly;
- whether proprietary or private information has leaked into the draft;
- whether a public example has been generalized enough to avoid exposing unrelated people or organizations.

## Repository maintenance

Update `INDEX.md` whenever a substantive note, paper, experiment, or publication record is added, renamed, promoted, superseded, or removed.

Do not create process for its own sake. The structure exists to prevent lost work, false certainty, duplicate writing, and confusion about what is ready for publication.
