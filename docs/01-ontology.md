# 01 — Foundational Ontology

This document defines the initial conceptual entities. It is deliberately extensible: languages are allowed to falsify or refine the model.

## Identity layers

### Language
A named linguistic system or variety used as the scope for lexical and grammatical entities.

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

### Lexeme
An abstract lexical unit conventionally grouped under a lemma.

### Sense
A contextually distinguishable meaning of a lexeme.

### Form
An inflected, orthographic, phonological, or otherwise realized form associated with a lexeme.

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

### Concept
A semantic concept used to relate senses without declaring that words across languages are identical.

### Gloss
A compact explanatory foothold, usually English by default.

A gloss is not the same thing as a sense and must not be treated as a perfect semantic equivalent.

### TranslationRelation
A context-sensitive relation between source and target spans/entities. It may express equivalence, approximation, explanatory rendering, idiomatic translation, or literal correspondence.

### Alignment
A correspondence between spans or linguistic features. Alignment is many-to-many and may occur at passage, phrase, token, morpheme, or feature level.

### LearnerProfile
The identity to which personal acquisition state belongs.

The foundation may assume one local learner while retaining the conceptual boundary.

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
CorpusSource -> CorpusSnapshot -> Document -> Passage -> TokenOccurrence
TokenOccurrence -> Form? -> Lexeme -> Sense -> Concept?
Form -> Morpheme*
Form -> GrammaticalFeature*
Form/Lexeme -> Pronunciation*
Sense -> Gloss*
Sense <-> Sense         lexical/semantic relations
Span <-> Span           translation/alignment relations
LearnerProfile -> KnowledgeState -> linguistic entity
LearningEvidence -> KnowledgeState
StudyItem -> linguistic entities / corpus spans
~~~

## Separation invariants

Do not collapse occurrence and form; form and lexeme; lexeme and sense; sense and English gloss; concept and English word; translation and alignment; objective linguistic data and learner knowledge; learner knowledge and UI color; or provenance and confidence.

## Open-world principle

Unknown is a valid state.

A token may exist without a resolved lexeme. A lexeme may exist without a complete paradigm. A sense may exist without a cross-language equivalent. A construction may exist before a formal syntactic analysis is available.

The model should absorb increasing knowledge without requiring destructive rewrites.
