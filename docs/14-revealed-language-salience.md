# 14 — Revealed Language Salience

The learner should not be required to manually rank portfolio languages.

Portfolio membership is explicit. Relative salience is normally revealed by use.

## Core distinction

### Explicit state
The learner chooses whether a language belongs in the portfolio.

### Revealed state
The system infers which portfolio languages are currently receiving the learner's attention.

### Proficiency state
The system separately estimates what the learner can actually do in each language.

These three dimensions must not be collapsed.

## Salience, not permanent priority

Each portfolio language has a continuously changing salience score derived from activity.

Potential signals include:
- corpus opens;
- reading duration;
- words looked up;
- lexical integrations triggered;
- flashcards reviewed;
- review failures/successes;
- language-specific app sessions;
- listening/subtitle activity;
- explicit one-off actions such as “study Japanese now.”

The exact weights are implementation policy.

## Decay

Recent activity should matter more than old activity.

Salience therefore decays over time unless reinforced.

This lets the learner naturally drift among languages without manually editing priorities.

## Hysteresis

Derived tiers must not flap constantly.

A small temporary spike should not instantly promote or demote a language.

Tier transitions should require enough sustained evidence, use smoothing, and/or use separate promotion/demotion thresholds.

The continuous salience score is primary. Tier labels are coarse UI projections.

## Revealed tiers

The app may project salience into labels such as:

- Focus
- Active
- Background

These are not manually assigned by default and are not durable truths about the learner.

A language can move among them automatically as activity changes.

## No ranking burden

The learner should never be required to answer:
- “Which language is #3?”
- “Is French 70 or 75 priority?”
- “Do you care more about Russian or Japanese today?”

The system should infer enough from behavior to allocate attention.

## Optional override

Explicit focus remains available but optional.

Examples:
- “Focus Russian today.”
- “Keep Spanish in the background this week.”
- “Do not surface Arabic for now.”

Such instructions act as bounded overrides or modifiers. They should not erase historical salience or proficiency.

## Cold start

When a portfolio is first declared and has little activity history, all non-English portfolio languages may begin with equal neutral salience.

Do not force an initial ranking.

If the learner offers a vague statement such as “Spanish, German, Japanese, and Chinese might be more important,” do not hard-code an ordering unless they explicitly request it. Activity should resolve the ambiguity.

## Resource allocation

Revealed salience may influence:
- bootstrap-work order;
- corpus processing;
- lexical enrichment;
- study queue selection;
- suggested reading;
- UI ordering/prominence.

It must not alter objective linguistic facts.

## English

English participates in learner activity and can have its own salience for English-vocabulary study, but its special workspace roles (interface, metalanguage, semantic pivot) do not depend on salience and are never demoted by inactivity.
