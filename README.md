# AI Second Brain / Wissensgraph — Showcase

> Privacy-safe showcase of a Git-backed personal knowledge system that connects human notes, AI agents, structured memory and multiple clients.

## Why I built this

Chats, project decisions, research and operational knowledge are usually scattered across tools. I wanted a system in which useful knowledge survives the individual conversation and becomes a reusable, versioned knowledge base.

The private production repository therefore acts as a **single source of truth**. AI agents can retrieve relevant context, add verified decisions and project progress, and keep the knowledge base synchronized without storing complete chat histories.

This public repository intentionally contains **no private notes, credentials, personal data or production content**. It documents the architecture and engineering decisions only.

## Architecture

```text
ChatGPT / AI Agents / Hermes
          │
          ▼
  Knowledge extraction
  + relevance filtering
          │
          ▼
┌──────────────────────────┐
│ GitHub Knowledge Base    │
│ Single Source of Truth   │
│ Markdown + Git history   │
└────────────┬─────────────┘
             │
      ┌──────┴──────┐
      ▼             ▼
   Obsidian       Logseq
      │             │
      └──────┬──────┘
             ▼
       Human review
```

## Knowledge model

The production vault is organized by responsibility rather than by application:

| Area | Purpose |
|---|---|
| `Projekte/` | Active and completed initiatives |
| `Wissen/` | Reusable knowledge, research and procedures |
| `CRM/` | Relationship and communication context |
| `Journal/` | Daily notes and decisions |
| `Hermes/` | Agent workflows, tasks and automation |
| `Vorlagen/` | Reusable note templates |

Notes use Markdown and wiki-style links such as `[[Wissen/...]]` and `[[Projekte/...]]`, turning individual notes into a navigable graph.

## Agent workflow

1. Retrieve only context relevant to the current task.
2. Distinguish raw conversation from durable knowledge.
3. Store confirmed decisions, project progress, reusable procedures and validated research.
4. Update existing notes instead of blindly replacing them.
5. Link related knowledge nodes.
6. Keep secrets, tokens, account data and unnecessary raw transcripts out of the vault.
7. Version every meaningful change through Git.

## Engineering principles

- **Git as source of truth** — history, rollback and traceability are built in.
- **Human-in-the-loop** — AI maintains knowledge; humans remain the authority for consequential decisions.
- **Selective memory** — the system stores useful knowledge, not indiscriminate chat archives.
- **Context minimization** — agents load only the notes required for a task.
- **Privacy by design** — credentials and sensitive raw data do not belong in the knowledge graph.
- **Tool independence** — Markdown keeps the data portable across Obsidian, Logseq, GitHub and future clients.
- **Agent interoperability** — multiple agents can work against the same documented rules and repository state.

## What this demonstrates

This project is less about a note-taking app and more about **system architecture**: defining a canonical data source, separating responsibilities, designing information flows, coordinating multiple AI agents, managing state, preserving auditability and integrating different clients around one data model.

For a Data/AI architecture context, the interesting problem is the full lifecycle:

```text
unstructured interaction
        ↓
relevance / validation
        ↓
structured knowledge
        ↓
versioned persistence
        ↓
retrieval by humans & agents
        ↓
new decisions and updates
```

## Production scale

At the time this showcase was created, the private repository contained roughly **170 versioned files and directories**, including daily journals, project notes, reusable knowledge, agent memory/workflow definitions and a generated graph representation.

## Repository contents

- `README.md` — public project overview
- `ARCHITECTURE.md` — architecture and design decisions
- `examples/` — sanitized examples of the knowledge model

## Privacy

The real knowledge graph is private. This showcase deliberately reproduces the **architecture, patterns and sanitized examples**, not the personal knowledge stored in production.

---

Built as a practical experiment in AI-assisted knowledge architecture, agent memory and Git-based information lifecycle management.
