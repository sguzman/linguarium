# 09 — Ontology Layers and Cross-Language Reconciliation

Linguarium does not use one giant flat universal ontology, and it does not give every language a completely isolated ontology.

It uses layered ontology.

## Layer 1 — Shared metamodel

This layer defines the kinds of things Linguarium knows how to represent:

- Language / Variety;
- Lexeme;
- Sense;
- Form;
- Morpheme;
- Paradigm;
- GrammaticalFeature;
- Construction;
- Pronunciation;
- Grapheme / Phoneme;
- Concept;
- TranslationRelation;
- Alignment;
- provenance and confidence;
- learner relations.

This layer says what an entity *is structurally*. It does not assert that every language instantiates the same features.

## Layer 2 — Language-local ontology

Each language or variety declares the categories and structures that actually matter to it.

Examples:

Spanish may instantiate:
- grammatical gender;
- person/number;
- tense/aspect/mood distinctions;
- -ar/-er/-ir conjugation classes;
- clitic constructions.

German may instantiate:
- four-case distinctions;
- grammatical gender;
- strong/weak/mixed verb classes;
- adjective declension patterns;
- V2 and verb-final constructions.

Japanese may instantiate:
- script-specific orthographic structures;
- politeness/honorific distinctions;
- agglutinative morphology;
- constructions that do not map cleanly onto Indo-European categories.

Lexemes and senses are inherently language-local entities.

Syntax is primarily language-local too: the shared metamodel can represent constructions and relations, but a language decides which structures exist and how they behave.

## Layer 3 — Cross-language semantic/comparative graph

Languages are reconciled by relations, not by forced merger.

Examples:

~~~text
Spanish Sense ── translation/semantic relation ── English Sense
German Sense  ── concept relation ─────────────── Concept
Latin Lexeme  ── etymological relation ───────── Spanish Lexeme
Sentence Span ── alignment ───────────────────── Target Span
~~~

A cross-language relation can express:
- close translation;
- approximate translation;
- shared concept;
- cognacy;
- inheritance;
- borrowing;
- syntactic analogy;
- morphological analogy;
- pedagogical comparison.

## Reconciliation rule

Do not reconcile languages by deleting distinctions.

Reconciliation means:
1. keep each language's own entities intact;
2. identify justified relationships;
3. record relation type, scope, provenance, and confidence;
4. allow partial or asymmetric mappings.

Two languages can organize similar semantic territory differently. That difference is itself useful data.

## Cheap-language invariant

Adding a language must not require redesigning the universal model unless the language reveals a genuine modeling failure.

Normally activation should require:
- a manifest;
- capability-state entries;
- language-local feature/construction declarations;
- source/analyzer declarations;
- incremental enrichment.

If adding an ordinary new language repeatedly requires application code changes, the architecture is failing.

## Extensibility test

A new language may:
- instantiate existing shared entity types;
- add language-local feature values and constructions;
- expose missing shared abstractions.

Only the third case should trigger ontology redesign, and even then the preferred response is to generalize the metamodel rather than special-case the language in the GUI.
