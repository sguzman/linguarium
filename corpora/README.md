# Corpora

Corpora create demand for Linguarium's lexicon and ontology.

## Intake contract

A corpus contribution should provide, when known:
- language/variety;
- title;
- author/creator;
- source/provenance;
- raw text or a source that an authorized importer can materialize;
- optional notes about edition, translation, or intended use.

The principal should be able to hand the director a plain-text work and say, effectively, “add this corpus.” The director should turn that into a queue record rather than requiring the principal to manually prepare lexical data.

## Snapshot layout

A committed small corpus may eventually use:

~~~text
corpora/
  snapshots/
    <snapshot-id>/
      manifest.toml
      source.txt
~~~

The manifest should include a content hash and provenance.

Large corpora may later use external/local object storage coordinated by manifests. The architecture must preserve stable snapshot identity either way.

## Mutation rule

Never silently replace an annotated snapshot. Import a new snapshot/version and preserve lineage.
