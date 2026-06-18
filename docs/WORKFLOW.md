# Workflow

## End-to-end chain

| Stage | Input | Decision | Output |
|---|---|---|---|
| 1. Capture | pasted or imported material | does it already have a reliable source boundary? | one or more capture units |
| 2. Detect | capture unit | monologue, conversation, interview, external reference, design preference? | transformation policy |
| 3. Preserve | raw source | what can be cleaned without changing meaning? | canonical organized text |
| 4. Classify | organized text | what is the primary meaning? | one Context domain |
| 5. Resolve | domain + entity | append, create, or inbox? | stable note path |
| 6. Index | final headings | which entities, speakers, section paths, aliases, keywords? | note and vault indexes |
| 7. Derive | canonical note | are questions, links, or routes useful? | isolated derived Context |
| 8. Activate | mature material | content, project, product, investment, or none? | linked destination artifact |
| 9. Review | changed files | did we preserve trust, retrieval, and privacy? | verified write report |

## Input-mode policies

### Mixed capture

Split conservatively using blank lines, source changes, explicit delimiters, and clear topic shifts. Do not merge unrelated items merely because they arrived together.

### Personal monologue

Keep sequence and texture. Add headings only at genuine topic changes. Repetition may carry emotional or cognitive meaning and should not be erased by default.

### Conversation or interview

Use a two-pass organization:

1. separate speakers;
2. regroup each speaker's scattered remarks by topic.

This makes the material retrievable without pretending the conversation was originally a polished essay.

### External reference

Keep source attribution, date, and quotation boundaries. Route it to reference material, not the personal voice layer.

### Design preference

Update one canonical design profile. Keep both normalized tokens and the raw preference record so future changes remain explainable.

## Index maintenance

For each note:

- title topics must match real sections;
- `entities` should use stable canonical names;
- `topic_index.section` should be an exact heading path;
- `keywords` should reflect likely user queries;
- aliases live in the entity index, not inconsistently across notes.

## Periodic operation

### Weekly

- empty the inbox;
- repair incomplete metadata;
- add new entities;
- check that derived notes are visibly labeled.

### Monthly

- promote mature material;
- merge true duplicates;
- test retrieval paths;
- update profile, privacy boundaries, and design preferences;
- archive stale interpretations without deleting source evidence.
