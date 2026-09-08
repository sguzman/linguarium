# 11 — Application and Study Interface

## Technology decision

The native desktop application is Rust + egui/eframe unless deliberately superseded.

The GUI is intentionally a thin projection layer over Linguarium's canonical model.

It should not contain a second hidden ontology in widget state.

## Product shape

The app combines the useful surfaces of:
- Language Reactor: text/subtitle consumption with linguistic overlays;
- Anki: durable spaced-repetition scheduling and review;
- Vocage: focused vocabulary study;
- dictionary/grammar workbench;
- comparative/interlinear linguistic visualization.

The application should remain visually clean even as the underlying ontology becomes rich.

## Primary surfaces

### 1. Reader

The central consumption surface.

Responsibilities:
- open a corpus document;
- render stable text;
- color/annotate tokens by learner state;
- click/hover a token to inspect its analysis;
- show lemma, sense, gloss, morphology, pronunciation, and provenance progressively;
- create or prioritize lexical work from unknown material;
- optionally show aligned translation;
- expose sentence/morpheme overlays;
- record reading progress and learning evidence.

The default view should stay readable. Rich annotation is layered on demand rather than permanently cluttering the page.

### 2. Study

SRS/review surface.

Responsibilities:
- present generated study prompts;
- capture review outcomes;
- update scheduling state;
- update learner evidence/knowledge;
- filter/focus by language and skill;
- inspect why a card exists and which canonical entities it references.

### 3. Lexicon

Browse/search canonical language-local knowledge.

Responsibilities:
- search lexemes, senses, forms, constructions;
- inspect paradigms;
- show corpus attestations;
- show semantic and etymological relations;
- edit/review proposed integrations;
- inspect provenance.

### 4. Analyze / Compare

Structured linguistic visualization.

Responsibilities:
- sentence alignment;
- word/morpheme correspondence;
- conjugation/declension paradigms;
- grammatical-feature coloring;
- syntax/construction overlays;
- cross-language comparison;
- IPA/orthography visualization.

### 5. Languages / Profile

Control plane.

Responsibilities:
- add/remove portfolio languages;
- show activity-derived salience and revealed tier;
- offer optional temporary focus overrides without requiring manual ranking;
- inspect capability maturity;
- inspect missing bootstrap work;
- set profile preferences;
- show progress/coverage without requiring configuration homework.

## Flashcard ontology

A flashcard must not be the canonical owner of vocabulary data.

Use separate concepts:

### StudyTarget
The canonical entity or relation being learned:
- Lexeme;
- Sense;
- Form;
- pronunciation;
- grapheme;
- morpheme;
- grammatical feature;
- Construction;
- aligned span;
- concept/relation.

### StudyTemplate
A reusable rule for constructing a prompt from canonical data.

### StudyItem
A materialized learning objective linking:
- target;
- template;
- optional corpus context;
- language/profile;
- scheduler state.

### ReviewEvent
One learner response:
- timestamp;
- outcome/grade;
- response time;
- optional error classification;
- evidence generated.

### ScheduleState
The current scheduling state produced by the selected SRS algorithm.

The scheduling algorithm must be replaceable without rewriting cards or linguistic entities.

## Initial template families

### Recognition
Show source form/context -> recall meaning/sense.

### Production
Show English foothold/context -> produce target-language form.

### Cloze
Hide a corpus span -> restore it.

### Morphology recognition
Show form -> identify lemma and feature bundle.

### Morphology production
Show lemma + requested features -> produce form.

### Listening
Play pronunciation/audio -> identify form/sense.

### Pronunciation
Show form -> produce/inspect pronunciation.

### Script/orthography
Grapheme <-> reading/sound/transliteration.

### Construction
Show sentence/context -> recognize or complete a grammatical construction.

Templates are projections. If a sense, gloss, pronunciation, or analysis is corrected, dependent study items should improve automatically.

## Review interaction

The default review flow should be low-friction:
1. prompt;
2. reveal;
3. compact self-grade / outcome;
4. next.

Detailed morphology/provenance/context must be available without forcing the learner through it every time.

Keyboard-first control is desirable.

## SRS scope

Linguarium should support an Anki-class scheduling model but should not clone Anki's note/card data ownership model.

Scheduling is one subsystem attached to StudyItems.

An initial mature scheduler may use FSRS or another well-understood algorithm if implementation review supports it. The scheduler choice is not ontology.

## App-performance doctrine

Adding languages must not linearly degrade interactive performance merely because more ontology exists.

The UI should query/index only relevant working sets:
- current language(s);
- current corpus;
- current review queue;
- requested comparison neighborhood.

Large ontology volume belongs behind indexed storage and lazy projections.

The learner must not pay cognitive or latency tax merely for having many languages registered.
