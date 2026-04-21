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
  <a href="https://github.com/domfelipe/mikael-3.3-co-behavior/blob/main/LICENSE">
    <img alt="License" src="https://img.shields.io/badge/license-MIT-ffd700?style=flat&labelColor=1a1a2e" />
  </a>
  <img alt="Built with" src="https://img.shields.io/badge/built%20with-🇧🇷-ffd700?style=flat&labelColor=1a1a2e" />
</p>

<br/>

---

<br/>

## ✦ The Story

Most AI agents feel like they're guessing. They answer from training data when they should search. They create files for everything or nothing. They over-format, narrate their decisions, and ignore copyright.

I spent time reverse-engineering how **Claude Opus 4.7** behaves internally — not just *what* it says, but *how* it decides to say it. The patterns I found weren't magic. They were **engineering discipline**.

So I extracted them, restructured them in my own format, and built **Mikael** — a behavioral framework skill that brings production-grade agent behavior to any system in the open skills ecosystem.

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

## 📦 What's Inside

| Module | What It Does |
|--------|-------------|
| 🧠 **Core Behavior** | Default stance, tone rules, refusal handling, user wellbeing |
| 🔍 **Search Policy** | When to search vs. answer from memory, query construction, effort scaling |
| 🛡️ **Copyright Rules** | Hard limits, paraphrase-first, content safety filters |
| 📄 **File Handling** | Creation triggers, directory structure, artifact criteria |
| 🧭 **Tool Routing** | Decision trees for web_search, image_search, visualize, computer_use |
| 🎨 **Visualizer** | 4-step routing: visual needed → MCP fit → file request → inline widget |
| 🔌 **API Patterns** | Claudeception, MCP integration, context window management |
| 💭 **Memory System** | Conversation search cues, past chat retrieval patterns |

<br/>

## 🎯 Who Is This For?

- **Agent builders** who want production-grade behavioral constraints without writing them from scratch
- **Prompt engineers** studying how top models handle tool routing, safety, and content creation
- **Developers** tired of agents that over-format, skip searches, or ignore copyright
- **Curious minds** who want to peek behind the curtain of how advanced agents are configured

<br/>

## 🏗️ Design Philosophy

> **Adapted, not copied.** Inspired by Opus 4.7, but restructured and rewritten in my own format. The organization and emphasis reflect my own judgment about what matters.

- **Modular** — Each section is self-contained. Agents can reference specific modules without loading everything.
- **Practical** — Every rule maps to a concrete behavior. No abstract principles.
- **Transferable** — These patterns work across agents, not just one model.

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
  <em>Um framework comportamental para agentes de IA, adaptado a partir dos padrões que observei dentro do system prompt do Claude Opus 4.7.</em>
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

### ⚡ Instalação Rápida

```bash
npx skills add domfelipe/mikael-3.3-co-behavior
```

Só isso. O agente absorve as restrições comportamentais no próximo load.

<br/>

### 📦 O Que Tem Dentro

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

<br/>

### 🎯 Pra Quem É

- **Construtores de agentes** que querem restrições comportamentais de nível production
- **Engenheiros de prompt** estudando como modelos top lidam com roteamento e segurança
- **Desenvolvedores** cansados de agentes que formatam demais ou pulam buscas
- **Curiosos** que querem espiar por trás das cortinas

<br/>

### 🏗️ Filosofia de Design

> **Adaptado, não copiado.** Inspirado no Opus 4.7, mas reestruturado e reescrito no meu formato.

- **Modular** — Cada seção é autocontida
- **Prático** — Toda regra mapeia um comportamento concreto
- **Transferível** — Padrões que funcionam em qualquer agente

<br/>

### 🚀 Experimente

Instale, carregue no seu agente e note a diferença. Se algo não soar certo ou tiver ideias pra melhorar, abre uma issue ou PR — esse é um projeto vivo.

<br/>

---

<br/>

<p align="center">
  <sub>🇧 Desenvolvido no Brasil com  e obsessão por detalhes</sub>
</p>
