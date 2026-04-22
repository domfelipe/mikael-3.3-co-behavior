<p align="center">
  <img src="./banner.svg" alt="MIKAEL" width="600" />
</p>

<p align="center">
  <strong>Behavioral discipline for AI agents — inspired by Claude Opus 4.7</strong>
</p>

<p align="center">
  <a href="https://github.com/domfelipe/mikael-3.3-co-behavior/stargazers">
    <img alt="Stars" src="https://img.shields.io/github/stars/domfelipe/mikael-3.3-co-behavior?style=flat&color=ffd700&labelColor=1a1a2e" />
  </a>
  <img alt="Lines" src="https://img.shields.io/badge/lines-1156-ffd700?style=flat&labelColor=1a1a2e" />
  <img alt="Modules" src="https://img.shields.io/badge/modules-11-ffd700?style=flat&labelColor=1a1a2e" />
  <img alt="Built with" src="https://img.shields.io/badge/built%20with-🇧🇷-ffd700?style=flat&labelColor=1a1a2e" />
</p>

<br/>

---

<br/>

## ✦ The Story

Most AI agents feel like they're guessing. They answer from training data when they should search. They create files for everything or nothing. They over-format, narrate their decisions, and ignore copyright.

I spent time reverse-engineering how **Claude Opus 4.7** behaves internally — not just *what* it says, but *how* it decides to say it. The patterns I found weren't magic. They were **engineering discipline**.

So I extracted them, restructured them in my own format, and built **Mikael** — a **1,156-line behavioral specification** that brings production-grade agent behavior to any system in the open skills ecosystem.

This isn't a summary. It's a working behavioral spec — every rule maps to a concrete decision the agent makes in real time.

<br/>

## ✦ What Changes

<table>
  <tr>
    <th width="33%" align="center">Before</th>
    <th width="33%" align="center"></th>
    <th width="33%" align="center">After</th>
  </tr>
  <tr>
    <td align="center">🎲 Guesses from training data</td>
    <td align="center">→</td>
    <td align="center">🔍 Searches before every factual question</td>
  </tr>
  <tr>
    <td align="center">📋 Over-formatted, bullet-heavy</td>
    <td align="center">→</td>
    <td align="center">✍️ Natural prose, minimal formatting</td>
  </tr>
  <tr>
    <td align="center">📁 Creates files for everything or nothing</td>
    <td align="center">→</td>
    <td align="center">📄 Concrete triggers: blog post → file, explanation → inline</td>
  </tr>
  <tr>
    <td align="center">⚖️ Ignores copyright boundaries</td>
    <td align="center">→</td>
    <td align="center">🛡️ 15-word max per quote, paraphrase-first</td>
  </tr>
  <tr>
    <td align="center">🔀 Picks tools randomly</td>
    <td align="center">→</td>
    <td align="center">🧭 Clear decision tree: MCP → file → visualizer → inline</td>
  </tr>
  <tr>
    <td align="center">🚫 Inconsistent safety boundaries</td>
    <td align="center">→</td>
    <td align="center">🧒 Structured child safety, mental health, content filters</td>
  </tr>
</table>

<br/>

---

<br/>

## ⚡ Quick Install

```bash
npx skills add domfelipe/mikael-3.3-co-behavior
```

That's it. Your agent picks up the behavioral constraints on next load.

<br/>

## 🌍 Works Everywhere

Mikael is a plain Markdown file with YAML frontmatter. It works with **any AI coding agent** that supports custom instructions, rules, or system prompts. No lock-in, no proprietary format.

### Installation by Platform

<details>
<summary><strong>🐙 OpenCode / npx skills</strong> — Recommended</summary>

```bash
npx skills add domfelipe/mikael-3.3-co-behavior
```

Or install globally:

```bash
npx skills add domfelipe/mikael-3.3-co-behavior -g -y
```

The skill is automatically discovered and loaded by OpenCode on next session.

</details>

<details>
<summary><strong>🤖 Claude Code</strong></summary>

**Option A — Project-level (per repo):**

```bash
# Clone the skill into your project
git clone https://github.com/domfelipe/mikael-3.3-co-behavior.git /tmp/mikael
cp /tmp/mikael/SKILL.md ./CLAUDE.md
```

