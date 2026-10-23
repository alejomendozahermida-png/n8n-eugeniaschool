# Lenses for specs, plans and designs

A spec fails when two people can read it and build different things, or when it is silent about what happens when things go wrong. Read it as the developer who has to build it tomorrow with nobody to ask.

## Clarity
- Ambiguous words: "fast", "secure", "user-friendly", "soon", "as needed", "etc.". What number or test would settle each?
- Terms used in two senses; undefined roles, states or levels.
- Missing or untestable acceptance criteria: how will anyone know it is done?

## Consistency
- Contradictions between sections, between the spec and the examples, or between the goal and the constraints.
- Requirements that cannot both be true (for example "never auto-reply" and "reply within one minute").
- Numbers, names and flows that differ from one place to the next.

## Completeness
- The unhappy paths: invalid input, timeouts, duplicates, partial failure, the third-party service being down, the user abandoning halfway.
- Who handles exceptions, and how do they find out? Is there an owner for every escalation?
- Volumes and limits: how many items, how often, what happens at 10x?
- Permissions, privacy and legal constraints (personal data, consent, retention, deletion).
- Migration, rollback and what happens to existing data.
- Monitoring: how do you notice that it is broken?

## Assumptions
- List every unstated assumption (data exists, API stays free, users are honest, input is French, the model is deterministic). For each, say what breaks if it is false.
- Dependencies on people, accounts, keys or quotas that are not under the team's control.

## Scope and feasibility
- Scope creep or scope holes: things promised in the intro but absent from the body.
- Effort or timeline claims with no basis.
- Simpler alternatives that were not considered; features nobody asked for.

## Evidence to gather
Quote the sentences that conflict or are silent. State the question that the spec cannot answer, and propose the question to ask the author.
