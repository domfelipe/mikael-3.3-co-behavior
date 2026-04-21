# mikael-3.3-co-behavior

Claude Opus 4.7 system behavior reference skill.

## What is this?

This is the complete behavioral instruction set (system prompt) for **Claude Opus 4.7**, packaged as a modular skill for the open agent skills ecosystem.

It contains ~1,400 lines of behavioral instructions covering safety, tool usage, copyright compliance, computer use workflows, visualizer routing, and more.

## Why?

Understanding how top-tier models are configured internally is valuable for:
- **Agent builders** who want to replicate similar behavioral profiles
- **Prompt engineers** studying production-grade system prompt design
- **Researchers** comparing safety and capability configurations across models
- **Developers** who want reference patterns for tool routing, file handling, and content safety

## Installation

```bash
npx skills add felipedomingues/mikael-3.3-co-behavior
```

Or manually clone this repo into your skills directory:

```bash
git clone https://github.com/felipedomingues/mikael-3.3-co-behavior.git ~/.agents/skills/mikael-3.3-co-behavior
```

## Contents

| Section | Description |
|---------|-------------|
| Core Behavior | Search-first policy, default stance, refusal handling, tone rules |
| Tool Usage | web_search, web_fetch, image_search, computer_use, visualize, and more |
| Copyright | Hard limits: 15-word quotes, one quote per source, paraphrase-first |
| File Handling | Upload/working/output directories, artifact triggers, package management |
| Skills System | How skills are discovered, loaded, and prioritized |
| Visualizer | 4-step routing: visual needed → MCP fit → file request → Visualizer |
| API in Artifacts | Claudeception patterns, MCP integration, context management |
| Past Chats | Memory system, conversation search, cue recognition |

## License

This is a reference extraction for educational and research purposes. The original system prompt is the property of Anthropic.

## Disclaimer

This skill is a reference document extracted from publicly observable model behavior. It is not an official Anthropic release and may not reflect the most current version of Claude's system prompt.
