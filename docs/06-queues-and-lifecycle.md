# 06 — Queues and Lifecycle

Linguarium uses explicit queues so unfinished linguistic work can accumulate safely without forcing immediate completion.

## Queue families

### corpus_intake
Raw source requests waiting to become reproducible corpus snapshots.

### corpus_analysis
Snapshots waiting for segmentation, tokenization, normalization, or statistics.

### lexical_candidate
Aggregated unresolved forms/lemmas discovered from corpora.

### lexical_enrichment
Integrated lexemes/senses waiting for additional semantic, grammatical, phonological, etymological, or usage data.

### alignment
Passages/entities waiting for cross-language correspondence work.

### review
Machine/model/imported analyses that require semantic adjudication.

### correction
Accepted data later found to need repair while preserving entity lineage.

## Lifecycle

Baseline states:

~~~text
queued
  -> ready
  -> in_progress
  -> proposed
  -> accepted
~~~

Side states: blocked, rejected, superseded, deferred.

High-volume implementations may use more specialized states, but they must map to this conceptual lifecycle.

## Queue identity

Every work item needs stable identity independent of an individual processing attempt.

A failed or rejected attempt does not necessarily create a new work item. Corrections should reopen the semantic objective when appropriate, mirroring repository macro-goal continuation doctrine.

## Queue records should capture

- stable ID;
- queue family;
- language/variety where relevant;
- target entity/source;
- priority;
- state;
- prerequisites;
- origin/provenance;
- created/updated timestamps;
- attempt lineage;
- blocker/rejection/supersession reason;
- optional requested enrichment dimensions.

## Corpus fan-out

~~~text
corpus_intake
   |
   v
snapshot
   |
   +--> structural analysis
   +--> tokenization
   +--> frequency statistics
   +--> lexical candidate aggregation
   +--> learner coverage report
   +--> optional translation/alignment candidates
~~~

Candidate aggregation is critical. Ten thousand occurrences of the same form must not become ten thousand independent lexical jobs.

## Lexeme integration fan-out

~~~text
lexeme
  +--> senses/glosses
  +--> morphology
  +--> pronunciation/IPA
  +--> semantic relations
  +--> derivation/cognates
  +--> examples
  +--> alignments
~~~

This lets value arrive incrementally.

## Priority doctrine

Default priority should favor:
1. what blocks the learner's current reading;
2. high-frequency unknown material;
3. reusable lexical entities seen across corpora;
4. high-confidence cheap enrichments;
5. ambiguities that cause incorrect projections;
6. low-frequency exhaustive enrichment last.

The system exists to increase comprehension, not to finish dictionaries for their own sake.

## Bootstrap representation

Until a database-backed queue exists, repository fixtures under data/queues/ document the contract and can hold small manually queued items.

Once the operational queue is implemented, GitHub issues remain macro engineering work; they must not become the lexical queue.
