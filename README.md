# STE-Prompt

**Simplified Technical English (ASD-STE100) for your coding agent.**

STE-Prompt makes Claude Code, Codex, and other agents write explanations,
runbooks, and procedures in **Simplified Technical English** — the controlled
language the aerospace and defence industry has used for decades to make
maintenance manuals unambiguous.

Short sentences. One idea each. Active voice. A controlled vocabulary where
every approved word has one meaning. The result is output you can scan fast and
misread rarely.

## Why

LLM prose hides ambiguity in two places: hedging ("this might potentially
help") and compound sentences that pack three claims into one. STE removes both
mechanically. It is a rule-based style, so a model can actually follow it.

Use it for procedures, runbooks, agent step logs, and API how-tos. Do **not**
use it for nuance, risk discussion, or research summaries — there, the hedging
is the content.

## Install

### Claude Code (plugin — recommended)

This repo is a Claude Code plugin **and** a one-plugin marketplace. Install it
straight from GitHub:

```
/plugin marketplace add menonpg/ste-prompt
/plugin install ste-prompt@menonlab
```

That gives you:

- the `/ste` **slash command** (rewrite a block on demand),
- a **`simplified-technical-english` skill** the agent invokes automatically
  when you ask for STE / clearer procedures,
- the full rule set and dictionary as reference.

Then:

```
/ste            rewrite the previous answer in Simplified Technical English
/ste <text>     rewrite the given text in STE
```

### Claude Code (manual, no plugin)

Copy `claude/commands/ste.md` into `.claude/commands/` (project) or
`~/.claude/commands/` (global). For a persistent style, copy
`claude/output-styles/ste.md` into `.claude/output-styles/` and select it with
`/output-style`.

### Codex / other agents

STE-Prompt works in Codex too — Codex doesn't use Claude's plugin format, so you
install it as agent instructions instead. Two options:

**Option 1 — `AGENTS.md` (recommended).** Codex automatically reads `AGENTS.md`
from the repo root (and `~/.codex/AGENTS.md` for all projects). Append our rules:

```bash
# per-project
cat AGENTS.ste.md >> AGENTS.md

# or global, for every Codex session
mkdir -p ~/.codex && cat AGENTS.ste.md >> ~/.codex/AGENTS.md
```

The agent then writes explanations, runbooks, and procedures in Simplified
Technical English by default. The behavior travels with the repo.

**Option 2 — on-demand prompt.** Paste `AGENTS.ste.md` (or `RULES.md`) into any
Codex / ChatGPT / Gemini / Cursor chat and say *"rewrite the above in Simplified
Technical English using these rules."* No install needed — it's just a prompt.

The same `AGENTS.md` drop-in works for any agent that reads an `AGENTS.md`
convention (Cursor, Cline, Aider, Windsurf, OpenClaw, etc.).

## The rules (condensed)

See [`RULES.md`](./RULES.md) for the full set and
[`DICTIONARY.md`](./DICTIONARY.md) for approved-verb substitutions.

1. Keep procedural sentences to **20 words or fewer**; descriptive to 25.
2. **One instruction per sentence.**
3. Use the **active voice**.
4. Use the **present tense** for procedures.
5. Start an instruction with the **command verb** ("Remove the bolt.").
6. Use **articles** ("the file," not "file").
7. Do not use a **noun as a verb**.
8. Use only **approved words** — one meaning per word (see DICTIONARY.md).
9. Write **one topic per paragraph**; lead with the topic sentence.
10. Use a **vertical list** for more than three conditions or steps.

## License

MIT. Borrowed from aerospace, where a misread sentence has consequences.

ASD-STE100 is a trademark of ASD (AeroSpace and Defence Industries Association
of Europe). This project reproduces none of the Specification text; it provides
original guidance inspired by the public description of the standard.

## Also check out

**[MotionStudio](https://github.com/menonpg/motionstudio)** — another Menon Lab
plugin for Claude Code & Codex. Turns a topic into a finished, rendered explainer
video (script, storyboard, motion, sound, captions) via a deterministic
HTML-to-MP4 pipeline. [motion.themenonlab.com](https://motion.themenonlab.com)
