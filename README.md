# My Claude Code Setup

Personal Claude Code configuration — CLAUDE.md, MCP servers, and notes on what's worth installing. Public so anyone can grab the workflow as-is.

## What's in here
- `Learning_Claude.md` — global CLAUDE.md for everyday, learning-focused coding
- `MCP.md` — the MCP servers I actually use, and why

## Which CLAUDE.md should you use?

If you're a junior dev who wants to actually *understand* the code Claude writes, not just ship it, use `Learning_Claude.md`. It explains the "why" before writing code, defines patterns and technical terms before applying them, and walks through logic and data flow step by step — that's how I use it day to day.

If you just want to code fast through the CLI with solid engineering discipline and don't need the teaching layer, use Andrej Karpathy's CLAUDE.md instead:
**https://github.com/multica-ai/andrej-karpathy-skills**

It's just 4 short rules — think before coding, simplicity first, surgical changes, goal-driven execution — built to fix the most common LLM coding mistakes (silent assumptions, over-engineering, unrelated refactors), with zero pedagogy overhead.

`Learning_Claude.md` is actually a merge of those same 4 rules with my own junior-developer preferences layered on top (step-by-step guidance, explaining patterns/data flow, French communication, code style). Same discipline as Karpathy's, plus the teaching layer.

## Superpowers (optional)

**https://github.com/obra/superpowers**

A plugin that installs 14 skills, turning Claude Code into something closer to a senior dev workflow: brainstorm → spec → plan → TDD → review → finalize. It enforces writing tests before code and breaks work into checkpoints instead of one big leap.

Worth it for real features or new projects where there's genuine ambiguity about what "done" looks like. Skip it for trivial tasks (typo fixes, small tweaks) — the planning overhead isn't worth it there.

```bash
/plugin marketplace add obra/superpowers-marketplace
/plugin install superpowers@superpowers-marketplace
```
