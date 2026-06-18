---
name: contextall-manager
description: Organize personal raw text, transcripts, conversations, observations, and mixed notes into a privacy-first Context vault. Preserve the user's original voice, separate AI-derived ideas, classify by meaning, decide append versus create, maintain entity and topic indexes, and route mature material toward content or projects. Use when the user asks to整理个人 context、归档原话、整理访谈或聊天、建立个人知识底座、更新人物/主题索引，或管理可供 AI 检索的个人语料。
---

# ContextAll Manager

Build a trustworthy personal context layer before turning material into polished content.

## Required inputs

Before writing, locate or ask for:

- vault root;
- `profile.md`, containing identity aliases, privacy boundaries, and optional downstream goals;
- `vault-map.yaml`, containing folder names and routes;
- existing indexes and candidate related notes.

If configuration is absent, copy the examples from `assets/config/` and keep unknown material in the configured inbox. Never infer sensitive identity facts merely to complete metadata.

## Core invariants

1. Treat raw personal expression as source evidence, not draft copy.
2. Preserve wording, examples, numbers, uncertainty, and speaking style.
3. Fix only obvious transcription errors that block understanding.
4. Put every AI-generated question, link, summary, or interpretation in a visibly separate derived section.
5. Classify by what the material means, not by capture format.
6. Prefer a new file when relation to an existing note is uncertain.
7. Never place secrets or private source material in public package files.

## Workflow

### 1. Read configuration and local context

Read the profile, vault map, destination descriptions, entity index, and filenames in likely folders. For public-facing or design work, also read the configured design profile.

### 2. Detect the input mode

- **Mixed capture:** split at reliable topic/source boundaries; keep ambiguous boundaries conservative.
- **Personal monologue:** preserve sequence unless a clear topic change occurs.
- **Conversation/interview:** separate speakers first, then regroup each speaker's scattered remarks by topic.
- **External reference:** preserve source attribution and route outside the personal-voice layer.
- **Design preference:** append to the design profile and update its topic navigation.

Read `references/routing-rules.md` for detailed decisions.

### 3. Create the source-of-truth note

Copy the closest template from `assets/templates/`. Add structured metadata, a concrete title, and topic navigation. Do not replace the source text with a summary.

For conversations, delete only empty acknowledgements, filler, false starts, and duplicated starts. Keep meaningful colloquial language. Mark uncertain speakers as `[未明确]`.

### 4. Decide append versus create

Append only when the primary entity is the same and the new material clearly extends, challenges, or deepens the same topic. Create a new note when the object differs, the event has independent value, or relation is uncertain.

### 5. Update retrieval structures

Maintain:

- note-level `entities`;
- note-level `topic_index` entries with entity, speaker, section path, and keywords;
- a visible topic navigation;
- the vault-level entity index;
- the vault-level total index.

Use the retrieval order: entity index → note `topic_index` → target section. Read `references/document-schema.md` for schemas.

### 6. Add optional derivation

Only when useful, add a clearly labeled derived layer containing follow-up questions, cross-note links, or downstream routes. If public content guidance is configured, generate it from the profile without modifying the source layer.

### 7. Route, do not silently duplicate

Keep the canonical original in Context. Link or deliberately copy mature material to content, product, business, investment, or relationship destinations. Record the route in metadata or the derived section.

### 8. Report writes

Report created, appended, moved, and indexed files. Surface uncertain classifications and privacy warnings. Do not claim an index was updated unless it was written.

## Review gates

Before completion, verify:

- source and AI derivation are visibly separated;
- no meaningful original detail was removed;
- every topic navigation item maps to a real section;
- every `topic_index.section` maps to an exact heading path;
- entities use stable names and aliases;
- private data stayed inside the configured private vault;
- design outputs use the configured tokens rather than invented colors.

Read `references/review-protocol.md` when running periodic maintenance or auditing a large batch.
