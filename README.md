# Linguarium

A repository-mediated language-learning workbench and language-world ontology for turning corpora into durable linguistic knowledge, study material, and comparative views.

Linguarium is not primarily a flashcard app. It is a system for incrementally transforming texts into a structured multilingual lexicon and ontology, while also maintaining profiles of languages, dialects, historical stages, writing systems, language families, and reconstructed linguistic systems.

The learner app is one interface into that universe.

## Core loop

```text
language-world ontology
        +
corpus source
  -> immutable corpus snapshot
  -> segmentation/tokenization
  -> lexical candidates
  -> lexeme integration queue
  -> enriched lexical/grammatical/semantic entities
  -> personal knowledge state
  -> reader/SRS/comparison projections
  -> new learning evidence
  -> updated knowledge state
```

The system must become useful before it becomes complete. A corpus may be imported while only a handful of its words are integrated. A language may have a useful ontology profile while its computational pack is incomplete. Every later integration should improve all projections that reference the same entities.

## Governing principles

1. **Corpus first, ontology incrementally.** Texts create demand for linguistic structure; they do not require the ontology to be complete in advance.
2. **Languages are ontology objects too.** Families, writing systems, reconstructed languages, languages, dialects, standards, and historical stages can have durable profiles and relations.
3. **Categories are empty by default.** Defining LanguageFamily does not authorize importing every known family; entity population is demand-driven.
4. **Occurrences are not lexemes.** The corpus owns token occurrences. The lexicon owns language-level lexical entities.
5. **Knowledge is relational.** “Known” is not a property of a word; it is a learner's state relative to an entity and skill.
6. **English is the default semantic pivot, not the ontology.** English glosses provide a common practical foothold across languages, but language-specific concepts must remain representable on their own terms.
7. **Dialect choice is optional.** A learner may specify Mexican Spanish, Mandarin, a historical stage, or multiple Arabic standards/stages, but no Language requires a designated variety before work can begin.
8. **Language/dialect classification is explicitly fuzzy.** Conventional, sociopolitical, historical, and structural evidence may all matter; Linguarium records the organizing convention rather than pretending the boundary is perfectly objective.
9. **Preserve source truth.** Imported texts are stored as reproducible snapshots with provenance and hashes so annotations do not drift when upstream sources change.
10. **Represent structure below the word when useful.** Forms, morphemes, grammatical features, phonemes, graphemes, and spans are first-class when the language requires them.
11. **Alignment is many-to-many.** Translation correspondence may connect phrases, words, morphemes, or grammatical features; never force false one-to-one mappings.
12. **Projections do not own truth.** Reader colors, flashcards, conjugation tables, and comparison views are views over shared data.
13. **Language diversity may challenge the model.** Do not hard-code Indo-European assumptions as universal linguistic facts.
14. **Queue unfinished cognition.** Ontology intake, corpus ingestion, lexical enrichment, ontology integration, review, and correction must all have durable repository-native queues.
15. **Automate extraction; review semantics.** Machines may propose tokens, lemmas, analyses, translations, classifications, and relations. Durable semantic integration remains reviewable and provenance-bearing.
16. **One platform first.** Keep subsystems in this repository until a component develops a genuinely independent lifecycle and reusable contract.

## Repository operating model

Linguarium follows [sguzman/software-philosophy](https://github.com/sguzman/software-philosophy).

- The human principal supplies intent, taste, corpora, language interests, optional variety preferences, local observations, and final veto.
- ChatGPT acts as director / architect / integrator and owns product structure, ontology, classification policy, roadmap, semantic review, and integration.
- Implementation workers receive bounded repository macro-goals and may not silently redefine architecture.
- The repository is the durable shared mind.
- Human testing must remain repo-native.
- Windows CLI dependencies should be declared through Scoop where appropriate.
- Nix/mise remain latent future options, not current work.

## Initial domains

```text
ontology/     language-world entity profiles and category schema
corpus/       source snapshots, document structure, token occurrences
lexicon/      lexemes, senses, forms, lexical relations
linguistics/  morphology, syntax, semantics, phonology, orthography
alignment/    cross-lingual span and feature correspondences
knowledge/    learner-state and learning evidence
study/        SRS/card projections and review events
languages/    computational language/variety packs
profiles/     learner-specific stable declarative state
importers/    Gutenberg/custom/subtitle/etc. ingestion adapters
app/          GUI projections over the shared model
```

These are architectural domains, not separate repositories.

## Start here

Read in order:

1. `AGENTS.md`
2. `docs/00-vision.md`
3. `docs/01-ontology.md`
4. `docs/02-corpus-to-knowledge-pipeline.md`
5. `docs/03-english-pivot.md`
6. `docs/04-language-universe.md`
7. `docs/05-artifacts-and-provenance.md`
8. `docs/06-queues-and-lifecycle.md`
9. `docs/07-language-packs.md`
10. `docs/08-language-bootstrap.md`
11. `docs/09-ontology-layers.md`
12. `docs/10-learner-profile.md`
13. `docs/11-app-and-study-interface.md`
14. `docs/12-english-special-status.md`
15. `docs/13-language-portfolio.md`
16. `docs/14-revealed-language-salience.md`
17. `docs/15-language-world-ontology.md`
18. `docs/16-language-dialect-policy.md`

Machine-readable registries, workspace defaults, and queues live under `data/`. Language-world profiles live under `ontology/`. Per-language computational specialization lives under `languages/`. Learner-specific declarative state lives under `profiles/`. Repository macro-goals live under `goals/`.
