# Architecture

## 1. Product boundary

ContextAll is not a generic note sorter. It is a personal context compiler:

```text
unstructured human traces
        ↓
trustworthy, addressable Context
        ↓
AI-assisted retrieval and transformation
```

The system stores Markdown so the user owns the data, can inspect every transformation, and is not locked into an application database.

## 2. Five-layer model

### Layer A — Capture

Temporary ingress for pasted text, transcripts, interviews, messages, and external material. Capture does not imply classification.

### Layer B — Canonical Context

The user's original voice and lived evidence. Structural edits are permitted; stylistic rewriting is not. Every later artifact should be traceable back here.

### Layer C — Retrieval graph

Human navigation and machine retrieval share the same primitives:

- stable entities and aliases;
- concrete topic headings;
- `topic_index` paths and keywords;
- vault-level entity and total indexes.

This is a lightweight graph implemented in Markdown and YAML rather than a hidden vector database.

### Layer D — Derivation

AI-generated questions, cross-note connections, hypotheses, and summaries. Derivation can evolve or be wrong, so it is visually and structurally separated from Context.

### Layer E — Destinations

Public content, product documents, startup ideas, investment work, relationship reflection, and design artifacts. Each destination may transform the source according to its own rules.

## 3. Trust and provenance

The trust order is:

```text
original source > organized source > index metadata > derivation > public transformation
```

Higher transformation means lower quotation authority. A generated summary can help find a passage, but it must not be cited as the user's exact view.

## 4. Write path

1. Read private configuration.
2. Detect input type.
3. Split only at reliable boundaries.
4. Preserve and structure the source.
5. Choose one primary semantic domain.
6. Append or create using entity-topic coherence.
7. Write topic navigation and metadata.
8. Update global indexes.
9. Add optional derivation.
10. Report every filesystem change.

## 5. Read path

1. Normalize the query to an entity or domain.
2. Resolve aliases in the entity index.
3. Select candidate notes.
4. Read each candidate's `topic_index`.
5. Open only matching heading paths.
6. Prefer canonical Context for quotes and destination documents for current product facts.

## 6. Why append versus create matters

Over-creation fragments a person's story. Over-appending creates junk drawers. The system therefore joins material only when both the central entity and durable topic align. Uncertainty defaults to a new note or inbox, preserving reversibility.

## 7. Configuration boundary

The framework is public; identity is private.

Public:

- schemas;
- workflow rules;
- example profile;
- templates;
- design tokens.

Private:

- real profile and aliases;
- conversations and transcripts;
- entity index;
- audience strategy and publishing boundaries;
- absolute source paths;
- health, relationship, employer, and financial information.
