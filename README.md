# Linguarium

A repository-mediated language-learning workbench for turning corpora into durable linguistic knowledge, study material, and comparative language views.

Linguarium is not primarily a flashcard app. It is a system for incrementally transforming texts into a structured multilingual lexicon and ontology, then projecting that structure back into reading, study, morphology, phonology, translation, and comparison interfaces.

## Core loop

```text
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

The system must become useful before it becomes complete. A corpus may be imported while only a handful of its words are integrated. Every later integration should improve all projections that reference the same entities.

## Governing principles

1. **Corpus first, ontology incrementally.** Texts create demand for linguistic structure; they do not require the ontology to be complete in advance.
2. **Occurrences are not lexemes.** The corpus owns token occurrences. The lexicon owns language-level lexical entities.
3. **Knowledge is relational.** “Known” is not a property of a word; it is a learner's state relative to an entity and skill.
4. **English is the default semantic pivot, not the ontology.** English glosses provide a common practical foothold across languages, but language-specific concepts must remain representable on their own terms.
5. **Preserve source truth.** Imported texts are stored as reproducible snapshots with provenance and hashes so annotations do not drift when upstream sources change.
6. **Represent structure below the word when useful.** Forms, morphemes, grammatical features, phonemes, graphemes, and spans are first-class when the language requires them.
7. **Alignment is many-to-many.** Translation correspondence may connect phrases, words, morphemes, or grammatical features; never force false one-to-one mappings.
8. **Projections do not own truth.** Reader colors, flashcards, conjugation tables, and comparison views are views over shared data.
9. **Language diversity may challenge the model.** Do not hard-code Indo-European assumptions as universal linguistic facts.
10. **Queue unfinished cognition.** Corpus ingestion, lexical enrichment, ontology integration, review, and correction must all have durable repository-native queues.
11. **Automate extraction; review semantics.** Machines may propose tokens, lemmas, analyses, translations, and relations. Durable semantic integration remains reviewable and provenance-bearing.
12. **One platform first.** Keep subsystems in this repository until a component develops a genuinely independent lifecycle and reusable contract.

## Repository operating model

Linguarium follows [sguzman/software-philosophy](https://github.com/sguzman/software-philosophy).

- The human principal supplies intent, taste, corpora, language priorities, local observations, and final veto.
- ChatGPT acts as director / architect / integrator and owns product structure, ontology, roadmap, semantic review, and integration.
- Implementation workers receive bounded repository macro-goals and may not silently redefine architecture.
- The repository is the durable shared mind.
- Human testing must remain repo-native.
- Windows CLI dependencies should be declared through Scoop where appropriate.
- Nix/mise remain latent future options, not current work.

## Initial domains

```text
corpus/       source snapshots, document structure, token occurrences
lexicon/      lexemes, senses, forms, lexical relations
linguistics/  morphology, syntax, semantics, phonology, orthography
alignment/    cross-lingual span and feature correspondences
knowledge/    learner-state and learning evidence
study/        SRS/card projections and review events
ontology/     shared linguistic concept model
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

Machine-readable registries and queues live under `data/`. Per-language specialization lives under `languages/`. Learner-specific declarative state lives under `profiles/`. Repository macro-goals live under `goals/`.
