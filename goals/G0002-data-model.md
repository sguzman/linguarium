# G0002 — Canonical Data Model

Status: queued

## Objective

Translate the conceptual ontology in docs/01-ontology.md into a versioned storage model and migration strategy suitable for the G0001 vertical slice while preserving future extension to morphology, phonology, alignment, and SRS.

## Required decisions

- storage engine for operational local data;
- stable ID strategy;
- schema versioning/migrations;
- corpus snapshot identity;
- span/offset representation;
- lexeme/sense/form separation;
- provenance envelope;
- learner knowledge/evidence representation;
- queue persistence;
- export/import boundary.

## Constraint

Do not model future richness by stuffing arbitrary untyped JSON everywhere. Also do not normalize hypothetical future features so aggressively that G0001 becomes impossible to implement.

The data model should be extensible, typed, and incrementally useful.