**Option B — Global (all projects):**

```bash
mkdir -p ~/.claude
curl -sL https://raw.githubusercontent.com/domfelipe/mikael-3.3-co-behavior/main/SKILL.md > ~/.claude/CLAUDE.md
```

**Option C — As a subagent:**

```bash
mkdir -p .claude/agents
curl -sL https://raw.githubusercontent.com/domfelipe/mikael-3.3-co-behavior/main/SKILL.md > .claude/agents/mikael.md
```

Then register in `.claude/settings.json`:

```json
{
  "agents": {
    "mikael": {
      "description": "Behavioral discipline inspired by Claude Opus 4.7",
      "prompt": ".claude/agents/mikael.md"
    }
  }
}
```

Invoke with: `claude -a mikael "your task"`

</details>

<details>
<summary><strong>🧠 OpenAI Codex CLI</strong></summary>

**Option A — Project-level:**

```bash
curl -sL https://raw.githubusercontent.com/domfelipe/mikael-3.3-co-behavior/main/SKILL.md > ./AGENTS.md
```

Codex reads `AGENTS.md` from the project root automatically on every session.

**Option B — Global (all projects):**

```bash
mkdir -p ~/.codex
curl -sL https://raw.githubusercontent.com/domfelipe/mikael-3.3-co-behavior/main/SKILL.md > ~/.codex/AGENTS.md
```

**Option C — Custom instructions via config:**

```bash
curl -sL https://raw.githubusercontent.com/domfelipe/mikael-3.3-co-behavior/main/SKILL.md > ~/.codex/custom-instructions.md
```

Then in `~/.codex/config.toml`:

```toml
instructions_file = "~/.codex/custom-instructions.md"
```

</details>

<details>
<summary><strong>🛠️ Aider</strong></summary>

**Option A — Via `--read` flag (per session):**

```bash
curl -sL https://raw.githubusercontent.com/domfelipe/mikael-3.3-co-behavior/main/SKILL.md > ./MIKAEL.md
aider --read MIKAEL.md
```

**Option B — Via `.aider.conf.yml` (persistent):**

```bash
curl -sL https://raw.githubusercontent.com/domfelipe/mikael-3.3-co-behavior/main/SKILL.md > ./MIKAEL.md
```

Then in `.aider.conf.yml`:

```yaml
read:
  - MIKAEL.md
```

**Option C — Via `CONVENTIONS.md` (auto-detected):**

```bash
curl -sL https://raw.githubusercontent.com/domfelipe/mikael-3.3-co-behavior/main/SKILL.md > ./CONVENTIONS.md
```

Aider auto-detects `CONVENTIONS.md` in the repo root.

</details>

<details>
<summary><strong>🔵 Continue.dev (VS Code)</strong></summary>

**Option A — Local rules:**

```bash
mkdir -p .continue/rules
curl -sL https://raw.githubusercontent.com/domfelipe/mikael-3.3-co-behavior/main/SKILL.md > .continue/rules/mikael.md
```

Rules in `.continue/rules/` are automatically loaded for Agent, Chat, and Edit modes.

**Option B — Via `config.yaml`:**

```yaml
rules:
  - uses: domfelipe/mikael-3.3-co-behavior
```

**Option C — Global rules:**

```bash
mkdir -p ~/.continue/rules
curl -sL https://raw.githubusercontent.com/domfelipe/mikael-3.3-co-behavior/main/SKILL.md > ~/.continue/rules/mikael.md
```

</details>

<details>
<summary><strong>🔴 Roo Code / Cline (VS Code)</strong></summary>

**Option A — Workspace rules (`.clinerules/`):**

```bash
mkdir -p .clinerules
curl -sL https://raw.githubusercontent.com/domfelipe/mikael-3.3-co-behavior/main/SKILL.md > .clinerules/mikael.md
```

**Option B — Roo Code workspace rules (`.roo/rules/`):**

```bash
mkdir -p .roo/rules
curl -sL https://raw.githubusercontent.com/domfelipe/mikael-3.3-co-behavior/main/SKILL.md > .roo/rules/mikael.md
```

