# 12 — English Special Status

English is both an ordinary first-class linguistic object and a special operational language in the initial Linguarium workspace.

The specialness is role-based, not type-based.

## English as ordinary linguistic data

English participates in the same canonical ontology as every other language:

- English Lexeme;
- English Sense;
- English Form;
- English Construction;
- English Pronunciation;
- English corpora;
- English learner KnowledgeState;
- English StudyItems;
- English semantic and etymological relations.

There is no special EnglishLexeme or EnglishSense type.

This means the learner can:
- catalogue rare or technical English vocabulary;
- read English corpora with knowledge overlays;
- generate English flashcards;
- maintain spelling/pronunciation knowledge;
- study etymology, morphology, register, and constructions;
- discover gaps in English vocabulary despite high overall fluency.

High proficiency does not disable learner machinery.

## English as semantic pivot

English is the default destination for practical semantic footholds from other languages.

A newly integrated non-English Sense should normally be eligible for:
- an English gloss;
- an English explanatory definition;
- one or more English translation relations where justified.

This is baseline interlingual accessibility, not a declaration that the English lexical item is the true concept.

Conceptually:

~~~text
German Sense
   |
   +--> English gloss/explanation
   |
   +--> English Sense relation when justified
   |
   +--> Concept relation when justified
~~~

The English foothold is expected by default. Direct non-English-to-non-English translation is optional enrichment.

## English as metalanguage

English is the initial human-readable metalanguage of Linguarium.

Unless a view explicitly requests otherwise, English is used for:
- UI labels and instructions;
- grammar explanations;
- ontology descriptions;
- provenance notes;
- semantic definitions/glosses intended for the learner;
- study instructions and error explanations.

The data model must still store the language of every Definition/Gloss/Note explicitly rather than assuming all prose is English forever.

## English as interface language

The initial desktop UI language is English.

This is a workspace/profile preference, not a linguistic truth.

A future interface localization must not require changing the ontology.

## English as source language for study

English frequently serves as the cue side of production study for another language:

~~~text
English semantic foothold -> produce German form
English explanation       -> identify Japanese construction
English concept cue       -> recall Russian lexeme
~~~

English can simultaneously be the target of its own learner exercises.

## Default mapping policy

For an active non-English language, the baseline expectation is:

1. preserve the language-local Sense;
2. provide an English semantic foothold when useful;
3. relate to a specific English Sense only when justified;
4. relate both to shared Concepts when justified;
5. add direct pairwise translations only when useful.

Thus English is the common practical destination while the ontology remains multilingual and distinction-preserving.

## English does not consume a target-language slot

The learner's bounded portfolio of languages-to-pursue is conceptually separate from English's permanent operational roles.

English remains registered and learnable even if the learner says “these are the ten other languages I care about most.”

This avoids the awkward choice between treating English as invisible infrastructure or consuming scarce attention-budget capacity.
