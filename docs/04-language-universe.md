# 04 — Language Universe

Linguarium distinguishes the languages known to the workspace from the learner's current relationship to those languages.

## Workspace registry

Machine-readable registration lives in data/languages.toml.

Registration answers:
- does Linguarium know this language/variety exists in this workspace?
- where is its language pack?
- what is its bootstrap state?

It does not store learner proficiency or current learning priority.

## Learner/profile universe

Learner-specific portfolio membership and stable preferences live under profiles/, initially profiles/default/profile.toml. Volatile activity-derived salience, revealed tiers, and evidence-derived proficiency belong in the operational database. English's workspace-wide interface/meta/pivot defaults live separately in data/workspace.toml.

## Activation

When the principal says something equivalent to “I want to learn A, B, and C,” the director should:

1. register the Language in data/languages.toml if absent;
2. create a minimal language pack if absent;
3. add/update the Language in the active learner profile;
4. record any explicitly preferred Dialect, StandardVariety, or HistoricalStage;
5. leave variety choice unresolved if none was supplied;
6. inspect the language-bootstrap capability matrix;
7. enqueue missing high-value language work such as orthography, tokenization, grammatical features, paradigms, syntax/constructions, phonology, and source/analyzer declarations;
8. create or reprioritize engineering macro-goals only when software/tooling support is missing.

Activation therefore creates a language-level work surface even with no corpus yet. It does not automatically create a giant vocabulary list.

## Variety targeting is optional

A learner has the privilege of specifying a preferred variety but never the obligation.

Valid examples:

~~~text
Spanish
Spanish -> prefer Mexican Spanish
Chinese -> prefer Mandarin Chinese
Arabic -> target Classical Arabic + Modern Standard Arabic
Hebrew -> historical stages preferred; Modern Hebrew not default
~~~

No Language requires a designated Dialect before reading, lexicon work, or study can begin.

A variety preference should specialize future examples, pronunciation, lexical enrichment, corpus suggestions, and comparison views where relevant. It should not invalidate language-level knowledge already accumulated.

## Plural and historical targets

A Language can have multiple simultaneous learner targets.

Targets may be:
- Dialects;
- StandardVarieties;
- HistoricalStages;
- unresolved broad historical scopes awaiting later decomposition.

This is necessary for cases such as Classical Arabic plus Modern Standard Arabic, or a learner interested in several historical stages of Hebrew.

## Bounded portfolio

The recommended starting universe is not every known language. Use a bounded non-English portfolio, initially at most ten languages. Portfolio membership is explicit; relative tiers are normally revealed from activity rather than manually assigned.

English remains outside that attention cap because it is both infrastructure and a learnable first-class language.

See docs/13-language-portfolio.md.

## Relative focus

The default policy does not ask the principal to rank languages. Relative focus is revealed from activity using decayed salience and hysteresis.

An explicit statement such as “focus German today” is treated as an optional bounded override, not as required long-lived configuration.

## Language-world ontology

Language, Dialect, HistoricalStage, StandardVariety, LanguageFamily, WritingSystem, and ReconstructedLanguage are first-class ontology categories.

Their profiles belong under ontology/, not in the learner profile and not in computational language packs.

See docs/15-language-world-ontology.md and docs/16-language-dialect-policy.md.
