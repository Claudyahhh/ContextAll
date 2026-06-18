# Workflow

[Documentation index](README.md) · [Architecture](ARCHITECTURE.md) · [Indexing](INDEXING.md)

## End-to-end write chain

| Stage | Input | Decision | Output |
|---|---|---|---|
| 1. Register | pasted/imported material | source, capture time, privacy, boundaries? | source entry + capture units |
| 2. Fragment | messy capture | which pieces can move without losing provenance? | optional fragment IDs |
| 3. Detect | capture unit | monologue, conversation, interview, external reference, mixed batch? | cleanup policy |
| 4. Preserve | raw fragments | what structural cleanup is safe? | Source Context |
| 5. Classify | organized source | what is the primary meaning? | one semantic domain |
| 6. Resolve | domain + entity + topic | append, create, or inbox? | stable note path |
| 7. Index | final headings | source/entity/topic/time pointers? | note + vault indexes |
| 8. Derive | Source Context | are questions or connections useful? | isolated Derived Context |
| 9. Activate | mature material | destination or none? | linked downstream artifact |
| 10. Verify | changed files | trust, links, privacy, exact paths? | write report |

## Input-mode policies

### Mixed batch

Split conservatively using source changes, explicit delimiters, reliable topic shifts, and blank lines. Items arriving in the same paste are not automatically related.

### Fragmented monologue or voice transcript

Preserve the speaking texture and uncertainty. Regroup only when multiple fragments clearly address the same concrete topic. Keep fragment IDs when order or wording may matter later.

### Conversation or interview

Use two passes:

1. separate speakers and mark uncertain attribution;
2. regroup each speaker's scattered remarks by concrete topic.

Remove empty acknowledgements and transcription noise, not meaningful repetition, disagreement, emotion, or personal phrasing.

### External reference

Retain creator, URL/file, date, quotation boundaries, and source type. Route to reference material rather than personal voice. Any connection to the user's beliefs belongs in Derived Context unless explicitly stated by the user.

### Design preference

Design choices belong in the user's private design profile. Ask for missing palette or mood information before establishing durable tokens. See [Design](DESIGN.md).

## Indexing transaction

Treat each write as a small transaction:

1. write or update the source note;
2. confirm exact heading paths;
3. update note-level `topic_index`;
4. update source index;
5. update affected entity and topic entries;
6. update timeline only for a meaningful change;
7. update total index/domain listing;
8. report all changed indexes.

If any required index cannot be updated, report the incomplete step instead of claiming success.

## Retrieval workflow

1. Parse the request into likely entities, topics, source types, dates, and desired trust layer.
2. Resolve aliases.
3. Read the smallest relevant global indexes.
4. Select candidate notes from pointers, not broad full-vault reading.
5. Read note `topic_index` and then exact sections.
6. Follow source fragments when quotation or chronology matters.
7. State whether the answer came from Source Context, Derived Context, or a destination document.

## Review cadence

### Per write

- verify source preservation and attribution;
- verify exact section paths;
- verify every visible navigation item maps to a heading;
- verify index updates and privacy state;
- verify AI additions are isolated.

### Weekly

- process inbox captures;
- repair incomplete source metadata;
- normalize new aliases;
- review broken or vague topic entries.

### Monthly

- merge only true duplicates;
- promote mature material to destinations;
- sample-test retrieval through all four index views;
- review profile, privacy boundaries, and design preferences;
- archive stale interpretations without deleting Source Context.
