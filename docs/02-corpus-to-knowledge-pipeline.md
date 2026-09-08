# 02 — Corpus-to-Knowledge Pipeline

The corpus pipeline converts raw text into progressively more structured value without demanding full analysis up front.

## Stage C0 — Intake

Input:
- source metadata;
- declared language/variety;
- raw text or import reference;
- optional title/author/work metadata.

Output: queue record with stable corpus intake ID.

No linguistic analysis is required.

## Stage C1 — Snapshot

Capture the exact text used for downstream annotation.

Output:
- immutable source payload;
- cryptographic hash;
- provenance record;
- normalization notes;
- document manifest.

Upstream changes must create a new snapshot rather than silently mutate annotated text.

## Stage C2 — Structural segmentation

Identify useful stable structure: chapters/sections, paragraphs, sentences/utterances, and subtitle cues where relevant.

Each span receives stable local identity.

## Stage C3 — Surface tokenization

Produce token occurrences with exact offsets and surface text.

This stage may be language-specific.

Outputs are occurrences, not dictionary entries.

## Stage C4 — Candidate resolution

For each relevant token occurrence:
- normalize as appropriate;
- propose language;
- propose form;
- propose lemma/lexeme;
- attach confidence/provenance;
- link to an existing lexeme when justified;
- otherwise emit a lexical candidate.

Repeated candidate forms are aggregated. The queue should prioritize reusable value rather than processing identical occurrences independently.

Useful priority signals include frequency in the current corpus, frequency across all active corpora, learner unknown/weak state, pedagogical value, ambiguity, and requested reading position.

## Stage C5 — Minimal lexical integration

A lexical candidate becomes minimally integrated when it has enough structure to be useful, typically:
- stable lexeme identity;
- language;
- lemma/display form;
- part-of-speech or explicit unknown;
- at least one sense or provisional explanatory gloss;
- provenance/confidence;
- linked observed forms/occurrences.

Minimal integration must not wait for exhaustive dictionary work.

## Stage C6 — Enrichment

Independent enrichment jobs may add additional senses, inflectional features/paradigms, derivation, morpheme segmentation, pronunciation/IPA, register, usage constraints, semantic relations, synonyms/antonyms, cognates/etymology, constructions, example occurrences, and frequency statistics.

These jobs should be idempotent and reviewable.

## Stage C7 — Interlingual foothold

For non-English senses, create an English semantic foothold where useful:
- concise English gloss;
- explanatory definition;
- translation equivalents with relation type;
- notes for partial/untranslatable mappings.

This permits comparison across languages without requiring direct translation between every pair.

## Stage C8 — Projection

Shared entities become visible through reader coloring, click-through lexical panels, morphology views, SRS templates, aligned translations, IPA/pronunciation views, script/orthography views, and cross-language comparisons.

## Stage C9 — Acquisition feedback

Reading and study generate LearningEvidence.

Evidence updates learner knowledge; changed knowledge updates projections without rewriting corpus or lexicon data.

## Work multiplication principle

One integration should create value everywhere.

Integrating one lexeme can immediately color all linked corpus occurrences, populate dictionary lookup, feed SRS, expose morphological relations, participate in cross-language comparison, and improve frequency/acquisition analytics.

That multiplication is the economic engine of Linguarium.
