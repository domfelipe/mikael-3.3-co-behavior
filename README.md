# mikael-3.3-co-behavior

A behavioral framework skill for AI agents — built from patterns observed in Claude Opus 4.7's system prompt.

## What is this?

This is a skill I developed by studying the behavioral patterns, safety rules, and tool-routing logic that power Claude Opus 4.7. Rather than copying the original prompt, I extracted the underlying principles and adapted them into a modular, installable skill that any agent in the open skills ecosystem can use.

The goal was to distill what makes a production-grade agent behave well — when to search vs. answer from memory, how to handle copyright, how to route between tools, when to create files vs. respond inline — and make those patterns reusable.

## Why I built this

I spent time analyzing how top-tier models are configured internally and noticed that many of their behavioral patterns are transferable. Things like:

- **Search-first discipline** — never answer present-day factual questions from training data
- **Copyright hard limits** — 15-word max per quote, one quote per source, paraphrase by default
- **Tool routing logic** — a clear decision tree for when to use which tool
- **File creation triggers** — concrete rules for when output belongs in a file vs. inline chat
- **Safety boundaries** — child safety, mental health, harmful content filters

These aren't unique to one model. They're good engineering practices for any agentic system. So I adapted them into a skill format that works across agents.

## Installation

```bash
npx skills add domfelipe/mikael-3.3-co-behavior
```

Or clone manually:

```bash
git clone https://github.com/domfelipe/mikael-3.3-co-behavior.git ~/.agents/skills/mikael-3.3-co-behavior
```

## What's covered

| Module | What it does |
|--------|-------------|
| Core Behavior | Default stance, tone rules, refusal handling, user wellbeing |
| Search Policy | When to search vs. answer from knowledge, query construction, scaling effort to complexity |
| Copyright Rules | Quotation limits, paraphrase-first, content safety filters |
| File Handling | When to create files, directory structure, artifact triggers |
| Tool Routing | Decision trees for web_search, image_search, visualize, computer_use |
| Visualizer | 4-step routing: visual needed → MCP fit → file request → inline widget |
| API Patterns | Claudeception, MCP integration, context window management |
| Memory System | Conversation search cues, past chat retrieval patterns |

## How it works

The skill uses frontmatter metadata that agents read before loading instructions. When activated, it injects behavioral constraints covering:

1. **Information retrieval** — search discipline, source quality, citation format
2. **Content creation** — file vs. inline decisions, artifact criteria, formatting rules
3. **Safety** — harm prevention, copyright compliance, content filters
4. **Tool selection** — priority ordering, category matching, fallback chains

## Design decisions

A few choices worth calling out:

- **Adapted, not copied** — The patterns are inspired by Opus 4.7 but restructured and rewritten in my own format. The organization, emphasis, and some rules reflect my own judgment about what matters.
- **Modular by design** — Each section is self-contained so agents can reference specific modules without loading the full prompt.
- **Practical over theoretical** — Every rule maps to a concrete behavior, not abstract principles.

## Disclaimer

This skill is inspired by publicly observable behavior from Claude Opus 4.7 but is my own adaptation. It is not affiliated with, endorsed by, or sourced directly from Anthropic. Some patterns may differ from the actual model configuration.
