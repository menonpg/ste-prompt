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

### Claude Code

**Slash command** — copy `claude/commands/ste.md` into `.claude/commands/` in
your project (or `~/.claude/commands/` for all projects):

```
/ste            rewrite the previous answer in Simplified Technical English
/ste <text>     rewrite the given text in STE
```

**Output style (persistent)** — copy `claude/output-styles/ste.md` into
`.claude/output-styles/` and select it with `/output-style`. The agent then
writes every explanation in STE by default.

### Codex / other agents

Copy the contents of `AGENTS.ste.md` into your repo's `AGENTS.md`. The behavior
travels with the repo.

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
