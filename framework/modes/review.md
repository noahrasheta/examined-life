# Review

The cross-session synthesizer. Review reads all prior outputs in the vault and surfaces recurring beliefs, patterns, and loops that aren't visible from inside any single session. This is the sleeper feature — the thing that makes the system matter beyond what a single conversation with an AI can provide.

---

## When to use

- After 3 or more sessions in the vault (minimum for meaningful synthesis)
- The user asks for a review: "Let's review my patterns" or `/examine review`
- Periodically (monthly recommended, but user's choice)
- When the user says: "What patterns are you seeing?" or "What's recurring?"

---

## Session Flow

### 1. Read the vault

Read all session outputs in `vault/sessions/`, `vault/experiments/`, and `vault/profiles/`. Parse frontmatter for structure. Read the full content for substance.

Catalog:
- All core beliefs surfaced across sessions
- All entry points used
- All modes used
- All experiments and their outcomes
- The current state of the Know Thyself Profile

### 2. Identify recurring beliefs

A belief is "recurring" if it appears in 2+ sessions. Rank by frequency. For each recurring belief:
- Count how many sessions it appeared in
- Note which situations triggered it
- Assess the trend: Is this belief getting examined more (possibly weakening) or showing up unchallenged (stable/strengthening)?
- Note if the user's language around this belief has changed over time

### 3. Identify recurring patterns

Patterns are behavioral or emotional sequences that repeat. They're distinct from beliefs — a pattern is the cycle path, while a belief is a single node. Look for:
- Common loop shapes (e.g., "Belief about unworthiness → Perception of rejection → Withdrawal → Isolation → Confirmed unworthiness")
- Common entry points (does the user consistently enter through Emotions? Through Actions?)
- Common avoidance points (does the user consistently resist going to a certain node?)

### 4. Surface themes

Higher-level patterns that emerge from the aggregate. Not specific beliefs or loops, but gravitational centers:
- "Most of your sessions involve some form of conflict avoidance"
- "The relationship between worthiness and performance comes up in very different contexts"
- "There's a tension between your desire for independence and your need for connection"

### 5. Note shifts and growth

Evidence of change. This matters — it shows the user the system is working:
- Beliefs that weakened or got relabeled from "fact" to "interpretation"
- Experiments that produced new evidence
- Sessions where the user caught themselves mid-loop
- Language changes: how the user talks about a pattern now vs. three weeks ago

### 6. Flag blind spots

Areas the tool notices but the user hasn't explored. This requires sensitivity:
- Topics the user consistently deflects from
- Emotions that never get named
- Cycle nodes the user consistently skips
- Relationships or roles that never come up despite being significant

Frame as invitations, not accusations: "I notice we haven't explored X. That might be worth a session sometime — or it might not be relevant."

### 7. Suggest directions

2-3 areas that seem worth examining in upcoming sessions. Based on:
- Recurring beliefs that haven't been excavated
- Patterns that keep showing up
- Blind spots that feel important
- Experiments that produced interesting results and could be extended

### 8. Update the Know Thyself Profile

Review is a primary trigger for profile updates:
- Add newly confirmed recurring beliefs
- Update frequency counts
- Add new patterns
- Note growth markers
- Rotate blind spots

Propose all changes to the user before saving.

### 9. Write the output

Write a Pattern Ledger to `vault/reviews/` following the output schema.

---

## Session Guidance

- **This mode is more analytical than others.** The user expects synthesis, not exploration. But still ground the analysis in their own words and specific sessions.
- **Show your work.** When you claim a pattern recurs, cite the sessions. When you say a belief is weakening, point to the evidence.
- **Don't over-pattern.** Not everything is a pattern. Two sessions about work stress might just be two stressful weeks, not a deep pattern. Use judgment.
- **Minimum data thresholds:**
  - A "recurring belief" needs 2+ appearances
  - A "trend" needs 3+ data points
  - A "growth marker" needs before/after evidence
  - With fewer data points, say so: "Only two sessions so far — too early for confident pattern detection"
- **This is the "oh" moment.** The Review should show the user something they couldn't see from inside any single session. If it's just a summary of what they already know, it's not doing its job.
- **End with an invitation.** "Based on what's here, what do you want to explore next?"

---

## Handling Small Vaults

If the vault has fewer than 3 sessions:
- Acknowledge it: "There isn't enough data yet for a full pattern review."
- Offer what you can: summarize what's been surfaced so far
- Suggest continuing with more sessions before the next review
- Do not fabricate patterns from insufficient data

---

## References

- [[cognitive-cycle]] — The cycle spec
- [[pattern-ledger]] — Output schema
- [[know-thyself-profile]] — The living self-profile
- [[vault-conventions]] — Where things live
- [[safety-rails]] — Crisis detection and scope limits
