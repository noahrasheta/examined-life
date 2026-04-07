# examined-life

A portable AI framework that helps you walk the cognitive cycle on your own life and see the loops you're stuck in.

---

**This tool is not therapy.** It is not a substitute for professional mental health support. It does not diagnose, treat, or prescribe. It is a structured self-reflection tool that asks you questions to help you see your own patterns more clearly. If you are in crisis, please contact the [988 Suicide & Crisis Lifeline](https://988lifeline.org/) (call or text 988), [Crisis Text Line](https://www.crisistextline.org/) (text HOME to 741741), or your local emergency services.

---

## What it is

`examined-life` is an open-source, local-first framework for AI-guided self-inquiry. It installs into the AI coding agent you already use — Claude Code, Cursor, Codex, OpenCode — and turns it into a Socratic mirror that walks you around your own cognitive cycle.

Sessions write structured markdown to a vault you own. Over time, the tool builds a living map of your recurring beliefs, patterns, and blind spots. The repo ships a portable specification (the cognitive cycle, mode templates, a questioning library, output schemas, and safety rails) plus thin platform adapters. The substance is the spec. The implementations are commodity.

## The north star

> The goal is not to tell people who they are. The goal is to help them see what they're doing clearly enough to choose differently.

## Quick start

### Claude Code

1. Clone this repo
2. Install as a plugin: `claude plugin add /path/to/examined-life`
3. Run `/examine` to start a Pattern Finder session
4. Run `/examine situation`, `/examine belief`, `/examine mirror`, `/examine life`, or `/examine review` for other modes

The repo is structured as a Claude Code plugin with the skill at `skills/examine/SKILL.md`. The skill auto-discovers and loads the framework files from `framework/`.

### Cursor

1. Copy `platforms/cursor/.cursorrules` to your project root
2. Ask Cursor to "examine" a pattern, situation, or belief

### Codex / OpenCode

1. Copy the relevant `AGENTS.md` from `platforms/` to your project root
2. Ask the agent to "examine" what you'd like to explore

## How it works

The framework is built around the **cognitive cycle** — a causal loop describing how your inner life produces your outer life:

**Beliefs** -> Perceptions -> Thoughts -> Emotions -> Feelings -> Decisions -> Actions -> Behaviors -> Consequences -> Experiences -> **(back to Beliefs)**

You can enter the cycle at any point. The tool walks you backwards to surface the driving belief, then forwards to map the full loop. Once you see the complete machinery, you can choose to intervene — usually with a small experiment that tests the belief at one point on the cycle.

## Modes

| Mode | What it does | When to use it |
|---|---|---|
| **Pattern Finder** | Walks the cycle on a recurring friction to surface the belief, the loop, and an experiment | "I keep doing this thing..." |
| **Situation Examiner** | Walks the cycle for a specific event or conversation | "This thing happened today..." |
| **Belief Excavator** | Deep examination of a single core belief — evidence, cost, alternatives | "I think I believe that..." |
| **Communication Mirror** | Reflects back patterns in a message or conversation without judgment | "Look at this message I wrote..." |
| **Life Review** | Wider examination of values, roles, narratives, and identity tensions | Monthly or quarterly zoom-out |
| **Review** | Cross-session synthesis — surfaces recurring patterns across all prior sessions | After 3+ sessions |

## Where your data lives

Everything you share stays on your machine. Session outputs are written to the `vault/` directory as plain markdown files with YAML frontmatter. The vault is gitignored by default. No telemetry, no analytics, no data sent anywhere. You own your data completely.

The vault uses Obsidian-friendly conventions (wikilinks, frontmatter) but has no Obsidian dependency. Any markdown editor works.

## What it draws from

The questioning approach blends three traditions:

- **Socratic questioning** — guided discovery, not directive answers
- **Motivational Interviewing** — evoking your own motivation and insight
- **Dharma-informed inquiry** — compassionate honesty drawn from contemplative practice

## What it does NOT do

- Diagnose mental health conditions
- Prescribe treatment or medication
- Act as a substitute for therapy
- Tell you what to do
- Analyze other people
- Flatter you

## Philosophy

A mirror that flatters is worse than no mirror. This tool reflects; you conclude. Observations are proposed with hedged language ("one possible pattern..." not "your pattern is...") and you approve, reject, or refine them before anything is saved.

The loop is the product. The cognitive cycle is not a feature — it is the architecture. Everything the tool does is some way of helping you enter, walk, and recognize your own loops.

## Project structure

```
examined-life/
├── .claude-plugin/             # Claude Code plugin manifest
│   └── plugin.json
├── skills/                     # Claude Code skill (primary adapter)
│   └── examine/
│       └── SKILL.md
├── framework/                  # The portable core — plain markdown
│   ├── cognitive-cycle.md      # The cycle specification
│   ├── modes/                  # Mode-specific instructions
│   ├── questioning-library.md  # Question bank
│   ├── output-schemas/         # Output templates
│   ├── safety-rails.md         # Crisis detection and guardrails
│   └── vault-conventions.md    # File naming and formatting
├── platforms/                  # Thin adapters for other AI agents
│   ├── cursor/
│   ├── codex/
│   └── opencode/
├── examples/                   # Anonymized example outputs
└── vault/                      # Your private data (gitignored)
```

## License

MIT. See [LICENSE](LICENSE).

## Author

Noah Rasheta — [Secular Buddhism Podcast](https://secularbuddhism.com)