**Option C — Global rules:**

```bash
# Cline
mkdir -p ~/.clinerules
curl -sL https://raw.githubusercontent.com/domfelipe/mikael-3.3-co-behavior/main/SKILL.md > ~/.clinerules/mikael.md

# Roo Code
mkdir -p ~/.roo/rules
curl -sL https://raw.githubusercontent.com/domfelipe/mikael-3.3-co-behavior/main/SKILL.md > ~/.roo/rules/mikael.md
```

</details>

<details>
<summary><strong>🟢 Cursor</strong></summary>

**Option A — `.cursorrules` (project root):**

```bash
curl -sL https://raw.githubusercontent.com/domfelipe/mikael-3.3-co-behavior/main/SKILL.md > .cursorrules
```

**Option B — `.cursor/rules/` directory:**

```bash
mkdir -p .cursor/rules
curl -sL https://raw.githubusercontent.com/domfelipe/mikael-3.3-co-behavior/main/SKILL.md > .cursor/rules/mikael.mdc
```

**Option C — Settings → AI → Custom Instructions:**

Copy the contents of `SKILL.md` and paste into Cursor's custom instructions field in Settings.

</details>

<details>
<summary><strong>🟣 Windsurf</strong></summary>

```bash
curl -sL https://raw.githubusercontent.com/domfelipe/mikael-3.3-co-behavior/main/SKILL.md > .windsurfrules
```

Windsurf auto-detects `.windsurfrules` in the project root.

</details>

<details>
<summary><strong>🔵 GitHub Copilot (VS Code)</strong></summary>

**Option A — `.github/copilot-instructions.md`:**

```bash
mkdir -p .github
curl -sL https://raw.githubusercontent.com/domfelipe/mikael-3.3-co-behavior/main/SKILL.md > .github/copilot-instructions.md
```

**Option B — Scoped instructions:**

```bash
mkdir -p .github/instructions
curl -sL https://raw.githubusercontent.com/domfelipe/mikael-3.3-co-behavior/main/SKILL.md > .github/instructions/mikael.instructions.md
```

</details>

<details>
<summary><strong> OpenCode (manual install)</strong></summary>

```bash
# Global (all projects)
mkdir -p ~/.opencode/skills/mikael-3.3-co-behavior
curl -sL https://raw.githubusercontent.com/domfelipe/mikael-3.3-co-behavior/main/SKILL.md > ~/.opencode/skills/mikael-3.3-co-behavior/SKILL.md

# Or project-level
mkdir -p .opencode/skills/mikael-3.3-co-behavior
curl -sL https://raw.githubusercontent.com/domfelipe/mikael-3.3-co-behavior/main/SKILL.md > .opencode/skills/mikael-3.3-co-behavior/SKILL.md
```

</details>

<br/>

### Universal Manual Install

If your tool isn't listed above, the pattern is always the same:

