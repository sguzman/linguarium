# 01 — Foundational Ontology

This document defines Linguarium's initial conceptual entities. It is deliberately extensible: languages, corpora, historical evidence, and learner use are allowed to falsify or refine the model.

## Language-world identity

### LanguageFamily
A genealogical grouping whose members are proposed to descend from a common ancestral linguistic system.

Family membership and branching are claims with provenance rather than immutable labels.

### WritingSystem
A conventional system for representing language graphically.

Languages and writing systems are many-to-many over history. More specific concepts such as Script, Orthography, GraphemeInventory, and transliteration systems may be modeled beneath or beside this category when demanded.

### ReconstructedLanguage
A linguistic system inferred from comparative/historical evidence rather than directly attested as a complete language.

Reconstructed entities carry explicit epistemic status and may participate in ancestry/family relations without being treated as directly observed historical recordings.

### Language
A canonical umbrella node for a conventionally recognized language-level linguistic system.

A Language is not assumed to be internally homogeneous and does not require a designated dialect.

### LanguageVariety
An abstract category for a coherent variety associated with a Language or language lineage.

### Dialect
A synchronic LanguageVariety conventionally organized beneath a Language.

Dialect status does not imply inferiority, corruption, or reduced complexity.

### StandardVariety
A LanguageVariety with an institutional, literary, administrative, educational, liturgical, or other standardizing role.

### HistoricalStage
A diachronically bounded LanguageVariety representing a historical stage of a Language or language lineage.

Language/dialect/variety classification is explicitly fuzzy and may be conventional or sociopolitically influenced. See docs/16-language-dialect-policy.md.

## Corpus identity

### CorpusSource
Where material came from: Gutenberg URL, pasted text, subtitle file, local import, transcription, etc.

### CorpusSnapshot
An immutable captured artifact used for reproducible annotation. A source may yield multiple snapshots over time.

### Document
A structured work inside a snapshot.

### Passage
A structural span such as chapter, section, paragraph, sentence, utterance, subtitle cue, or verse.

### TokenOccurrence
A span occurring at a specific location in a specific snapshot.

A token occurrence is not a word in the dictionary sense.

## Lexical and grammatical identity

### Lexeme
An abstract lexical unit conventionally grouped under a lemma and scoped to a Language/LanguageVariety where appropriate.

### Sense
A contextually distinguishable meaning of a lexeme.

### Form
An inflected, orthographic, phonological, or otherwise realized form associated with a lexeme.

### Paradigm
A structured family of forms organized by grammatical contrasts. A paradigm is language-specific and may be partial, irregular, defective, or disputed.

### Morpheme
A recurrent meaning-bearing or grammatical unit that may participate in forms.

### GrammaticalFeature
A language-relevant grammatical distinction such as number, case, tense, aspect, mood, person, class, evidentiality, politeness, etc.

The ontology must not assume every language has every feature or partitions a feature identically.

### Construction
A conventional pairing of linguistic form/structure with function that may not reduce cleanly to individual lexical entries.

### Grapheme
An orthographic unit.

### Phoneme
A contrastive phonological unit within a language/variety.

### Pronunciation
A pronunciation of a form or lexeme, potentially dialect/register specific and representable with IPA and audio.

## Semantic and historical relations

### Concept
A semantic concept used to relate senses without declaring that words across languages are identical.

### Definition
A prose explanation of a sense, in a declared language and with provenance.

### Gloss
A compact explanatory foothold, usually English by default.

A gloss is not the same thing as a sense and must not be treated as a perfect semantic equivalent.

### EtymologicalRelation
A provenance-bearing historical relation among lexical entities or forms, including derivation, borrowing, inheritance, or proposed cognacy. Historical uncertainty must remain representable.

### TranslationRelation
A context-sensitive relation between source and target spans/entities. It may express equivalence, approximation, explanatory rendering, idiomatic translation, or literal correspondence.

### Alignment
A correspondence between spans or linguistic features. Alignment is many-to-many and may occur at passage, phrase, token, morpheme, or feature level.

## Learner identity

### LearnerProfile
The identity to which personal acquisition state and stable preferences belong.

The foundation assumes one local learner while retaining the conceptual boundary.

### KnowledgeState
The learner's current relationship to an entity.

Possible dimensions include reading recognition, listening recognition, prompted recall, free production, pronunciation, and grammatical analysis confidence.

### LearningEvidence
An event that informs knowledge state: encounter, review, successful recall, failed recall, production, correction, etc.

### StudyItem
A generated or curated exercise referencing canonical entities.

It should not duplicate dictionary truth.

## Core relations

~~~text
LanguageFamily <-> Language / ReconstructedLanguage
Language -> Dialect / StandardVariety / HistoricalStage
Language / LanguageVariety <-> WritingSystem
ReconstructedLanguage -> reconstructed ancestry/family relations

CorpusSource -> CorpusSnapshot -> Document -> Passage -> TokenOccurrence
TokenOccurrence -> Form? -> Lexeme -> Sense -> Concept?
Form -> Paradigm*
Form -> Morpheme*
Form -> GrammaticalFeature*
Form/Lexeme -> Pronunciation*
Sense -> Definition*
Sense -> Gloss*
Sense <-> Sense         lexical/semantic relations
Span <-> Span           translation/alignment relations

LearnerProfile -> preferred Language/Variety/Stage*
LearnerProfile -> KnowledgeState -> linguistic entity
LearningEvidence -> KnowledgeState
StudyItem -> linguistic entities / corpus spans
~~~

## Separation invariants

Do not collapse:
- language-world ontology profile and computational language pack;
- objective language classification and learner variety preference;
- Language and mandatory reference Dialect;
- attested Language and ReconstructedLanguage epistemic status;
- occurrence and form;
- form and lexeme;
- lexeme and sense;
- sense and English gloss;
- concept and English word;
- translation and alignment;
- objective linguistic data and learner knowledge;
- learner knowledge and UI color;
- provenance and confidence.

## Open-world principle

Unknown is a valid state.

A Language may exist without a selected Dialect. A learner may request a broad historical scope before individual HistoricalStages are instantiated. A family relation may remain unresolved. A token may exist without a resolved lexeme. A lexeme may exist without a complete paradigm. A sense may exist without a cross-language equivalent. A construction may exist before a formal syntactic analysis is available.

The model should absorb increasing knowledge without requiring destructive rewrites.
