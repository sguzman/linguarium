# 00 — Vision

Linguarium is a personal language-acquisition and computational-philology environment.

Its central promise is:

> Give the system text; progressively turn that text into structured linguistic knowledge; project that knowledge back into reading and study so every integration makes the corpus more legible.

The platform combines concerns normally scattered across separate products: dictionary and lexicon, corpus reader, vocabulary acquisition, SRS/flashcards, morphology and conjugation/declension visualization, phonology and IPA, script/orthography learning, translation, sentence/phrase/token/morpheme alignment, comparative linguistics, learner-state tracking, and grammatical/semantic ontology.

These are not independent products glued together. They are projections over shared entities.

## Product invariant

The durable model must be richer than any single interface.

A flashcard is a projection.
A colored reader is a projection.
A conjugation table is a projection.
An interlinear translation is a projection.
A cognate tree is a projection.

None of these should duplicate or own the underlying linguistic truth.

## First useful loop

The first complete vertical slice should support:

1. declare a language;
2. import a text snapshot;
3. segment it into stable passages/sentences/tokens;
4. resolve or create lexeme candidates;
5. click an unknown token in a reader;
6. integrate a minimal lexical record;
7. record learner knowledge;
8. recolor every occurrence of that lexeme;
9. derive SRS material from the shared record;
10. let review evidence update knowledge state.

Everything more sophisticated extends this loop.

## Non-goals for the foundation

The foundation does not require all languages, perfect lemmatization, automatic grammar parsing, N×N translation, full historical linguistics, a complete universal grammar, Netflix integration, game dialogue extraction, or automatic speech recognition.

Those may become projections/adapters after the shared model is proven.
