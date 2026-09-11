# Evidence, decision, and human-input records

Agent-maintained. No research records exist yet. Add only material that supports continuity, auditability, or a conclusion. Use ID-only headings such as `## E001`, `## D001`, and `## H001`; put a descriptive title beneath the heading. Links then stay stable when descriptions change. From the project root use `[E001](evidence/RECORDS.md#e001)`; from `outputs/REPORT.md` use `[E001](../evidence/RECORDS.md#e001)`. Use the same link pattern for D and H records. These examples refer to a record you would create. Existing IDs must not be renamed or reused.

The formats below are templates, not findings. Adapt fields to the evidence; combine related facts instead of creating repetitive records. Remove this introductory guidance when it is no longer useful. If splitting records across topic files, keep this entry point and preserve existing links.

## Evidence record format

```markdown
## E001

**Short finding**

- Recorded: YYYY-MM-DD, with time and timezone when useful.
- Kind: observation | primary result | secondary statement | reproduced calculation | inference | assumption | hypothesis | speculation
- Finding: the claim or result, with scope and units when relevant.
- Provenance: author/organization, title, date/version, URL/DOI or local path; retrieval date for online sources; page/section/table/figure/data locator. For an inference, assumption, or hypothesis, identify its author and evidence or rationale instead of inventing an external source.
- Access / method: what was actually read, observed, or executed; any access limitation. For computation, link inputs, method, run instructions, and outputs.
- Bearing on the objective: what this supports or challenges; separate the source result from the agent's interpretation.
- Limitations / counterevidence: relevant uncertainty, dependencies on other evidence, contrary records, or untested assumptions.
```

Reuse provenance by linking an existing record for the same source and specifying the new locator. Do not count reuse of that source as corroboration. For a source-reported number, say whether it was independently checked. Add a correction or supersession link if a recorded claim changes; retain enough of the earlier record to explain the change.

## Decision record format

```markdown
## D001

**Short decision**

- Date: YYYY-MM-DD, with time and timezone when useful.
- Decision / change: the agent's adopted interpretation, rejected hypothesis, consequential assumption, or scope decision.
- Basis: concise justification, linking originating H records, relevant E records or artifacts, and any consequential contrary evidence as applicable. Separate human direction from evidential support.
- Consequence / reconsider when: what changes next, and which new evidence or input could reverse this decision.
```

## Human-input record format

```markdown
## H001

**Short description of consequential input**

- Timestamp: YYYY-MM-DD HH:MM timezone; identify as input time or capture time, noting uncertainty when the input time is unknown.
- Type: scope/objective change | constraint | priority | clarification | hypothesis | observation | authorization | stopping decision
- Human input: short exact quote when wording matters, otherwise a labeled paraphrase; identify origin (conversation instruction, brief section, or supplied material) and a locator if available.
- Agent interpretation: operational meaning, separate from the human's statement; note consequential ambiguity and what remains unverified.
- Effect on research state: changed scope, assumptions, priorities, permitted actions, queued work, or stopping status; link related H, D, E records or artifacts where useful.
```

Capture consequential input promptly, before dependent action or handoff, and link it from the applicable `STATE.md` fields. Group related points; do not create a D or E record merely to repeat H. Preserve authorization scope, limits, conditions, expiry, or revocation when stated. For changed or withdrawn input, add a new H record, link both records, and update state; mark only the affected points in the earlier record superseded or withdrawn without erasing its original content. Unaffected instructions remain applicable. Human-reported observations and hypotheses are not independently verified evidence: link any subsequent check in E back to H.

Do not store routine conversation, exhaustive transcripts, private reasoning, or unrelated personal detail. Record a failed avenue when it matters to the interpretation, prevents duplicated work, or supports the stopping rationale.
