# Architecture

[Documentation index](README.md) · [Indexing](INDEXING.md) · [Workflow](WORKFLOW.md)

## Product boundary

ContextAll is a personal Context compiler:

```text
heterogeneous, fragmented human traces
        ↓
trustworthy source records
        ↓
addressable indexes
        ↓
explicit interpretation and downstream work
```

It uses readable Markdown and YAML so the owner can inspect every transformation and move the vault without exporting from a proprietary database.

## The five layers

### L0 — Capture

Temporary ingress for chats, voice transcripts, interviews, journals, notes, clippings, OCR, files, links, and disconnected thoughts.

Capture preserves arrival context. It does not promise that the input is clean, chronological, correctly attributed, or limited to one topic.

### L1 — Source records

Canonical evidence organized for reading while preserving wording, examples, uncertainty, attribution, and traceability.

Permitted changes include sectioning, obvious transcription correction, speaker separation, and regrouping scattered fragments under concrete topics. Stylistic rewriting and silent summarization are not permitted.

External sources also live at this trust layer when attribution and quotation boundaries are preserved, but they are not treated as the user's voice.

### L2 — Retrieval indexes

Pointers that make source records addressable:

- source index;
- entity and alias index;
- concrete topic index;
- optional timeline;
- note-level `topic_index` paths;
- total index by semantic domain.

Indexes describe relationships. They do not become a second copy of the source. See [Indexing](INDEXING.md).

### L3 — Derived Context

AI-generated summaries, questions, cross-note links, hypotheses, disagreements, and possible routes. This layer may evolve or be wrong, so it must carry explicit provenance and must never be quoted as the user's original expression.

### L4 — Destinations

Content, products, projects, investment work, decisions, relationship reflection, and visual artifacts. Each destination may transform material according to its own purpose while retaining a route back to L1.

## Trust order

```text
raw capture
  > organized source record
  > index description
  > derived interpretation
  > transformed destination
```

“Greater than” means stronger quotation authority, not greater usefulness. A destination document may be the best current product definition; it is still not proof of what the user originally said.

## Write path

1. Read private profile, vault map, and destination descriptions.
2. Register source and split only at reliable source/topic boundaries.
3. Assign fragment IDs when later regrouping could obscure order.
4. Detect input mode and apply its cleanup policy.
5. Create or append the Source Context note.
6. Choose one primary semantic domain.
7. Write visible topic navigation and note-level `topic_index`.
8. Update required vault-level indexes.
9. Add optional Derived Context.
10. Link mature material to a destination.
11. Report every write and unresolved uncertainty.

## Read path

1. Convert the question into source, entity, topic, and time constraints.
2. Read only the relevant vault-level index.
3. Select candidate notes.
4. Inspect each candidate's `topic_index`.
5. Open matching sections and source fragments.
6. Use L1 for evidence and L3 for exploration.
7. Use L4 for current project facts when its provenance is intact.

## Append versus create

Append only when the central entity and durable topic both align and the note remains a coherent retrieval unit. Create when the event, speaker relationship, object, or question is independently meaningful. Send uncertain material to the inbox rather than creating false certainty.

## Public framework, private identity

Public repository:

- layer and indexing contracts;
- empty templates;
- fictional examples;
- configuration examples;
- role-based design guidance.

Private vault:

- real profile, aliases, and design choices;
- conversations, transcripts, and source files;
- generated entity/source/topic indexes;
- health, relationship, financial, and confidential work material.
