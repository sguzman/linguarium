# 09 — Ontology Layers and Cross-Language Reconciliation

Linguarium does not use one giant flat universal ontology, and it does not give every language a completely isolated ontology.

It uses layered ontology.

## Layer 0 — Language-world ontology

This layer models languages themselves as objects in a historical and sociolinguistic world.

It includes categories such as:
- LanguageFamily;
- WritingSystem;
- ReconstructedLanguage;
- Language;
- LanguageVariety;
- Dialect;
- StandardVariety;
- HistoricalStage.

This layer answers questions such as:
- What is Spanish?
- What varieties belong under it?
- What historical stages does Hebrew have?
- Which writing systems does a language use?
- Which family relations are asserted?
- Which ancestral systems are reconstructed rather than directly attested?

See docs/15-language-world-ontology.md and docs/16-language-dialect-policy.md.

## Layer 1 — Shared linguistic metamodel

This layer defines the kinds of linguistic things Linguarium knows how to represent:

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

A Dialect, StandardVariety, or HistoricalStage may inherit much of its parent Language's local ontology and add, override, or constrain only what differs.

## Layer 3 — Cross-language semantic/comparative graph

Languages are reconciled by relations, not by forced merger.

Examples:

~~~text
Spanish Sense ── translation/semantic relation ── English Sense
German Sense  ── concept relation ─────────────── Concept
Latin Lexeme  ── etymological relation ───────── Spanish Lexeme
Sentence Span ── alignment ───────────────────── Target Span
Mexican Spanish ── dialect_of ────────────────── Spanish
Biblical Hebrew ── historical_stage_of ───────── Hebrew
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
- pedagogical comparison;
- family membership;
- dialect/standard/historical-stage relations;
- writing-system usage.

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
- a registry entry;
- an ontology profile when demanded;
- a language pack;
- capability-state entries;
- language-local feature/construction declarations;
- source/analyzer declarations;
- incremental enrichment.

A designated dialect is optional. Missing variety choice is valid state.

If adding an ordinary new language repeatedly requires application code changes, the architecture is failing.

## Extensibility test

A new language or variety may:
- instantiate existing shared entity types;
- add language-local feature values and constructions;
- expose missing shared abstractions.

Only the third case should trigger ontology redesign, and even then the preferred response is to generalize the metamodel rather than special-case the language in the GUI.
