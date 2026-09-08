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

Learner-specific role, interest tier, priority, proficiency, and focus live under profiles/, initially profiles/default/profile.toml. English's workspace-wide interface/meta/pivot defaults live separately in data/workspace.toml.

Roles include:

### pivot
Default interlingual semantic foothold for this learner/profile.

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

1. register the language in data/languages.toml if absent;
2. create a minimal language pack if absent;
3. add/update the language in the active learner profile;
4. inspect the language-bootstrap capability matrix;
5. enqueue missing high-value language work such as orthography, tokenization, grammatical features, paradigms, syntax/constructions, phonology, and source/analyzer declarations;
6. create or reprioritize engineering macro-goals only when software/tooling support is missing.

Activation therefore creates a language-level work surface even with no corpus yet. It does not automatically create a giant vocabulary list.

Corpus work and language-bootstrap work are separate demand planes. Learner priority is a third demand plane. See docs/08-language-bootstrap.md and docs/10-learner-profile.md.

## Bounded portfolio

The recommended starting universe is not every known language. Use a bounded non-English portfolio, initially at most ten languages, grouped into interest tiers.

English remains outside that attention cap because it is both infrastructure and a learnable first-class language.

See docs/13-language-portfolio.md.

## Relative focus

When the principal says “I care more about German right now,” that is primarily a profile update.

German's explicit priority/focus rises. Other languages become relatively less urgent without losing their ontology or learner history.

Usage-derived signals may later influence effective priority, but explicit principal intent outranks inferred behavior.

## Variety principle

If a distinction matters pedagogically, represent the variety rather than pretending the parent language is homogeneous.

Regional pronunciation, historical stages, script reforms, formal/informal registers, and dialect-specific vocabulary may eventually matter.

Do not create varieties gratuitously. Add them when corpus or learner needs justify the distinction.
