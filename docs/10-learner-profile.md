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
- German is in the learner's portfolio;
- Japanese has high current revealed salience;
- Spanish reading is fluent;
- a particular lexeme is well recognized but poorly produced;
- the learner prefers IPA visible by default;
- one language has a temporary focus override.

These facts belong to a LearnerProfile.

## Initial scope

Linguarium is not being designed as a multitenant service.

The first implementation should support one local profile while preserving a clean profile boundary.

Repository bootstrap state lives under:

~~~text
profiles/default/
    profile.toml
~~~

Large/volatile operational learner data should eventually live in the application database, not be committed to Git on every event.

The repository keeps:
- portfolio membership;
- stable declarative preferences;
- optional coarse self-reported proficiency;
- migration contracts;
- optional export/import snapshots.

The operational database keeps:
- activity events;
- derived salience;
- revealed tier;
- review history;
- knowledge states;
- scheduling state;
- reading progress;
- evidence-derived proficiency;
- high-frequency changing learner data.

## Portfolio membership

Membership is the main explicit language-interest input.

The learner may simply say:

> These are the languages I care about.

No ordering or numeric priority is required.

## Revealed salience

Relative language attention is normally inferred from usage rather than manually ranked.

Activity-derived salience may use:
- reading;
- reviews;
- lookups;
- language-specific sessions;
- corpus operations;
- learning failures/successes.

Salience decays over time and uses hysteresis so the UI does not constantly reshuffle from trivial short-term activity.

Derived labels such as Focus / Active / Background are projections over salience, not durable profile facts.

See docs/14-revealed-language-salience.md.

## Optional explicit focus

The learner may still issue bounded overrides such as:
- “Focus Russian today.”
- “Keep Arabic in the background.”
- “Surface more Japanese this week.”

These are optional conveniences, never required configuration homework.

## Proficiency

Proficiency is separate from both portfolio membership and salience.

The system may begin with:
- a rough self-report;
- unknown;
- existing strong evidence.

Over time it should discover competence by modality from actual use.

Explicit self-report and evidence-derived estimates should remain distinguishable.

## English

English is permanently available as:
- interface language;
- metalanguage;
- semantic pivot;
- ordinary learnable language.

English may also accumulate learner knowledge state and English-study salience, but its infrastructure roles do not depend on activity.

## Profile portability

Profile data should be exportable independently of the shared linguistic database where practical.

This separation allows:
- rebuilding or sharing ontology data without exposing learner history;
- resetting study state without deleting lexicons;
- future alternate profiles without redesigning the model;
- deterministic backup/migration.
