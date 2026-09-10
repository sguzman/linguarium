# 15 — Language-World Ontology

Linguarium is not only a learner application. It is also a durable ontological workbench for languages as historical, social, grammatical, graphic, and genealogical objects.

The learner-facing application is one projection over this wider language-world ontology.

## Core categories

### LanguageFamily
A genealogical grouping whose members are proposed to descend from a common ancestral linguistic system.

Language-family structure is a graph of claims with provenance and confidence, not merely a display label. Subfamilies and branches may nest recursively.

### WritingSystem
A conventional system for representing language graphically.

WritingSystem is broader than a font or alphabet name. Linguarium may later distinguish Script, Orthography, GraphemeInventory, transliteration systems, historical script stages, and language-specific orthographic conventions.

A writing system can serve multiple languages; a language can use multiple writing systems.

### ReconstructedLanguage
A linguistic system inferred from comparative/historical evidence rather than directly attested as a complete spoken language.

Examples may eventually include Proto-Indo-European or other reconstructed proto-languages.

Reconstructed entities must carry explicit epistemic status. Reconstruction is not direct attestation, and competing reconstructions must remain representable.

### Language
A canonical organizing node for a conventionally recognized language-level linguistic system.

Language is not assumed to be internally homogeneous. It may contain Dialects, StandardVarieties, HistoricalStages, registers, and other varieties.

### LanguageVariety
A broader abstraction for a coherent linguistic variety associated with a Language or language lineage.

LanguageVariety exists so Linguarium does not force every meaningful variety into the binary language/dialect distinction.

### Dialect
A synchronic LanguageVariety conventionally treated as subordinate to a Language node.

Dialect status is an organizing classification, not a claim of inferiority, corruption, or lesser linguistic complexity.

### StandardVariety
A LanguageVariety with an institutional, literary, educational, liturgical, administrative, or other standardizing role.

This category is useful where a standard is not well described as simply one regional dialect.

### HistoricalStage
A diachronic LanguageVariety representing a historically bounded stage in a language or language lineage.

Examples may eventually include Biblical Hebrew, Mishnaic Hebrew, Old English, Middle English, or Classical stages of other languages.

HistoricalStage allows the learner to prefer historical forms of a language without pretending that thousands of years of change constitute one homogeneous target.

## Specific entities

A specific language is an instance classified as Language.

A specific dialect is an instance classified as Dialect.

A specific historical stage is an instance classified as HistoricalStage.

A specific reconstructed proto-language is an instance classified as ReconstructedLanguage.

Category definitions do not imply that Linguarium should pre-populate all known instances. The ontology grows demand-first.

## Relations

The language-world graph should eventually support relations including:

- member_of_family;
- subfamily_of;
- descends_from;
- reconstructed_ancestor_of;
- historical_stage_of;
- dialect_of;
- standard_variety_of;
- related_variety;
- uses_writing_system;
- formerly_used_writing_system;
- influenced_by;
- borrowed_from;
- contact_with;
- mutually_intelligible_with;
- partially_intelligible_with;
- standardized_from;
- learner_prefers_variety.

Every substantive historical/classificatory relation should be able to carry provenance, confidence, and dispute state.

## Language profiles

Language-world entities may have durable profiles independent of language packs.

A profile describes the entity as an object of knowledge: classification, names, historical scope, relations, writing systems, geography, sociolinguistic status, major grammatical traits, source notes, and provenance.

A language pack describes computational/learning support: tokenization, morphology adapters, source adapters, analyzers, and capability maturity.

Do not collapse these.

~~~text
ontology profile
    "What is Spanish?"

language pack
    "What can Linguarium currently do with Spanish?"

learner profile
    "What is the learner's relationship to Spanish?"
~~~

## Empty-by-default doctrine

Defining a category does not authorize bulk encyclopedic population.

Language families, writing systems, reconstructed languages, languages, dialects, standards, and historical stages are instantiated only when demanded by:
- the learner portfolio;
- a corpus;
- a comparison;
- an explicit principal request;
- a relation needed by an already integrated entity.

Linguarium should become an ontological emporium by accretion, not by importing the world's language catalogue on day one.
