# Document schema

## Standard Context note

```yaml
---
document_type: context_note
source_type: monologue | transcript | interview | conversation | text
date: YYYY-MM-DD
people: []
primary_section:
status: inbox | organized | reviewed
entities: []
topics: []
privacy: private | sensitive | shareable
derived_from: []
routes: []
topic_index:
  - entity:
    speaker:
    section:
    keywords: []
---
```

Required human-readable sections:

1. title;
2. topic navigation;
3. organization note;
4. organized source text;
5. derived Context, with an explicit “not original wording” notice.

## Topic index contract

Each entry must point to one exact heading path:

```yaml
- entity: Project Atlas
  speaker: User
  section: "User's expression > Why Project Atlas started"
  keywords: [origin, user pain, prototype]
```

Keywords should support likely retrieval language, including stable aliases. Do not stuff generic words.

## Entity index entry

```markdown
## Project Atlas

Aliases: Atlas, project-atlas

### Original Context

- [[path/to/context-note]]
  - User: origin, product judgment, current uncertainty.

### Canonical project material

- [[path/to/project-doc]]: product definition and current scope.

### Default retrieval strategy

1. For motivation, read original Context.
2. For product facts, read the canonical project document.
3. For counterarguments, read external feedback sections.
```

## Filename rules

- Context: `YYYYMM_source_concrete-topic.md`
- Entity-centered reference: `entity_core-judgment.md`
- Conversation: `person_concrete-conversation-theme.md`
- Avoid emojis, vague adjectives, and private legal names in shareable filenames.
