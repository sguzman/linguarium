# Language Packs

Each directory under languages/ declares language- or variety-specific behavior for the shared Linguarium engine.

A minimal pack needs only a manifest. Richer packs may later add:
- orthography data;
- grammatical feature declarations;
- tokenizer/normalizer configuration;
- transliteration tables;
- source registries;
- language-specific ontology extensions;
- test fixtures.

Operational lexemes and learner knowledge do not live here merely because they belong to the language. Those remain in the shared operational store.
