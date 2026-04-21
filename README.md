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

---

## 🇧🇷 Português

> E se seu agente tivesse a disciplina comportamental do Claude Opus 4.7 — busca antes de responder, respeito a direitos autorais, roteamento inteligente entre ferramentas — como uma skill reutilizável?

Um framework comportamental para agentes de IA, adaptado a partir dos padrões que observei dentro do system prompt do Claude Opus 4.7.

### A ideia

Passei tempo analisando como modelos de ponta se comportam internamente — não apenas *o que* dizem, mas *como* decidem dizer. Quando buscar na web vs. responder da memória. Quando criar um arquivo vs. responder no chat. Como lidar com copyright sem quebrar o fluxo. Como rotear entre ferramentas sem narrar a decisão.

Isso não é mágica. São **padrões de engenharia**. E são transferíveis.

Extraí os princípios, reestruturei no meu próprio formato e empacotei como uma skill que qualquer agente no ecossistema open skills pode instalar.

### O que você ganha

| Capacidade | Antes | Depois |
|------------|-------|--------|
| **Disciplina de busca** | Chuta a partir do treino | Busca antes de toda pergunta factual sobre o presente |
| **Copyright** | Cita livremente, risco de reprodução | Máx. 15 palavras por citação, uma por fonte, paráfrase primeiro |
| **Roteamento de ferramentas** | Escolhe aleatoriamente ou narra a escolha | Árvore de decisão clara: MCP → arquivo → visualizer → inline |
| **Criação de arquivos** | Cria pra tudo ou pra nada | Gatilhos concretos: blog post → arquivo, explicação → inline |
| **Tom** | Over-formatado, cheio de bullets, robótico | Prosa natural, formatação mínima, conciso |
| **Segurança** | Limites inconsistentes | Child safety, saúde mental, filtros de conteúdo nocivo |

### Instalação rápida

```bash
npx skills add domfelipe/mikael-3.3-co-behavior
```

Só isso. O agente absorve as restrições comportamentais no próximo load.

### O que tem dentro

- **Comportamento base** — postura padrão, regras de tom, tratamento de recusa
- **Política de busca** — quando buscar, como construir queries, esforço proporcional à complexidade
- **Regras de copyright** — limites rígidos, paráfrase primeiro, filtros de segurança
- **Manuseio de arquivos** — gatilhos de criação, estrutura de diretórios, critérios de artifacts
- **Roteamento de ferramentas** — árvores de decisão para web_search, image_search, visualize, computer_use
- **Visualizer** — roteamento em 4 passos: visual necessário → MCP → arquivo → widget inline
- **Padrões de API** — Claudeception, integração MCP, gerenciamento de contexto
- **Sistema de memória** — cues de busca em conversas passadas, recuperação de histórico

### Pra quem é

- **Construtores de agentes** que querem restrições comportamentais de nível production sem escrever do zero
- **Engenheiros de prompt** estudando como modelos top lidam com roteamento, segurança e criação de conteúdo
- **Desenvolvedores** cansados de agentes que formatam demais, pulam buscas ou ignoram copyright
- **Curiosos** que querem espiar por trás das cortinas de como agentes avançados são configurados

### Decisões de design

- **Adaptado, não copiado** — Inspirado no Opus 4.7, mas reestruturado e reescrito no meu formato. A organização e ênfase refletem meu próprio julgamento.
- **Modular** — Cada seção é autocontida. Agentes podem referenciar módulos específicos sem carregar tudo.
- **Prático** — Toda regra mapeia um comportamento concreto. Sem princípios abstratos.

### Experimente

Instale, carregue no seu agente e note a diferença em como ele lida com buscas, arquivos e formatação. Se algo não soar certo ou tiver ideias pra melhorar, abre uma issue ou PR — esse é um projeto vivo.

### Disclaimer

Esta skill é inspirada em comportamento publicamente observável do Claude Opus 4.7, mas é minha própria adaptação. Não é afiliada, endossada ou fornecida diretamente pela Anthropic. Alguns padrões podem diferir da configuração real do modelo.

---

> 🇧🇷 Desenvolvido no Brasil
