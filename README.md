![Mikael — Behavioral Framework](./banner.svg)

# mikael-3.3-co-behavior

> What if your agent had the behavioral discipline of Claude Opus 4.7 — search-first, copyright-aware, tool-routing logic — as a reusable skill?

A behavioral framework for AI agents, adapted from the patterns I observed inside Claude Opus 4.7's system prompt.

## The idea

I spent time reverse-engineering how top-tier models behave internally — not just *what* they say, but *how* they decide to say it. When to search vs. answer from memory. When to create a file vs. respond inline. How to handle copyright without breaking flow. How to route between tools without narrating the decision.

These aren't magic. They're **engineering patterns**. And they're transferable.

So I extracted the principles, restructured them in my own format, and packaged them as a skill that any agent in the open skills ecosystem can install.

## What you get

| Capability | Before | After |
|------------|--------|-------|
| **Search discipline** | Guesses from training data | Searches before every present-day factual question |
| **Copyright** | Quotes freely, risks reproduction | 15-word max per quote, one per source, paraphrase-first |
| **Tool routing** | Picks tools randomly or narrates the choice | Clear decision tree: MCP → file → visualizer → inline |
| **File creation** | Creates files for everything or nothing | Concrete triggers: blog post → file, explanation → inline |
| **Tone** | Over-formatted, bullet-heavy, robotic | Natural prose, minimal formatting, concise |
| **Safety** | Inconsistent boundaries | Structured child safety, mental health, harmful content filters |

## Quick install

```bash
npx skills add domfelipe/mikael-3.3-co-behavior
```

That's it. The agent picks up the behavioral constraints on next load.

## What's inside

- **Core Behavior** — default stance, tone rules, refusal handling
- **Search Policy** — when to search, how to construct queries, scaling effort to complexity
- **Copyright Rules** — hard limits, paraphrase-first, content safety
- **File Handling** — creation triggers, directory structure, artifact criteria
- **Tool Routing** — decision trees for web_search, image_search, visualize, computer_use
- **Visualizer** — 4-step routing: visual needed → MCP fit → file request → inline widget
- **API Patterns** — Claudeception, MCP integration, context window management
- **Memory System** — conversation search cues, past chat retrieval

## Who is this for?

- **Agent builders** who want production-grade behavioral constraints without writing them from scratch
- **Prompt engineers** studying how top models handle tool routing, safety, and content creation
- **Developers** tired of agents that over-format, skip searches, or ignore copyright
- **Curious folks** who want to peek behind the curtain of how advanced agents are configured

## Design decisions

- **Adapted, not copied** — Inspired by Opus 4.7, but restructured and rewritten in my own format. The organization and emphasis reflect my own judgment.
- **Modular** — Each section is self-contained. Agents can reference specific modules without loading everything.
- **Practical** — Every rule maps to a concrete behavior. No abstract principles.

## Try it out

Install it, load it on your agent, and notice the difference in how it handles searches, files, and formatting. If something feels off or you have ideas for improvements, open an issue or PR — this is a living project.

## Disclaimer

This skill is inspired by publicly observable behavior from Claude Opus 4.7 but is my own adaptation. It is not affiliated with, endorsed by, or sourced directly from Anthropic. Some patterns may differ from the actual model configuration.
