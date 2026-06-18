---
name: contextall-manager
description: Organize heterogeneous, fragmented personal material—chats, voice transcripts, interviews, journals, notes, clippings, OCR, external references, and scattered thoughts—into a privacy-first Context vault. Preserve original expression and provenance, regroup out-of-order fragments, separate AI-derived interpretation, maintain source/entity/topic/time indexes with exact section paths, and route mature Context to downstream work. Use when users ask to整理个人 Context、归档杂乱语料、整理东一句西一句的记录、整理聊天或访谈、更新人物/主题/来源索引，或构建可供 AI 精确检索的个人资料库。
---

# ContextAll Manager

Turn messy human traces into trustworthy, addressable Context without silently rewriting the person.

## Required configuration

Locate:

- vault root;
- `profile.md` for aliases, language, privacy, and downstream goals;
- `vault-map.yaml` for domains, destinations, and all index paths;
- existing source, entity, topic, timeline, and total indexes;
- `design-profile.md` only when visual work is requested.

If configuration is absent, copy examples from `assets/config/`. Keep uncertain material in the configured inbox. Do not infer sensitive identity facts to complete metadata.

## Invariants

1. Treat original personal expression as evidence, not draft copy.
2. Preserve wording, examples, numbers, emotion, uncertainty, and attribution.
3. Fix only obvious transcription errors that block understanding.
4. Keep AI summaries, questions, and hypotheses in Derived Context.
5. Classify by meaning, not by capture tool or file format.
6. Preserve provenance when regrouping “one sentence here, another there.”
7. Prefer reversible writes: create or inbox when append confidence is low.
8. Never copy private source material into public package files.

## Workflow

### 1. Register the source

Record `source_id`, source type/reference, capture time, people, privacy, and language. Split mixed batches only at reliable source or topic boundaries. Assign fragment IDs when later regrouping could hide original order.

### 2. Detect input mode

- **Mixed batch:** keep unrelated arrivals separate.
- **Fragmented monologue/transcript:** preserve texture; regroup only clear topic matches.
- **Conversation/interview:** separate speakers first, then regroup each speaker by topic.
- **External reference:** preserve creator, date, link/file, and quotation boundaries.
- **Design preference:** update the private design profile; do not impose example colors.

Read `references/routing-rules.md` for mode-specific decisions.

### 3. Write Source Context

Copy the closest template from `assets/templates/`. Add a concrete title, source note, topic navigation, and structured metadata. Do not replace source text with a summary.

For conversations, delete only empty acknowledgements, filler, false starts, duplicated starts, and obvious transcription noise. Keep meaningful colloquial language. Mark uncertain speakers as `[未明确]`.

### 4. Resolve append, create, or inbox

Append only when the primary entity and durable topic both match and the note remains coherent. Create for a distinct event, relationship, object, or question. Use inbox when the decision is genuinely unclear.

### 5. Build the index transaction

Maintain:

- note-level `entities`, `topics`, and exact `topic_index` section paths;
- source index and generated note paths;
- entity names and aliases;
- concrete topic entries;
- timeline entries for meaningful changes only;
- total index by semantic domain.

Use: index → candidate note → note `topic_index` → exact heading → source fragment. Read `references/document-schema.md` for contracts.

### 6. Add optional Derived Context

Only when useful, add clearly labeled questions, summaries, cross-note links, disagreements, or downstream routes. Never represent this layer as original wording.

### 7. Route without erasing provenance

Keep the canonical source in Context. Link mature material to content, product, business, investment, relationship, or other destination documents. Record the route rather than silently duplicating.

### 8. Handle visual preferences

Read the user's design profile before visual work. If absent, ask for a palette or mood and confirm generated values before creating durable tokens. Treat bundled CSS values as a neutral temporary preview only.

### 9. Report writes

Report created, appended, moved, and indexed files. Name every updated index. Surface unresolved attribution, classification, and privacy questions. Do not claim indexing is complete when only note metadata changed.

## Review gates

Verify:

- Source Context and Derived Context are visibly separate;
- meaningful original details and source references remain;
- regrouped passages retain fragment traceability when needed;
- topic navigation maps to real headings;
- every `topic_index.section` maps to an exact heading path;
- canonical entity names and aliases are stable;
- required vault-level indexes were written;
- private data stayed in the configured private vault;
- visual outputs use user-confirmed design values.

Read `references/review-protocol.md` for batch and periodic audits.
