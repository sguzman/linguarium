# 07 — Language Packs

Linguarium uses one shared platform and shared canonical data model, but languages need language-specific knowledge and processing behavior.

A language pack is the declarative boundary for that specialization.

## A language pack may declare

- language/variety identity and aliases;
- writing systems and scripts;
- tokenization and normalization strategy;
- case-folding rules where appropriate;
- grammatical feature inventory used by that language;
- morphology capabilities;
- paradigm conventions;
- pronunciation/IPA capabilities and dialect notes;
- transliteration/romanization systems;
- dictionary/grammar/lexical source manifests;
- available importers/enrichers;
- language-specific constructions or ontology extensions;
- default learner/projection conventions.

## A language pack is not

- a separate application;
- a separate repository by default;
- a complete dictionary;
- a separate learner database;
- a claim that all linguistic facts fit one schema identically.

## Shared database, logical language partition

Lexemes, forms, senses, and language-specific grammatical entities belong to a language or variety through stable language identity.

The operational store should therefore be physically shareable while remaining logically partitionable by language.

This preserves:
- easy per-language browsing;
- cross-language concepts;
- cognates and etymological relations;
- multilingual alignments;
- one learner model;
- one provenance model;
- one migration path.

Creating one physical database per language would make cross-language relations unnecessarily expensive and is not the default architecture.

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
- a Sense is language-specific lexical meaning;
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

A language can enter the workspace with a minimal pack containing only identity and basic tokenization. The pack becomes richer as corpora demand more structure.

This is the language-level form of Linguarium's incrementality doctrine.
