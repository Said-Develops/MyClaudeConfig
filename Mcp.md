# MCP Servers

MCP (Model Context Protocol) is a standard that lets Claude connect to external tools and data sources — GitHub, databases, documentation, browsers, and more. Each MCP server exposes a set of tools that Claude can call automatically when relevant to the task at hand.

Browse the most used MCP servers here: https://mcp.directory/

## A note on native tools

Many things MCP servers used to provide are now built natively into Claude Code: file read/write, web search, web fetch, and persistent memory (Auto Memory) all work out of the box, no server needed. Before installing an MCP server, check if Claude Code already covers it natively — adding servers for no reason just adds context overhead and attack surface.

## What I actually use

### Context7
Injects up-to-date, version-specific library/API documentation directly into the context. Native WebFetch exists, but it's lossy (summarized by a small model) and not version-pinned to what's actually installed in the project. Context7 fixes both.

```bash
claude mcp add --transport http context7 https://mcp.context7.com/mcp
```

Auto-invoke rule (added to CLAUDE.md, so I don't have to type "use context7" every time):
```markdown
Always use Context7 MCP when I need library/API documentation,
code generation, setup or configuration steps, without me having
to explicitly ask.
```

### Playwright
Lets Claude control a real browser (navigate, click, fill forms, read the page) via structured accessibility snapshots — no native equivalent exists in Claude Code, since it has no browser control at all. Useful for verifying UI changes render correctly and for end-to-end testing without writing test scripts by hand.

```bash
claude mcp add playwright -- npx @playwright/mcp@latest
```

## Everything else
Skipped for now — Bash + native tools (gh CLI, WebFetch, WebSearch) already cover most other common use cases (GitHub, file ops, memory, structured reasoning). Add a new server only when a real, specific need comes up.
