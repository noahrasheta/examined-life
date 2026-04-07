# Know Thyself Profile — Output Schema

The living self-profile that accumulates over time. Unlike session outputs (which are snapshots), the Know Thyself Profile is a single document that is updated — not rewritten — as new sessions add data. It lives in `vault/profiles/know-thyself-profile.md`.

---

## Template

```markdown
---
last-updated: {{YYYY-MM-DD}}
sessions-incorporated: {{number}}
---

# Know Thyself Profile

*This is a living document. It grows and changes as you examine your life. Nothing here is permanent or final — it reflects what has been surfaced so far.*

## Core Recurring Beliefs

{{Beliefs that have appeared across multiple sessions, labeled as skillful or unskillful. "Skillful" and "unskillful" are not judgments — they describe whether the belief tends to produce outcomes the user wants.}}

### Unskillful

{{Beliefs that consistently produce suffering, friction, or unwanted outcomes.}}

- **"{{Belief}}"** — First surfaced: [[session]]. Appeared in {{N}} sessions. {{Brief note on how it manifests.}}

### Skillful

{{Beliefs that support clarity, connection, or chosen outcomes.}}

- **"{{Belief}}"** — First surfaced: [[session]]. {{Brief note.}}

### Under Examination

{{Beliefs the user is actively investigating — not yet clear whether skillful or unskillful.}}

- **"{{Belief}}"** — Surfaced: [[session]]. Currently testing via [[experiment]].

## Habitual Reactive Patterns

{{Repeated behavioral sequences that show up across different situations. Each pattern is a compressed loop: trigger → reaction → consequence.}}

### {{Pattern name}}

- **Trigger:** {{What typically activates this pattern}}
- **Reaction:** {{What the user typically does}}
- **Consequence:** {{What typically results}}
- **Frequency:** {{How often this has appeared in sessions}}
- **Sessions:** [[session1]], [[session2]], ...

## Communication Style Observations

{{Patterns in how the user communicates, drawn from Communication Mirror sessions and from language patterns across all sessions.}}

- {{Observation — e.g., "Tends to over-explain when feeling defensive"}}
- {{Observation — e.g., "Uses humor to deflect from vulnerability"}}
- {{Observation}}

## Growth Markers

{{Evidence of change over time. Beliefs that have weakened or shifted. Patterns that have been interrupted. New awareness that didn't exist at the start.}}

- **{{Date range}}:** {{What changed and evidence for it}}

## Blind Spots

{{Areas the tool has flagged but the user hasn't yet explored. These are invitations for future work, not accusations.}}

- {{Blind spot — hedged, with the session where it was noticed: "Flagged in [[session]]: ..."}}

## Experiments Log

{{Summary of experiments tried, outcomes, and what was learned.}}

| Experiment | Date | Status | What Was Learned |
|---|---|---|---|
| [[experiment]] | {{date}} | {{status}} | {{brief outcome}} |
```

---

## Update Rules

- **Additive by default.** New observations are added, not substituted. If a belief was recorded in April and is still present in July, both the original entry and the update should be visible.
- **Growth is documented, not assumed.** Only move a belief from "Unskillful" to "Under Examination" or remove it when there is session evidence supporting the change.
- **The user approves updates.** Before modifying the profile, the tool proposes the change and the user accepts, rejects, or modifies it.
- **Timestamps matter.** Each entry should indicate when it was first surfaced and when it was last confirmed or updated.
- **Don't prune too eagerly.** A belief that hasn't appeared in recent sessions isn't necessarily gone. It may just not have been triggered. Keep it unless the user explicitly says it no longer applies.
- **Blind spots rotate.** As the user explores a blind spot, it moves out of this section and becomes either a belief, a pattern, or a growth marker. New blind spots take its place.
