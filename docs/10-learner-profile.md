# 10 — Learner Profile and Priority

Linguistic truth and learner state must remain separate.

## Shared linguistic state

Examples:
- German has a case system;
- a lexeme has a particular sense;
- a form is dative plural;
- two senses are approximate translations;
- a corpus contains a token occurrence.

## Learner/profile state

Examples:
- German is currently high priority;
- Spanish is fluent/reference-level;
- Japanese reading is weak;
- a particular lexeme is well recognized but poorly produced;
- the learner prefers IPA visible by default;
- current study workload target is 20 reviews;
- one language is temporarily demoted.

These facts belong to a LearnerProfile.

## Initial scope

Linguarium is not being designed as a multitenant service.

The first implementation should support one local profile while preserving a clean profile boundary.

Repository bootstrap state lives under:

~~~text
profiles/default/
    profile.toml
~~~

Large/volatile operational learner data should eventually live in the application database, not be committed to Git on every review event.

The repository keeps:
- profile schema/configuration;
- stable declarative preferences;
- migration contracts;
- optional export/import snapshots.

The operational database keeps:
- review history;
- knowledge states;
- usage events;
- scheduling state;
- reading progress;
- high-frequency changing learner data.

## Language interest model

A profile may assign each language:

- role: pivot / active / reference / candidate / dormant;
- interest tier for non-English portfolio languages;
- explicit priority weight;
- proficiency estimates by modality;
- desired study modes;
- optional temporary focus boost.

Example:

~~~toml
[[languages]]
id = "de"
role = "active"
priority = 100

[languages.proficiency]
reading = "beginner"
listening = "beginner"
speaking = "beginner"
writing = "beginner"

[[languages]]
id = "es"
role = "reference"
priority = 40

[languages.proficiency]
reading = "fluent"
~~~

## Interest tiers

For bounded attention management, non-English portfolio languages may be grouped as:
- Tier 1: focus;
- Tier 2: active;
- Tier 3: exploratory/reference.

Interest tier is independent of proficiency and may change without deleting learner history.

English does not consume one of the suggested ten non-English portfolio slots because it is permanently available as interface/meta/pivot language and as a normal learnable language.

See docs/13-language-portfolio.md.

## Relative priority

When the principal says:

> I care more about German right now.

the director/profile layer should increase German's explicit priority or focus boost and thereby relatively demote competing work.

This affects:
- corpus processing order;
- lexical enrichment queues;
- language-bootstrap work;
- study scheduling;
- suggested reading;
- UI prominence.

It must not rewrite objective linguistic data.

## Usage-derived signals

Linguarium may infer *signals* from behavior:
- recent reading time;
- reviews completed;
- corpus opens;
- lookup frequency;
- failure rate;
- repeated unknown words.

But usage must not silently override explicit intent.

Priority should conceptually combine:

~~~text
effective_priority =
    explicit_profile_priority
  + temporary_focus_boost
  + bounded_usage_signal
  + current_learning_need
~~~

The exact scoring policy is implementation work.

Explicit principal intent outranks inferred usage.

## Profile portability

Profile data should be exportable independently of the shared linguistic database where practical.

This separation allows:
- rebuilding or sharing ontology data without exposing learner history;
- resetting study state without deleting lexicons;
- future alternate profiles without redesigning the model;
- deterministic backup/migration.
