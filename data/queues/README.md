# Queue Fixtures

These files bootstrap Linguarium's high-volume work contracts before the operational database exists.

They are not intended to remain the final queue backend.

- corpus-intake.toml — raw source material waiting for snapshot creation.
- corpus-analysis.toml — snapshots waiting for segmentation/tokenization/statistics.
- lexical-candidates.toml — aggregated unresolved lexical work discovered from corpora.
- lexical-enrichment.toml — integrated lexemes waiting for richer linguistic data.
- alignment.toml — spans/entities waiting for cross-language correspondence work.
- review.toml — proposed semantic analyses requiring adjudication.
- correction.toml — accepted entities that must be repaired while preserving lineage.

Do not create one GitHub issue per record.

A future database migration may import these records while preserving stable IDs and lineage.
