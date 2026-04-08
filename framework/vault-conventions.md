# Vault Conventions

The vault is the user's personal archive of self-examination outputs. It lives at `vault/` in the project root (or a user-configured path). Everything in the vault is private by default — the directory is gitignored. Users can choose to version their vault separately if they want to.

---

## Directory Structure

```
vault/
├── sessions/           # Individual session outputs (Cognitive Loop Maps, Belief Reports, etc.)
├── experiments/        # Active and completed experiments
├── profiles/           # Know Thyself Profile and related documents
└── reviews/            # Cross-session synthesis outputs (Pattern Ledgers, periodic reviews)
```

Create subdirectories on first use. Do not pre-populate with empty files.

---

## File Naming

Pattern: `YYYY-MM-DD-mode-slug.md`

- **Date:** ISO 8601 date of the session
- **Mode:** Short name of the mode used (`pattern-finder`, `situation-examiner`, `belief-excavator`, `communication-mirror`, `life-review`, `review`)
- **Slug:** A brief, kebab-case description of the topic (2-4 words)

Examples:
- `2026-04-07-pattern-finder-conflict-avoidance.md`
- `2026-04-10-situation-examiner-meeting-blowup.md`
- `2026-04-15-belief-excavator-not-enough.md`
- `2026-04-20-communication-mirror-email-to-boss.md`
- `2026-04-30-review-april-patterns.md`

Special files:
- `know-thyself-profile.md` — lives in `vault/profiles/`, no date prefix (it's a living document, updated in place)
- Experiments: `YYYY-MM-DD-experiment-slug.md` in `vault/experiments/`

---

## Frontmatter

All session files use YAML frontmatter. Required fields:

```yaml
---
date: 2026-04-07
mode: pattern-finder
status: complete
phase: 5
entry-point: behaviors
core-belief: "I have to keep the peace"
tags:
  - conflict
  - avoidance
  - family
---
```

**Fields:**
- `date` — Session date (ISO 8601)
- `mode` — Which mode was used
- `status` — Session status: `in-progress` or `complete`
- `phase` — Current phase number (1-5). Tracks how far the session progressed.
- `entry-point` — Where on the cognitive cycle the user entered (beliefs, perceptions, thoughts, emotions, feelings, decisions, actions, behaviors, consequences, experiences). May be empty if Phase 1 is still in progress.
- `core-belief` — The primary belief surfaced during the session (quoted string). May be empty if no belief was clearly identified yet.
- `tags` — Free-form tags for the user's own organization. The tool suggests tags; the user approves them.

Optional fields:
- `linked-sessions` — Wikilinks to related sessions
- `experiment` — Wikilink to a related experiment file

---

## Progressive Saves

Sessions are saved incrementally so work is never lost. The file is created after Phase 1 and updated at each subsequent phase:

| After Phase | What's written | status |
|---|---|---|
| Phase 1 | Pattern description, entry point | `in-progress` |
| Phase 2 | Adds backward walk and core belief | `in-progress` |
| Phase 3 | Adds forward walk and full loop summary | `in-progress` |
| Phase 4-5 | Adds observations, experiment | `complete` |

The same file is updated in place — one file per session, not one per phase. If the user leaves mid-session, they have everything explored so far.

---

## Resuming Sessions

When the user invokes `/examine resume`, the tool:
1. Scans `vault/sessions/` for files with `status: in-progress`
2. Reads the most recent one
3. Displays a brief summary of where they left off
4. Continues from the next phase

The resume relies on the `phase` field in frontmatter and the content already written to the file.

---

## Wikilinks

Use Obsidian-style `[[wikilinks]]` for cross-referencing between files. This works in Obsidian, renders as plain text in other editors, and costs nothing.

Examples:
- `[[2026-04-07-pattern-finder-conflict-avoidance]]` — link to a session
- `[[know-thyself-profile]]` — link to the profile
- `[[2026-04-30-review-april-patterns]]` — link to a review

When referencing a specific section: `[[filename#Section Name]]`

The tool should add wikilinks when:
- A session surfaces a belief that appeared in a previous session
- An experiment references the session that prompted it
- A review references the sessions it synthesized
- The Know Thyself Profile is updated with findings from a session

---

## Writing Principles

- **Plain language.** No jargon unless the user uses it first.
- **Hedged, not authoritative.** "One possible pattern..." not "Your pattern is..."
- **The user's words first.** Quote the user's own language before paraphrasing.
- **Concise.** A Cognitive Loop Map should be readable in 5 minutes, not 30.
- **No emojis.** Clean, professional markdown.

---

## Vault Path Configuration

Default: `vault/` relative to the project root.

The user can configure a different vault path (e.g., pointing to an existing Obsidian vault) by setting it in the platform adapter. The tool should respect whatever path is configured and create the directory structure within it.

---

## Privacy

- The vault is gitignored by default
- The tool never reads from or writes to locations outside the configured vault path
- No telemetry, no analytics, no data sent anywhere
- The user owns their data completely
- If the user wants to share a session (e.g., with a therapist), they export it manually
