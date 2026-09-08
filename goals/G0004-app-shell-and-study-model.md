# G0004 — Rust + egui App Shell and Study Model

Status: queued

## Objective

Materialize Linguarium's first native desktop application shell in Rust + egui/eframe as a thin projection over the shared model, while defining the typed StudyTarget / StudyTemplate / StudyItem / ReviewEvent / ScheduleState boundaries.

## Required capabilities

1. Rust workspace and repo-native run/test entrypoints;
2. egui/eframe desktop shell;
3. navigation surfaces for Reader, Study, Lexicon, Analyze/Compare, and Languages/Profile;
4. no duplicated linguistic truth in UI-only models;
5. typed study-domain entities;
6. at least one recognition-card template over canonical lexeme/sense data;
7. low-friction review interaction;
8. language/profile priority visible in the control surface;
9. deterministic tests for study-item generation and corrected canonical data flowing into projections;
10. performance architecture based on lazy/indexed working sets rather than loading all languages into interactive state.

## Not required

A polished visual theme, full morphology visualization, subtitle/video integration, a mature SRS algorithm, or exhaustive keyboard bindings are not required for the first shell.

## Dependency

Build against the accepted canonical storage/domain boundaries from G0002 and coordinate with the G0001 vertical slice.

The app is not permitted to become a second source of ontology truth.
