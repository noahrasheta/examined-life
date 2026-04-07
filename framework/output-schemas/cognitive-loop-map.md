# Cognitive Loop Map — Output Schema

The primary output of Pattern Finder and Situation Examiner modes. A Cognitive Loop Map traces one complete walk around the cognitive cycle for a specific situation or recurring pattern.

---

## Template

```markdown
---
date: {{YYYY-MM-DD}}
mode: {{pattern-finder | situation-examiner}}
entry-point: {{cycle node where the user entered}}
core-belief: "{{the primary belief surfaced}}"
tags:
  - {{tag}}
linked-sessions:
  - "{{[[wikilink]]}}"
experiment: "{{[[wikilink to experiment]]}}"
---

# Cognitive Loop Map: {{Short title}}

## What brought this up

{{1-3 sentences. The user's own words about why they're here today. Quote directly where possible.}}

## The Loop

### Entry: {{Node name}}

{{Where the user entered the cycle. What they said or described that placed them here. Quote their language.}}

### Walking Back

{{For each node traced backwards from the entry point to Beliefs. Not every node needs to appear — only the ones that surfaced during the conversation. Each node gets:}}

#### {{Node name}}

{{What was surfaced at this node. Use the user's own language first, then the tool's reframing. Keep hedged: "One way to read this..." not "This is..."}}

### The Belief

{{The core belief at the root of this loop. Stated clearly but hedged. "The belief that seems to be operating here is something like: '...'" Quote the user's formulation if they named it.}}

### Walking Forward

{{For each node traced forward from the belief back to the entry point (or beyond). Same format as Walking Back.}}

#### {{Node name}}

{{What was surfaced.}}

### The Full Loop

{{A concise, 3-5 sentence summary of the complete cycle. "The belief that [X] leads you to perceive [Y], which generates thoughts of [Z], triggering [emotion], which drives you to [action], creating [consequence], which reinforces the belief that [X]."}}

### What I Noticed

{{2-4 observations from the tool. Hedged, compassionate, honest. Things the user might not have seen. Contradictions, blind spots, or patterns worth noting. Each observation is a separate bullet point.}}

## Experiment

{{A small, concrete experiment. See experiment.md schema. Include inline here as a summary, and optionally create a separate experiment file.}}

**Try this:** {{One sentence describing what to try.}}

**Notice:** {{What to pay attention to during the experiment.}}

**When:** {{When to try it — next time X happens, this week, etc.}}

**Report back:** {{Invitation to revisit. "Next time we talk, I'd be curious to hear what happened."}}
```

---

## Guidelines

- The map should be readable in 5 minutes. If it's longer than that, it's too detailed.
- Use the user's words first, the tool's reframing second.
- Not every cycle node needs to appear. Only include nodes that actually surfaced during the conversation.
- The "Walking Back" and "Walking Forward" sections trace the path from entry point, not the full 10-node cycle every time.
- The "What I Noticed" section is where the tool adds value beyond what the user already said. These observations must be hedged and must have been proposed to and accepted by the user during the session.
- The experiment should be small enough that it doesn't feel like homework. One thing to try. One thing to notice.
