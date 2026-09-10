# 07 — Language Packs

Linguarium uses one shared platform and shared canonical data model, but languages and varieties need language-specific computational knowledge and processing behavior.

A language pack is the declarative boundary for that specialization.

## Language pack versus ontology profile

These are different artifacts.

### Ontology profile

Stored under ontology/.

Answers:
- What is this language/variety?
- How is it classified?
- What historical/family/writing-system relations does it have?
- What names, scopes, periods, and sociolinguistic facts belong to it?

### Language pack

Stored under languages/.

Answers:
- How can Linguarium process this language/variety?
- What tokenizer/normalizer applies?
- What grammatical feature inventory is supported?
- What morphology/paradigm machinery exists?
- Which dictionaries, grammars, analyzers, and pronunciation sources can be used?

### Learner profile

Stored under profiles/.

Answers:
- Does the learner care about it?
- Which dialect/standard/historical stage do they prefer, if any?
- What is their proficiency and current revealed salience?

Never collapse these three layers.

## A language pack may declare

- ontology entity reference when one is instantiated;
- language/variety identity and aliases;
- writing systems and scripts;
- tokenization and normalization strategy;
- case-folding rules where appropriate;
- grammatical feature inventory used by that language;
- morphology capabilities;
- paradigm conventions;
- pronunciation/IPA capabilities and variety notes;
- transliteration/romanization systems;
- dictionary/grammar/lexical source manifests;
- available importers/enrichers;
- language-specific constructions or ontology extensions;
- default projection conventions that are not learner preferences.

## A language pack is not

- a separate application;
- a separate repository by default;
- an encyclopedia profile of the language;
- a complete dictionary;
- a separate learner database;
- a claim that all linguistic facts fit one schema identically.

## Shared database, logical language partition

Lexemes, forms, senses, and language-specific grammatical entities belong to a language or variety through stable linguistic identity.

The operational store should therefore be physically shareable while remaining logically partitionable by language/variety.

This preserves:
- easy per-language browsing;
- dialect/standard specialization;
- cross-language concepts;
- cognates and etymological relations;
- multilingual alignments;
- one learner model;
- one provenance model;
- one migration path.

Creating one physical database per language would make cross-language relations unnecessarily expensive and is not the default architecture.

## Inheritance across varieties

A Dialect, StandardVariety, or HistoricalStage should not duplicate an entire parent Language pack.

Prefer inheritance/overlay semantics:

~~~text
Spanish pack
   + Mexican Spanish overlay

Arabic shared structure
   + Classical Arabic stage overlay
   + Modern Standard Arabic standard overlay
~~~

The child/overlay declares only meaningful differences, additions, constraints, source preferences, or analysis behavior.

A learner may still use the parent Language when no child variety is selected.

## Grammar representation

Grammar should not live only as prose documentation.

Where structure is useful to the application, represent it as typed entities and relations:
- GrammaticalFeature;
- feature values;
- Form-to-feature analyses;
- Morpheme;
- Paradigm;
- Construction;
- syntactic/semantic roles where justified;
- usage constraints and register.

Prose grammar notes may coexist as explanatory artifacts with provenance.

## Dictionary representation

Imported dictionary material is evidence feeding canonical entities.

A dictionary entry may propose:
- lemma/lexeme identity;
- senses;
- definitions;
- English glosses;
- usage labels;
- examples;
- pronunciation;
- etymology;
- semantic relations.

Do not make an external dictionary's entry format the internal ontology.

## Semantic representation

Semantics has multiple layers:
- a Sense is language/variety-specific lexical meaning;
- a Definition explains a sense;
- a Gloss offers a compact foothold, usually English;
- a Concept can connect senses across languages when justified;
- semantic relations connect senses/concepts without forcing identity.

## Morphology representation

Morphology should distinguish:
- observed surface Form;
- Lexeme;
- grammatical feature bundle;
- Morpheme segmentation where useful;
- Paradigm membership;
- analysis provenance/confidence.

A form may have multiple analyses when ambiguity is real.

## Pack lifecycle

A language can enter the workspace with a minimal pack containing only identity. Activation creates explicit bootstrap work across independent capability dimensions.

The pack becomes richer from both:
- language-level bootstrap work, which can happen before any corpus exists; and
- corpus-driven demand, which reveals which lexical forms, constructions, ambiguities, and analyses matter in practice.

Conjugation/declension systems belong to the language pack as paradigm/inflection structure. Individual lexemes and observed forms belong to the shared operational data model.

See docs/08-language-bootstrap.md for the full work surface and lifecycle.

This is the language-level form of Linguarium's incrementality doctrine.
