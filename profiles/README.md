# Profiles

Profiles contain learner-specific declarative state and schema fixtures.

The initial product supports one local profile: profiles/default/.

Do not store objective linguistic facts here.

Stable preferences and explicit language priorities may be repository-declared. High-frequency operational state such as every review event, reading position, and changing SRS schedule belongs in the application database once implemented.

The profile boundary exists for ontology hygiene and portability, not because Linguarium is currently a multitenant service.
