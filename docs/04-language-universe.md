# 04 — Language Universe

Linguarium should not assume that every supported language deserves equal active processing.

The repository therefore maintains a declared language universe: the set of languages/varieties currently known to the workspace, together with their role and processing priority.

Machine-readable state lives in data/languages.toml.

## Roles

### pivot
Default interlingual semantic foothold. Initially English.

### active
A language the learner currently wants corpora, lexical integration, and study workflows to actively support.

### reference
A language useful for comparison or already strong enough that aggressive study is not necessarily needed.

### candidate
Interesting but not currently authorized for substantial processing.

### dormant
Previously used but not currently active.

## Proficiency is separate from role

A fluent language can be active. A beginner language can be reference.

Role answers “what should Linguarium spend work on?”
Proficiency answers “what is the learner's current relationship to the language?”

Do not infer one from the other.

## Activation

When the principal says something equivalent to “I want to learn A, B, and C,” the director should:

1. update the registry;
2. create a minimal language pack if absent;
3. inspect the language-bootstrap capability matrix;
4. enqueue missing high-value language work such as orthography, tokenization, grammatical features, paradigms, syntax/constructions, phonology, and source/analyzer declarations;
5. create or reprioritize engineering macro-goals only when software/tooling support is missing.

Activation therefore creates a language-level work surface even with no corpus yet. It does not automatically create a giant vocabulary list.

Corpus work and language-bootstrap work are separate demand planes. See docs/08-language-bootstrap.md.

## Variety principle

If a distinction matters pedagogically, represent the variety rather than pretending the parent language is homogeneous.

Regional pronunciation, historical stages, script reforms, formal/informal registers, and dialect-specific vocabulary may eventually matter.

Do not create varieties gratuitously. Add them when corpus or learner needs justify the distinction.
