---
name: mikael-3.3-co-behavior
description: Claude Opus 4.7 system prompt — complete behavioral instructions, safety guidelines, tool usage rules, copyright compliance, and computer use patterns for agentic coding workflows.
---

# Claude Opus 4.7 — System Behavior Reference

This skill contains the complete behavioral instructions and system prompt for Claude Opus 4.7. It serves as a reference for understanding how the model is configured, including safety guidelines, tool usage patterns, copyright rules, and computer use workflows.

## What's Included

### Core Behavior
- Search-first policy for present-day factual questions
- Default stance: help unless concrete serious harm risk
- Refusal handling and child safety protocols
- Legal/financial advice guardrails
- Tone and formatting preferences (prose over lists, minimal bold, no emojis unless asked)
- User wellbeing and mental health sensitivity

### Tool Usage
- **web_search**: When to search vs. answer from knowledge, query construction, scaling calls to complexity
- **web_fetch**: URL retrieval rules and copyright constraints
- **image_search**: When visuals add value, content safety filters, interleaving patterns
- **computer_use**: Linux container (Ubuntu 24) with bash, file creation/editing, skills system
- **visualize**: SVG/HTML inline widgets, design modules, trigger conditions
- **places_search / places_map_display**: Location-based recommendations and itineraries
- **weather_fetch**: Location-aware weather retrieval
- **sports_data**: Scores, standings, game stats via SportRadar
- **message_compose**: Strategic message drafting with multiple approaches
- **MCP registry**: Connector discovery and integration

### Copyright Compliance (Hard Limits)
- Maximum 15 words per direct quote
- One quote per source maximum
- Default to paraphrasing
- Never reproduce lyrics, poems, haikus, or article paragraphs
- Never reconstruct article structure

### Computer Use & File Handling
- User uploads: `/mnt/user-data/uploads`
- Working directory: `/home/claude`
- Final outputs: `/mnt/user-data/outputs`
- File creation triggers (blog posts → files, explanations → inline)
- Artifact usage criteria (when to create .md, .html, .jsx, .svg, .pdf)
- Package management (npm, pip with `--break-system-packages`)

### Skills System
- Read SKILL.md files before creating documents
- Core skills: docx, pdf, pptx, xlsx, frontend-design, file-reading, pdf-reading
- User skills take priority over public skills

### Knowledge & Cutoff
- Reliable knowledge cutoff: January 2026
- Current date: April 16, 2026
- Search for any present-day factual question regardless of confidence

### Past Chats & Memory
- `conversation_search` for topic-based lookup
- `recent_chats` for time-based lookup
- Recognize linguistic cues (possessives, definite articles, past-tense references)

### Visualizer Routing
- Step 0: Does it need a visual at all?
- Step 1: Is a connected MCP tool a fit?
- Step 2: Did the person ask for a file?
- Step 3: Visualizer (default inline visual)

### API in Artifacts (Claudeception)
- Standard Anthropic `/v1/messages` endpoint
- MCP server integration patterns
- Web search tool in artifacts
- Context window management and stateful applications

## Usage

Load this skill when you need to:
- Understand Claude Opus 4.7's behavioral constraints and capabilities
- Reference safety guidelines and copyright rules
- Study tool usage patterns and routing decisions
- Compare system prompt designs across model versions
- Build agents with similar behavioral profiles

## Notes

This is a reference document extracted from the Claude Opus 4.7 system prompt. It reflects the model's configuration as of the time of extraction and may not represent the most current version.
