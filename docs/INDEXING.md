# Indexing

[Documentation index](README.md) · [Architecture](ARCHITECTURE.md) · [Workflow](WORKFLOW.md)

## Why indexing is a separate layer

Personal Context is too irregular for filenames alone. One idea may be split across a voice transcript, two chats, an interview, and a project note. One document may contain several people and several topics. Indexes describe these relationships without duplicating or rewriting the source.

## Four vault-level indexes

### 1. Source index

Tracks provenance and capture boundaries.

Use it to answer:

- where did this material come from?
- which notes were produced from the same conversation, recording, or import?
- can this passage be quoted or shared?

Minimum fields: `source_id`, source type, source reference, capture date, generated note paths, privacy.

### 2. Entity index

Tracks stable objects and their aliases: people, companies, products, projects, places, and organizations.

Use it to answer: “What have I actually said about this object, and where?”

Each entity entry separates original Context, canonical destination documents, related references, and default retrieval strategy.

### 3. Topic index

Tracks concrete issues rather than broad categories. Prefer “Project Atlas pricing uncertainty” over “business,” and “Mira's objection to weekly logs” over “conversation.”

Topic entries point to exact note sections and preserve the speaker or source role.

### 4. Timeline

Tracks meaningful changes: first appearance, decision, contradiction, update, abandonment, or revival. It is optional for static material and valuable for evolving beliefs or projects.

## Note-level topic index

Every organized note carries a compact map near the top:

```yaml
topic_index:
  - topic: Project Atlas pricing uncertainty
    entity: Project Atlas
    speaker: User
    section: "Organized source > Why pricing still feels premature"
    keywords: [pricing, willingness to pay, prototype]
    source_fragments: [frag-001, frag-004]
```

The `section` value must match a real heading path. `source_fragments` preserves the route back to scattered pieces that were regrouped.

## Fragment identity

When a capture contains disconnected statements, assign lightweight fragment IDs before moving or regrouping them:

```markdown
<a id="frag-001"></a>
First original fragment.

<a id="frag-002"></a>
Second original fragment from later in the source.
```

Fragment IDs are useful when order changes during conversation or interview organization. They should not interrupt ordinary reading more than necessary.

## Retrieval sequence

1. Identify likely source, entity, topic, or time constraints from the query.
2. Open only the relevant vault-level index.
3. Select candidate notes.
4. Read note-level `topic_index` metadata.
5. Open only the matching heading path.
6. Follow fragment or source references when attribution matters.
7. Prefer Source Context for quotation; use Derived Context only for exploration.

## Index update contract

After writing or moving a note:

- update the source index when provenance or note paths changed;
- update the entity index for new entities, aliases, or retrieval routes;
- update the topic index for new concrete topics;
- update the timeline only for meaningful state changes;
- update the total index so people can discover the note by domain;
- report exactly which indexes changed.

An agent must not claim that indexing is complete if it only added YAML to the note and skipped vault-level indexes.

## Avoid these failure modes

| Failure | Consequence | Repair |
|---|---|---|
| indexing only by filename | hidden topics stay invisible | add section-level topic entries |
| using generic topics | search returns everything | use object + judgment/action/tension |
| treating aliases as separate entities | history fragments | choose a canonical name and map aliases |
| copying source text into every index | divergence and privacy risk | store pointers and short descriptions |
| indexing AI summaries as source claims | false attribution | label layer and provenance explicitly |
