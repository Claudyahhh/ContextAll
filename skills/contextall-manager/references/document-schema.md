# Document and index schema

## Standard Context note

```yaml
---
document_type: context_note
source_id: src-YYYYMMDD-short-name
source_type: monologue | transcript | interview | conversation | text | clipping | ocr
source_ref:
captured_at: YYYY-MM-DDTHH:MM:SSZ
language:
people: []
primary_domain:
status: inbox | organized | reviewed
entities: []
topics: []
privacy: private | sensitive | shareable
routes: []
topic_index:
  - topic:
    entity:
    speaker:
    section:
    keywords: []
    source_fragments: []
---
```

Required readable sections:

1. title;
2. topic navigation;
3. source and organization note;
4. Source Context;
5. Derived Context with an explicit provenance notice;
6. routes when material has moved downstream.

## Topic index contract

```yaml
- topic: Project Atlas pricing uncertainty
  entity: Project Atlas
  speaker: User
  section: "Source Context > User > Why pricing still feels premature"
  keywords: [pricing, willingness to pay, prototype]
  source_fragments: [frag-001, frag-004]
```

Rules:

- `topic` uses a concrete object plus judgment, action, tension, or plan;
- `section` exactly matches a heading path;
- `keywords` reflect likely retrieval language and stable aliases;
- `source_fragments` point back to moved or regrouped pieces;
- generic category words do not qualify as topics.

## Source index entry

```markdown
## src-20260618-atlas-conversation

- Type: conversation
- Captured: 2026-06-18
- People: User, Mira
- Privacy: private
- Source reference: [private path or message identifier]
- Generated notes:
  - [[context/path/to/note]]
```

## Entity index entry

```markdown
## Project Atlas

Aliases: Atlas, project-atlas

### Original Context

- [[context/path/to/note]]
  - User: origin, pricing uncertainty, prototype direction.

### Canonical destination material

- [[projects/project-atlas]]: current product definition.

### Retrieval strategy

1. For motivation and quotation, read Original Context.
2. For current facts, read the canonical destination document.
3. For objections, read attributed feedback sections.
```

## Topic index entry

```markdown
## Project Atlas pricing uncertainty

- Entity: Project Atlas
- Aliases: Atlas pricing, willingness to pay
- Sections:
  - [[context/path/to/note#why-pricing-still-feels-premature]] — User; source fragments 001 and 004.
```

## Timeline entry

```markdown
## 2026-06-18 — Project Atlas pricing remains unresolved

- Change type: update
- Entity: Project Atlas
- Source: [[context/path/to/note]]
- Evidence: User says the prototype is not ready for a pricing decision.
```

## Filename rules

- Context: `YYYYMM_source_concrete-topic.md`
- Conversation: `YYYYMM_conversation-person_concrete-theme.md`
- Entity reference: `entity_core-judgment.md`
- Avoid emojis, vague adjectives, and private legal names in shareable filenames.
