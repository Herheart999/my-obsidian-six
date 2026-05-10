# Agent Schema for This Obsidian Vault

## Purpose

This repository is a persistent knowledge vault. Treat it like a maintained wiki, not a loose pile of documents.

The agent's job is to:

- ingest information from trustworthy sources
- convert that information into clear markdown notes
- connect related notes with links
- keep the vault organized as it grows

The human's job is to choose sources, ask questions, and decide what matters.

## Operating Model

This vault follows a three-layer pattern:

1. Source layer
   External URLs, PDFs, articles, books, screenshots, transcripts, and other references. These are the source of truth.
2. Wiki layer
   Markdown notes inside this vault. These are the maintained, paraphrased, cross-linked knowledge artifacts.
3. Schema layer
   This file, `AGENT.md`, defines how the agent should write, update, and maintain the wiki.

## Vault Conventions

- Default explanation language for notes is Thai.
- Keep English technical terms when they are clearer or are standard usage.
- Prefer one topic per file.
- Use root-level markdown files unless the user asks for folders.
- Prefer ASCII filenames with descriptive slugs such as `01-logic-gates.md`.
- Do not modify `.obsidian/` unless the user explicitly asks.
- Do not rewrite source material verbatim when a source is copyrighted; create structured paraphrased notes instead.
- Distinguish clearly between facts from a source and synthesis or inference.

## Note Template

Each knowledge note should usually begin with:

```md
# Title

Source: <URL or citation>
Accessed: YYYY-MM-DD

## สรุปย่อ

## ประเด็นสำคัญ

## คำสำคัญ

## ดูเพิ่ม
```

The exact sections may vary, but source attribution and retrieval date should always be present for web-derived notes.

## Writing Rules

- Write for future reuse, not only for the current question.
- Prefer concise synthesis over raw copying.
- Use bullet points for scanability when useful.
- Add `[[wikilinks]]` to related notes when they genuinely help navigation.
- Preserve uncertainty. If a claim is time-sensitive or may change, label it with an "as of accessed date" note.
- When multiple sources disagree, record the disagreement instead of hiding it.

## Standard Operations

### 1. Ingest

When adding a new source:

- read the source carefully
- identify the core topic, definitions, mechanisms, examples, and notable facts
- create a new note or update an existing note
- add cross-links to related notes
- preserve the original source URL in the note

### 2. Query

When answering questions using the vault:

- inspect the most relevant notes first
- synthesize across notes when needed
- cite specific files or source links when helpful
- if a generated answer is durable, store it back into the vault as a note

### 3. Lint

Periodically check the vault for:

- duplicate notes
- broken or missing cross-links
- notes with no source attribution
- outdated time-sensitive facts
- orphan notes that should link to related topics

## Maintenance Preferences

- Update an existing note when the topic already exists.
- Create a separate note only when the content is meaningfully distinct.
- Prefer stable, durable summaries over transient chat-style prose.
- Keep notes readable in plain markdown without requiring plugins.

## Current Local Conventions

For this vault at the moment:

- numbered reference notes are acceptable
- source-based notes should remain easy to browse from the repo root
- duplicate-source requests may be represented as different note formats, such as a full summary and a quick reference

## Success Criteria

The vault is healthy when:

- each note is understandable on its own
- sources are visible
- related ideas connect naturally
- the collection compounds in value over time
