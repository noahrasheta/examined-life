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

**Prerequisite:** [Claude Code](https://docs.anthropic.com/en/docs/claude-code) must be installed.

**Install from GitHub (recommended):**

```bash
# Step 1: Add the repo as a marketplace
claude plugin marketplace add noahrasheta/examined-life

# Step 2: Install the plugin
claude plugin install examined-life
```

To install globally (available in all projects):

```bash
claude plugin marketplace add noahrasheta/examined-life
claude plugin install examined-life --global
```

**Verify it worked:** Open Claude Code and type `/`. You should see `examined-life:examine` in the list of available skills. (Claude Code namespaces plugin skills as `plugin-name:skill-name`.)

**Start a session:**

- `/examine` — Pattern Finder (default)
- `/examine situation` — explore a specific event
- `/examine belief` — examine a core belief
- `/examine mirror` — reflect on a message or conversation
- `/examine life` — wide-angle life review
- `/examine review` — synthesize patterns across past sessions
- `/examine resume` — pick up an unfinished session where you left off

**Pausing and resuming:** Sessions save progressively — after each phase of the cognitive cycle, your progress is written to the vault. You can close the terminal at any time without losing work. When you're ready to continue, run `/examine resume` and the tool will pick up where you left off.

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

Sessions save progressively as you work through the cognitive cycle. Each phase checkpoint updates your session file, so you never lose progress — even if you close the terminal mid-session. Session files include a `status` field (`in-progress` or `complete`) and a `phase` number so the tool knows exactly where you left off.

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
├── skills/                     # Claude Code skill
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

[Noah Rasheta](https://noahrasheta.com) — [Eightfold Path (Secular Buddhism Podcast)](https://eightfoldpath.com)

To learn more about the cognitive cycle, check out [the podcast episode](https://eightfoldpath.com/sbp/episode-188) where Noah explains the framework, or explore the [Inner Peace Roadmap course](https://eightfoldpath.com/courses/inner-peace-roadmap) for the full curriculum.
