# 05 — Artifacts and Provenance

Linguarium separates durable artifacts from projections and caches.

## Canonical durable artifacts

### Corpus manifests
Identity, source metadata, language, licensing/public-domain status where known, snapshot hash, ingestion state, and structural metadata.

### Corpus snapshots
Exact imported source payloads used by annotations.

### Linguistic entities
Lexemes, senses, forms, morphemes, grammatical features, constructions, pronunciations, graphemes, phonemes, concepts, and relations.

### Learner-state records
KnowledgeState and LearningEvidence.

### Alignment records
Cross-lingual or intra-lingual span/entity correspondences.

### Queue records
Unfinished work with identity, lifecycle state, prerequisites, provenance, attempts, and disposition.

## Derived artifacts

These should be reproducible from canonical data where practical:
- token-frequency tables;
- reader color assignments;
- generated flashcards;
- conjugation tables;
- search indexes;
- vector embeddings;
- cached machine translations;
- rendered interlinear views.

## Provenance envelope

Durable semantic assertions should support a provenance envelope with fields conceptually equivalent to:

~~~text
source_kind
source_ref
created_by
created_at
method
confidence
review_state
notes
~~~

Potential source kinds include corpus_attestation, imported_dictionary, imported_grammar, mechanical_analysis, translation_service, model_proposal, director_review, and human_principal_input.

## Review states

Suggested baseline:
- proposed;
- mechanically_verified;
- reviewed;
- accepted;
- disputed;
- rejected;
- superseded.

Mechanical verification and semantic acceptance are different dimensions in principle; the storage design may later normalize them further.

## Source hierarchy

No external source is infallible.

Prefer retaining disagreement over flattening competing analyses into false certainty. A lexeme can carry multiple proposed etymologies, segmentations, or glosses with provenance.

## Repository storage

During bootstrap, small machine-readable registries and queue fixtures may live directly in Git.

Large operational data should eventually live in the application's database while preserving exportable manifests and migrations in the repository.

Public-domain corpus snapshots may be committed when size/licensing make that reasonable. Do not make Git itself the permanent database architecture merely because it is the bootstrap control plane.
