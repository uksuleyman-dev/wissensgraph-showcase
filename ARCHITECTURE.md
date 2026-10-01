# Architecture

## Goal

Create a durable knowledge layer between transient AI conversations and long-running projects.

## Core components

### 1. Interaction layer
ChatGPT and other AI agents are entry points. They create research, decisions, tasks and project progress.

### 2. Knowledge-processing layer
Information is filtered before persistence. The goal is not chat archiving but extracting durable knowledge: decisions, verified findings, reusable procedures and project state.

### 3. Canonical persistence layer
A private GitHub repository is the source of truth. Markdown provides a portable representation; Git provides history, diffs, rollback and provenance.

### 4. Graph layer
Wiki links connect projects, people, knowledge and agent documentation. The same source can be rendered as a graph without introducing a second authoritative database.

### 5. Client layer
Obsidian and Logseq consume the same Markdown knowledge base. Clients are views/editors, not competing sources of truth.

## Write path

```text
interaction → classify → validate → choose target note
→ merge/update → create links → commit → push
```

## Read path

```text
task → identify information need → retrieve relevant notes
→ reason with bounded context → act/answer
```

## Consistency strategy

- Pull before modifying the repository.
- Prefer targeted updates over wholesale replacement.
- Commit and push every durable update.
- Never delete knowledge without an explicit reason.
- Resolve contradictory information rather than silently overwriting it.

## Security boundary

The production graph may contain personal context, so the public showcase is structurally representative but content-isolated. Secrets, tokens, one-time codes, banking data and unnecessary raw transcripts are excluded by design.

## Architectural trade-offs

**Markdown instead of a proprietary database:** lower query sophistication, but excellent portability, inspectability and longevity.

**Git instead of opaque memory:** more operational discipline, but strong auditability and rollback.

**Selective persistence instead of full transcripts:** requires relevance judgment, but reduces noise and privacy exposure.

**One canonical repository instead of per-agent memory silos:** requires synchronization, but prevents agents from drifting into incompatible states.
