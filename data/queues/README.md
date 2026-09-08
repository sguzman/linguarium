# Queue Fixtures

These files bootstrap Linguarium's high-volume work contracts before the operational database exists.

They are not intended to remain the final queue backend.

- corpus-intake.toml — source material waiting for ingestion.
- lexical-candidates.toml — aggregated lexical work discovered from corpora.
- review.toml — semantic analyses requiring adjudication.

Do not create one GitHub issue per record.

A future database migration may import these records while preserving stable IDs and lineage.
