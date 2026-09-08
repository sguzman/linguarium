# 08 — Language Bootstrap Work Surface

Declaring interest in a language is an operational event, not merely a registry edit.

It creates a bounded language-level work surface even before any corpus exists.

## Three demand planes

Linguarium separates three sources of work.

### 1. Language demand

Triggered by declaring or activating a language.

This asks: what must Linguarium know about the language itself so later corpora can be analyzed correctly?

### 2. Corpus demand

Triggered by adding text/audio/subtitle material.

This asks: what lexical, morphological, syntactic, semantic, phonological, and alignment facts are actually demanded by observed material?

### 3. Learner demand

Triggered by learner state and current reading/study behavior.

This asks: which unresolved or weak entities should receive attention first?

The queues may combine these signals into priority, but they must not collapse the three concepts.

## Language bootstrap stages

A language pack can progress independently through the following capability surface.

### L0 — Identity

Required immediately on declaration.

- stable language/variety ID;
- name and aliases;
- role in the language universe;
- relation to parent/macro/historical varieties where relevant;
- principal scripts;
- basic provenance for the declaration.

### L1 — Orthography and normalization

- writing system(s);
- grapheme inventory where pedagogically useful;
- Unicode normalization rules;
- case-folding behavior where relevant;
- punctuation/token-boundary conventions;
- transliteration/romanization systems where useful.

### L2 — Segmentation and tokenization

- word/token segmentation strategy;
- sentence/utterance segmentation strategy;
- clitic/compound handling conventions;
- tokenizer/normalizer adapter declarations;
- test fixtures.

Languages without whitespace word boundaries must be representable without pretending whitespace is universal.

### L3 — Grammatical feature inventory

Declare the grammatical distinctions Linguarium may need to represent for this language.

Examples include:
- person;
- number;
- gender/noun class;
- case;
- tense;
- aspect;
- mood;
- voice;
- definiteness;
- animacy;
- politeness;
- evidentiality;
- comparison;
- agreement classes.

This is a language-specific inventory. Absence of a feature is meaningful; unknown support is distinct from absence.

### L4 — Morphology and paradigm system

Describe how lexemes may realize grammatical features.

This includes, where applicable:
- inflectional classes;
- conjugation classes;
- declension classes;
- paradigm dimensions;
- principal parts;
- regular formation rules;
- irregular/defective behavior;
- suppletion;
- derivational morphology;
- morpheme segmentation conventions.

The language pack defines the *system*. Individual lexemes instantiate or deviate from it.

### L5 — Syntax and constructions

Seed the structural phenomena needed to analyze sentences without forcing a universal English syntax.

Examples:
- basic constituent-order tendencies;
- agreement relations;
- argument-marking strategies;
- subordinate-clause mechanisms;
- negation;
- questions;
- relative clauses;
- copular constructions;
- case government;
- serial verbs;
- classifiers;
- topic/focus constructions;
- language-specific idiomatic constructions.

This is not intended to become an exhaustive grammar book during bootstrap. It establishes typed hooks and high-value constructions.

### L6 — Phonology and pronunciation

- phoneme inventory where useful;
- IPA conventions;
- stress/accent behavior;
- syllabification conventions;
- dialect/variety distinctions;
- grapheme-to-phoneme capabilities;
- pronunciation source adapters.

### L7 — Lexical and semantic sources

Declare trusted/usable evidence sources and adapters for:
- lemmas;
- senses;
- definitions;
- English glosses;
- usage/register;
- examples;
- morphology;
- pronunciation;
- etymology;
- semantic relations.

Source declarations do not import entire dictionaries by default.

### L8 — Analysis capability

Record what automation exists for the language:
- tokenizer;
- lemmatizer;
- morphological analyzer;
- morphological generator;
- POS tagger;
- dependency/syntax parser;
- named-entity analyzer where useful;
- transliterator;
- pronunciation/IPA generator;
- translation provider;
- embedding/vector resources.

Every capability should expose confidence/provenance and may be absent.

## Conjugation and declension model

Conjugation and declension are not just UI tables.

They are projections of typed morphology.

Conceptually:

~~~text
Language
  -> GrammaticalFeature inventory
  -> ParadigmTemplate / InflectionClass
  -> Lexeme
  -> Form
  -> FeatureBundle
~~~

For Spanish:

~~~text
Lexeme: hablar
InflectionClass: -ar verb

Form: hablo
features:
  person = 1
  number = singular
  tense = present
  mood = indicative

Form: hablábamos
features:
  person = 1
  number = plural
  tense = imperfect
  mood = indicative
~~~

For a case-inflecting noun:

~~~text
Lexeme: ...
DeclensionClass: ...

Form A -> case=nominative, number=singular
Form B -> case=accusative, number=singular
Form C -> case=genitive, number=plural
~~~

The GUI conjugation/declension table is then derived from these entities.

## Where forms come from

Linguarium may learn or propose forms from multiple evidence channels:

1. corpus attestation;
2. imported dictionaries;
3. imported/reference grammars;
4. morphological analyzers;
5. morphological generators;
6. model proposals;
7. director/human correction.

A generated regular form is not the same evidence class as an attested form.

The provenance model must retain that distinction.

## Corpus interaction

A corpus does not need the whole language pack complete before ingestion.

If the tokenizer exists but morphology does not, Linguarium can still create TokenOccurrences and lexical candidates.

Later, improving the language pack can re-analyze existing corpus material and enrich already stored entities.

Therefore:

> language capability upgrades should retroactively increase the value of existing corpora without invalidating their source snapshots.

## Activation semantics

When the principal declares a language as active/reference:

1. add/update data/languages.toml;
2. create its language-pack manifest if absent;
3. inspect the bootstrap capability matrix;
4. enqueue missing high-value bootstrap dimensions at neutral initial salience;
5. let operational learner activity later influence processing order through revealed salience;
6. create engineering macro-goals only when new software/tooling is actually required;
7. do not fabricate a giant vocabulary list merely because the language was activated.

If a corpus arrives in an undeclared language, intake may create a provisional language declaration and block only the analysis stages that truly require missing language support.

## Completion semantics

A language pack is never globally “finished.”

Each capability dimension has its own state, for example:
- absent;
- queued;
- partial;
- usable;
- mature;
- blocked.

This prevents “support German” from becoming an impossible monolithic task.
