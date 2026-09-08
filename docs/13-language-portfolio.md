# 13 — Bounded Language Portfolio

Linguarium may know about arbitrarily many languages, but the learner should not need to actively pursue all of them.

The default operating model uses a bounded language portfolio.

## Recommendation

Start with at most ten non-English languages that materially interest the learner.

English does not consume one of these slots because it is permanently available as:
- interface language;
- metalanguage;
- semantic pivot;
- ordinary learnable language.

Ten is an attention-management convention, not a technical hard limit.

## Portfolio membership is explicit

The learner chooses which languages belong in the portfolio.

That is the main stable interest input.

The learner is not required to rank them.

## Interest tiers are revealed

Labels such as Focus / Active / Background are derived from recent and sustained activity rather than manually assigned by default.

The system should infer relative salience from:
- reading;
- lookups;
- reviews;
- language-specific sessions;
- lexical/corpus activity;
- other learner actions.

Use decay and hysteresis so tiers respond to real shifts without constantly flapping.

See docs/14-revealed-language-salience.md.

## Interest is not proficiency

A highly fluent language can become the most salient language.
A completely new language can also become the most salient language.

Salience controls resource allocation.
Proficiency models learner capability.

Do not collapse them.

## Proficiency is provisional and discoverable

The profile may begin with rough self-estimates or unknown values.

Over time, the operational system can accumulate evidence by modality:
- reading comprehension;
- listening recognition;
- lexical lookup rate;
- review performance;
- production success;
- morphology/syntax task performance.

Store explicit self-estimate separately from evidence-derived competence when implementation reaches that stage.

The system should become more accurate about proficiency through use rather than demanding a placement-test bureaucracy before the learner can begin.

## Portfolio operation

When the principal supplies an unordered list of languages, the director should:

1. register missing languages;
2. create minimal language packs;
3. add them to the learner portfolio with neutral initial salience;
4. enqueue appropriate bootstrap work;
5. avoid exhaustive lexical population until corpora or learner demand justify it;
6. let activity reveal relative tiers over time.

The learner should not need to supply grammar facts, scripts, tokenizers, dictionary sources, or an explicit ordering.
