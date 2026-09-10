# Linguarium Ontology Store

This tree stores durable profiles for language-world entities.

It is distinct from:

- `languages/` — computational language packs and capability state;
- `profiles/` — learner-specific preferences, portfolio membership, proficiency, and salience policy;
- the operational database — high-volume lexemes, senses, occurrences, learner events, and study state.

## Entity categories

The schema recognizes at least:

- LanguageFamily
- WritingSystem
- ReconstructedLanguage
- Language
- LanguageVariety
- Dialect
- StandardVariety
- HistoricalStage

Additional categories may be added when real language data demands them.

## Storage convention

Entity profiles live under category-oriented paths such as:

~~~text
ontology/entities/languages/<id>/profile.toml
ontology/entities/dialects/<id>/profile.toml
ontology/entities/language-families/<id>/profile.toml
ontology/entities/writing-systems/<id>/profile.toml
ontology/entities/reconstructed-languages/<id>/profile.toml
ontology/entities/historical-stages/<id>/profile.toml
~~~

The directory is not the entity's ultimate identity. Stable IDs inside profiles must survive reclassification/moves.

## Empty-by-default

Do not populate category catalogues merely because the category exists.

At bootstrap, categories may have zero instances. Add entities only when demanded.

The initial explicitly requested ontology instances are Spanish and Mexican Spanish.
