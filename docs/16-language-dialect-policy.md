# 16 — Language, Dialect, and Variety Policy

The language/dialect boundary is fuzzy, historically contingent, and partly sociopolitical. Linguarium will not pretend otherwise.

## Organizing principle

For repository organization, Linguarium uses the following practical rule:

- **Language** is the canonical umbrella node when a linguistic system is conventionally treated as a language in the project's working sources and ordinary scholarly/reference usage.
- **Dialect** is a synchronic subordinate variety when it is conventionally treated as part of a broader Language node.
- **StandardVariety** is used when a formal/literary/administrative standard is better modeled as a standardized variety than as a regional dialect.
- **HistoricalStage** is used when the distinction is primarily diachronic rather than regional/social.

This is an organizing convention, not a discovery of a perfectly objective natural boundary.

## The army-and-navy warning

Linguarium explicitly accepts the force of the old aphorism that “a language is a dialect with an army and a navy” as a warning: political institutions, literary standards, identity, education, state power, and historical convention materially affect what societies call a language versus a dialect.

The aphorism is not used as a literal decision algorithm. It exists to prevent false scientific certainty.

## Classification evidence

When classification is ambiguous, consider multiple kinds of evidence:

- conventional linguistic/reference treatment;
- mutual intelligibility and structural distance;
- existence of a shared or separate standard language;
- literary and educational traditions;
- speaker identity and self-designation;
- political/institutional recognition;
- historical lineage;
- practical usefulness to the learner and corpus system.

No single criterion is universally decisive.

## Conventional classification is allowed

Linguarium may choose a conventional category simply because it produces a stable, legible ontology.

Such a choice should be marked with metadata such as:

~~~text
classification_basis = "conventional"
classification_confidence = "working"
classification_disputed = true/false
~~~

Do not hide arbitrariness behind overconfident prose.

## Identity survives reclassification

A linguistic entity's stable identity should survive later reclassification.

If a variety initially treated as a Dialect is later better modeled as a Language, the preferred operation is to change its classification and relations rather than pretend a new linguistic object came into existence.

## No mandatory dialect selection

A Language may be used without a designated Dialect or StandardVariety.

This is a hard usability rule.

The learner may simply say:

> I want Spanish.

and begin.

If later they say:

> Prefer Mexican Spanish.

Linguarium adds that preference without invalidating earlier Spanish data.

Missing dialect specification is therefore a valid state, never a prerequisite for language activation.

## Reference variety is separate from ontological parentage

A project may choose a default/reference variety for pronunciation, spelling, examples, or UI generation.

That does not make the reference variety the ontological parent of other dialects.

For Spanish, Linguarium uses **Spanish** as the umbrella Language node. Mexican Spanish is a Dialect/national variety of Spanish. European/Spain varieties, if later instantiated, would be sibling varieties under Spanish rather than the metaphysical “real Spanish” from which Mexican Spanish is treated as a defective offshoot.

Historical ancestry may of course be represented separately through historical relations.

## Plural targeting

A learner may target more than one variety or stage of the same Language.

Examples:
- Mexican Spanish plus a later European Spanish comparison target;
- Classical Arabic plus Modern Standard Arabic;
- several historical stages of Hebrew.

The learner profile may express preferred, secondary, historical, or comparison targets independently.
