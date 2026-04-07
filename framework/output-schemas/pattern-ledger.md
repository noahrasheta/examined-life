# Pattern Ledger — Output Schema

The output of the Review mode's cross-session synthesis. A Pattern Ledger aggregates recurring beliefs, patterns, and themes across all session outputs in the vault.

---

## Template

```markdown
---
date: {{YYYY-MM-DD}}
mode: review
period: {{date range covered, e.g., "2026-04-01 to 2026-04-30"}}
sessions-analyzed: {{number}}
tags:
  - review
  - synthesis
---

# Pattern Ledger: {{Period description, e.g., "April 2026"}}

## Sessions Reviewed

{{List of sessions analyzed, with wikilinks.}}

- [[{{session 1}}]]
- [[{{session 2}}]]
- ...

## Recurring Beliefs

{{Beliefs that appeared in multiple sessions, ranked by frequency. For each:}}

### "{{Belief, in the user's words}}"

- **Frequency:** Appeared in {{N}} of {{total}} sessions
- **Sessions:** [[session1]], [[session2]], ...
- **Trend:** {{Strengthening / Stable / Weakening / Newly surfaced}}
- **Related cycle nodes:** {{Which nodes this belief most commonly activates}}
- **Notes:** {{Any observations about how this belief manifests differently across situations}}

## Recurring Patterns

{{Behavioral or emotional patterns that repeat across sessions, distinct from specific beliefs.}}

### {{Pattern name, e.g., "Conflict avoidance loop"}}

- **Description:** {{Brief description of the pattern}}
- **Appears in:** [[session1]], [[session2]], ...
- **Typical cycle path:** {{e.g., "Belief → Perception → Emotion → Avoidance → Relief → Reinforcement"}}
- **Variations:** {{How the pattern shows up differently in different contexts}}

## Themes

{{Higher-level themes that emerge from the aggregate. Not specific beliefs or patterns, but the gravitational centers of the user's inner work.}}

- **{{Theme}}:** {{Description and which sessions/beliefs cluster here}}

## Shifts and Growth

{{Evidence of change over the review period. Beliefs that weakened, experiments that produced results, new awareness that didn't exist before.}}

- {{Observation about change}}

## Blind Spots

{{Areas the tool notices but the user hasn't explored yet. Patterns in what the user avoids examining, what they deflect from, or where their curiosity consistently stops.}}

- {{Blind spot observation — hedged, compassionate, and flagged for future exploration, not asserted as fact}}

## Suggested Directions

{{2-3 areas that seem worth examining in upcoming sessions. Not prescriptions — invitations.}}

1. {{Direction and why it seems worth exploring}}
2. {{Direction}}
```

---

## Guidelines

- The Pattern Ledger is a synthesis, not a summary. It should surface things that aren't visible in any single session.
- Frequency counts should be honest. If a belief appeared once, don't inflate it.
- Trends require at least 3 data points to claim directionality. With fewer, say "insufficient data to determine trend."
- Blind spots are the most valuable and most sensitive part. Flag them gently. "I notice we haven't explored..." not "You're avoiding..."
- Shifts and Growth should be grounded in evidence. Don't claim growth that isn't demonstrated in the sessions.
- This document should make the user go "oh" — showing them something they couldn't see from inside any single session.
