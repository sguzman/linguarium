# Linguarium Agent Guide

## Authority

The human principal owns:
- language-learning intent and priorities;
- corpus selection and additions;
- preferred dialects/standards/historical stages when they care to specify them;
- taste and usability judgments;
- local runtime observations;
- final veto.

ChatGPT in the director / architect / integrator role owns:
- product philosophy and scope;
- ontology and canonical terminology;
- language/dialect classification conventions and explicit uncertainty;
- architecture and subsystem boundaries;
- corpus-to-knowledge workflow;
- queue semantics and lifecycle;
- roadmap and repository macro-goals;
- semantic review of linguistic data conventions;
- acceptance, rejection, correction, and integration.

Implementation workers may implement explicitly authorized macro-goals, add tests and mechanical validation, propose bounded improvements needed to satisfy an accepted goal, and create candidate linguistic analyses when a goal explicitly authorizes automated enrichment.

Implementation workers may not silently:
- redefine the ontology;
- hide language/dialect classification ambiguity behind false certainty;
- require a designated dialect before a Language can be used;
- treat Dialect as inferior/corrupt Language;
- turn a learner variety preference into an objective linguistic fact;
- make English the universal linguistic model;
- collapse token occurrences into lexemes;
- collapse lexemes, senses, and forms;
- treat a machine translation as semantic truth;
- force one-to-one alignment where languages encode meaning differently;
- make GUI colors or flashcard fields canonical storage;
- create one GitHub issue per word/token/analysis item;
- bulk-populate language-world categories merely because they exist;
- discard provenance or overwrite source snapshots;
- redefine the active language universe;
- invent cross-language or historical relations without evidence;
- split architectural domains into new repositories;
- ask the principal to download and execute ad hoc payloads for normal development or QA.

## Repository doctrine

Follow sguzman/software-philosophy v1.3 unless this repository explicitly specializes a rule.

The repository is the durable shared mind. Important architectural decisions, queue contracts, data semantics, and acceptance criteria belong here rather than only in chat.

## Language-world ontology rule

Linguarium models languages themselves as ontology objects.

Keep separate:
- ontology entity profiles under ontology/ — what a language/family/dialect/writing system/historical stage is;
- language packs under languages/ — what Linguarium can computationally do with a language/variety;
- learner profiles under profiles/ — what the learner wants, knows, or currently prefers.

The language/dialect boundary is treated as fuzzy and partly conventional/sociopolitical. Use docs/16-language-dialect-policy.md as the organizing rule. Record classification basis and dispute state where relevant.

A Language does not require a selected Dialect. Variety specification is an optional learner privilege.

## High-volume work rule

GitHub issues and repository macro-goals are for bounded engineering/integration objectives.

High-volume linguistic work belongs in dedicated queues:
- ontology intake queue;
- corpus ingestion queue;
- document-analysis queue;
- lexeme integration queue;
- enrichment queue;
- alignment queue;
- review/correction queue.

A novel may produce tens of thousands of token occurrences and thousands of lexical candidates. Those are data-plane records, not project-management issues.

## Semantic evidence rule

Every durable linguistic assertion should be able to carry provenance and confidence.

Distinguish source-attested, mechanically derived, externally sourced, model-proposed, human/director reviewed, accepted canonical, and disputed/uncertain claims.

Machine output may accelerate enrichment. It may not erase uncertainty.

## English pivot rule

English is the default practical interlingual pivot for glosses and comparison because it reduces N×N translation work.

English is not the ontology, universal syntax, universal semantic decomposition, a mandatory literal translation target, or proof that two non-English terms are equivalent.

Language-specific concepts may remain partially untranslatable and receive English explanatory glosses rather than false equivalents.

## Incrementality rule

No stage may require global completeness.

A corpus is useful before every word is integrated. A lexeme is useful before every sense is known. A language is useful before its grammar model is complete. A reader is useful before automated morphology exists. Unknown structure must remain representable as unknown rather than blocked.

## Correction rule

Semantic and classificatory corrections preserve identity and lineage where possible. Do not mint a new entity merely to repair a bad gloss, analysis, language/dialect classification, or relation unless the earlier entity was genuinely a different thing.

## Application stack rule

The native desktop application uses Rust + egui/eframe unless the director deliberately supersedes this decision.

The GUI is a projection layer. It may not become a second canonical ontology or duplicate durable lexical/grammatical truth in widget-local models.

Learner-specific priority, proficiency, preferences, and study state must remain separable from shared linguistic truth. Stable declarative profile intent belongs under profiles/; volatile operational usage/review state belongs in the application database once available.

## Human execution rule

Normal development and QA must be repository-native. Encode dependencies and stable entrypoints in the repository. On Windows, use Scoop for ordinary CLI dependencies when appropriate. Nix/mise remain latent future options unless doctrine changes.