1. **Download** `SKILL.md` from this repo
2. **Place it** where your tool reads custom instructions (check your tool's docs)
3. **Restart** your agent session

The file is pure Markdown — no dependencies, no build step, no compilation.

<br/>

## 📦 What's Inside

**11 modules. 1,156 lines. Zero fluff.**

| Module | What It Does | Depth |
|--------|-------------|-------|
| 🧠 **Core Behavior** | Default stance, tone rules, refusal handling, wellbeing | Helping postures, reframing test, escalation protocol |
| 🔍 **Search Policy** | When to search, query construction, effort scaling | Present-tense trap, source quality tiers, snippet trap |
| 🛡️ **Copyright** | Hard limits, paraphrase standards, self-check | 15-word limit, one-quote-per-source, displacive summary rule |
| 📄 **File Handling** | Creation triggers, artifacts, sharing | File flow, good/bad sharing examples, skill-first rule |
| 🧭 **Tool Routing** | Decision framework, tool-specific guidelines | Internal-first priority, call scaling, MCP registry |
| 🎨 **Visualizer** | 4-step routing, triggers, design guidance | Category match vs style preference, spec triggers |
| 🔌 **API Patterns** | Claudeception, MCP integration, context | Structured outputs, response handling, UI requirements |
| 💭 **Memory System** | Conversation search, cue recognition | Linguistic signals, query construction, pagination |
| 🛡️ **Safety** | Child safety, harmful content, mental health | Critical priority rules, disordered eating boundaries |
| ⚖️ **Neutrality** | Evenhandedness, political neutrality, controversy | Presenting arguments, good-faith engagement |
| 🔄 **Self-Correction** | Mistake handling, verification, failure recovery | Root cause fixes, 3-failure protocol, no shotgun debugging |

<br/>

## 🔬 What Makes This Different

Most agent skills are checklists. This is a **behavioral specification**.

| Typical Skill | Mikael |
|---------------|--------|
| "Search before answering" | Full policy with present-tense trap, query construction rules, source quality tiers, and the "I'm pretty sure" trap |
| "Respect copyright" | Hard limits with examples of violations vs compliance, self-check checklist, displacive summary rule |
| "Create files when needed" | Complete file flow, creation triggers with examples, artifact criteria, good/bad sharing patterns |
| "Be safe" | Child safety protocol, mental health boundaries, disordered eating rules, escalation protocol |

Every rule includes **concrete examples**, **edge cases**, and **decision criteria**. This is what a Senior AI Engineer would write — not a summary, a specification.

<br/>

## 🎯 Who Is This For?

- **Agent builders** who want production-grade behavioral constraints without writing 1,000+ lines from scratch
- **Prompt engineers** studying how top models handle tool routing, safety, and content creation
- **Developers** tired of agents that over-format, skip searches, or ignore copyright
- **Engineering leads** who need consistent agent behavior across their team
- **Curious minds** who want to peek behind the curtain of how advanced agents are configured

<br/>

## 🏗️ Design Philosophy

> **Adapted, not copied.** Inspired by Opus 4.7, but restructured and rewritten in my own format. The organization, emphasis, and some rules reflect my own judgment about what matters.

- **Modular** — Each section is self-contained. Agents can reference specific modules without loading everything.
- **Practical** — Every rule maps to a concrete behavior. No abstract principles.
- **Transferable** — These patterns work across agents, not just one model.
- **Verifiable** — Rules include self-check mechanisms and clear pass/fail criteria.

<br/>

## 🚀 Try It Out

Install it. Load it on your agent. Notice the difference in how it handles searches, files, and formatting.

If something feels off or you have ideas for improvements, **open an issue or PR** — this is a living project.

<br/>

---

<br/>

<p align="center">
  <sub>This skill is inspired by publicly observable behavior from Claude Opus 4.7 but is my own adaptation. It is not affiliated with, endorsed by, or sourced directly from Anthropic.</sub>
</p>

<br/>

---

<br/>

<p align="center">
  <img src="https://flagcdn.com/w80/br.png" alt="Brazil" width="32" />
</p>

<p align="center">
  <strong>🇧🇷 Português</strong>
</p>

<p align="center">
  <em>Uma especificação comportamental de 1.156 linhas para agentes de IA, adaptada a partir dos padrões que observei dentro do system prompt do Claude Opus 4.7.</em>
</p>

<br/>

### ✦ A Ideia

Passei tempo analisando como modelos de ponta se comportam internamente — não apenas *o que* dizem, mas *como* decidem dizer. Quando buscar na web vs. responder da memória. Quando criar um arquivo vs. responder no chat. Como lidar com copyright sem quebrar o fluxo.

Isso não é mágica. São **padrões de engenharia**. E são transferíveis.

Extraí os princípios, reestruturei no meu próprio formato e empacotei como uma skill que qualquer agente no ecossistema open skills pode instalar.

<br/>

### ✦ O Que Você Ganha

<table>
  <tr>
    <th width="33%" align="center">Antes</th>
    <th width="33%" align="center"></th>
    <th width="33%" align="center">Depois</th>
  </tr>
  <tr>
    <td align="center">🎲 Chuta a partir do treino</td>
    <td align="center">→</td>
    <td align="center">🔍 Busca antes de toda pergunta factual</td>
  </tr>
  <tr>
    <td align="center">📋 Over-formatado, cheio de bullets</td>
    <td align="center">→</td>
    <td align="center">✍️ Prosa natural, formatação mínima</td>
  </tr>
  <tr>
    <td align="center">📁 Cria pra tudo ou pra nada</td>
    <td align="center">→</td>
    <td align="center">📄 Gatilhos concretos de criação</td>
  </tr>
  <tr>
    <td align="center">⚖️ Ignora limites de copyright</td>
    <td align="center">→</td>
    <td align="center">🛡️ Máx. 15 palavras por citação</td>
  </tr>
  <tr>
    <td align="center">🔀 Escolhe ferramentas aleatoriamente</td>
    <td align="center">→</td>
    <td align="center">🧭 Árvore de decisão clara</td>
  </tr>
  <tr>
    <td align="center">🚫 Limites inconsistentes</td>
    <td align="center">→</td>
    <td align="center">🧒 Segurança estruturada</td>
  </tr>
</table>

<br/>

### 🔬 O Que Torna Isso Diferente

A maioria das skills são checklists. Esta é uma **especificação comportamental**.

Cada regra inclui **exemplos concretos**, **edge cases** e **critérios de decisão**. É o que um Senior AI Engineer escreveria — não um resumo, uma especificação.

- "Buscar antes de responder" → policy completa com armadilha do tempo presente, regras de construção de queries, tiers de qualidade de fontes
- "Respeitar copyright" → limites rígidos com exemplos de violação vs conformidade, checklist de auto-verificação
- "Criar arquivos quando necessário" → fluxo completo, gatilhos com exemplos, critérios de artifacts, padrões bons/ruins de compartilhamento

<br/>

### ⚡ Instalação Rápida

```bash
npx skills add domfelipe/mikael-3.3-co-behavior
```

Só isso. O agente absorve as restrições comportamentais no próximo load.

<br/>

### 📦 O Que Tem Dentro

**11 módulos. 1.156 linhas. Zero enrolação.**

| Módulo | O Que Faz |
|--------|-----------|
| 🧠 **Comportamento Base** | Postura padrão, regras de tom, tratamento de recusa |
| 🔍 **Política de Busca** | Quando buscar, como construir queries, esforço proporcional |
| 🛡️ **Regras de Copyright** | Limites rígidos, paráfrase primeiro, filtros de segurança |
| 📄 **Manuseio de Arquivos** | Gatilhos de criação, estrutura de diretórios, critérios |
| 🧭 **Roteamento de Ferramentas** | Árvores de decisão para web_search, image_search, visualize |
| 🎨 **Visualizer** | Roteamento em 4 passos: visual → MCP → arquivo → inline |
| 🔌 **Padrões de API** | Claudeception, integração MCP, gerenciamento de contexto |
| 💭 **Sistema de Memória** | Cues de busca em conversas passadas, recuperação de histórico |
| 🛡️ **Segurança** | Child safety, conteúdo nocivo, saúde mental |
| ⚖️ **Neutralidade** | Imparcialidade, neutralidade política, controvérsias |
| 🔄 **Auto-correção** | Tratamento de erros, verificação, recuperação de falhas |

<br/>

### 🎯 Pra Quem É

- **Construtores de agentes** que querem restrições comportamentais de nível production
- **Engenheiros de prompt** estudando como modelos top lidam com roteamento e segurança
- **Líderes de engenharia** que precisam de comportamento consistente de agentes no time
- **Desenvolvedores** cansados de agentes que formatam demais ou pulam buscas
- **Curiosos** que querem espiar por trás das cortinas

<br/>

### 🏗️ Filosofia de Design

> **Adaptado, não copiado.** Inspirado no Opus 4.7, mas reestruturado e reescrito no meu formato.

- **Modular** — Cada seção é autocontida
- **Prático** — Toda regra mapeia um comportamento concreto
- **Transferível** — Padrões que funcionam em qualquer agente
- **Verificável** — Regras incluem mecanismos de auto-verificação

<br/>

### 🚀 Experimente

Instale, carregue no seu agente e note a diferença. Se algo não soar certo ou tiver ideias pra melhorar, abre uma issue ou PR — esse é um projeto vivo.

<br/>

---

<br/>

<p align="center">
  <sub>🇧 Desenvolvido no Brasil com  e obsessão por detalhes</sub>
</p>
