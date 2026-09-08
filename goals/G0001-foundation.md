# G0001 — Foundation

Status: accepted doctrine / implementation pending

## Objective

Materialize the smallest repository-native Linguarium implementation that proves the corpus -> lexicon -> learner-state -> reader projection loop without prematurely implementing the entire linguistic vision.

## Required capabilities

1. Parse data/languages.toml.
2. Accept a plain UTF-8 text corpus with language metadata through a repository-owned command/entrypoint.
3. Create a stable corpus snapshot and manifest with content hash.
4. Segment enough structure to preserve paragraphs and token occurrences.
5. Persist token occurrences separately from lexical entities.
6. Aggregate unresolved lexical candidates.
7. Allow a minimal lexeme to be integrated manually.
8. Maintain a learner knowledge state for that lexeme.
9. Render or expose a reader projection in which every linked occurrence reflects learner state.
10. Provide deterministic tests for identity, snapshot immutability, candidate aggregation, and projection behavior.

## Architectural constraints

- one repository;
- shared canonical model;
- no one-issue-per-word workflow;
- English pivot semantics from docs/03-english-pivot.md;
- open-world/unknown states;
- provenance retained;
- repo-native human execution;
- ordinary Windows CLI dependencies declared through Scoop when needed.

## Not required

SRS, automated translation, full lemmatization, morphology engine, IPA, syntax parsing, subtitles/video, multi-user support, and an exhaustive GUI are not required.

## Acceptance

The director accepts G0001 only when one tiny corpus can be imported, tokenized, minimally linked to a manually integrated lexeme, assigned learner knowledge, and projected back into a reader-like view with tests proving the shared identity flow.
