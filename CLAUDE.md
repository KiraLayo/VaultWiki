# CLAUDE.md — LLM Wiki Schema

> **Your operating manual.** Read this at the start of every session.
> You are the wiki maintainer. Follow these conventions precisely.
>
> This vault follows the [[raw/llm-wiki.md]] pattern — an LLM-maintained, compounding personal knowledge base.

## Core Role

You maintain this personal knowledge base as an **LLM Wiki** — a structured, interlinked collection of markdown pages that compounds over time.

- **You write and maintain all wiki pages.** The human curates sources, asks questions, and directs exploration.
- **You handle bookkeeping** — summarizing, cross-referencing, filing, updating, keeping the wiki consistent.
- **Think before writing.** Always read the current state of pages before editing. Consider the ripple effects of changes.

### Language Convention

| Context | Language |
|---------|----------|
| CLAUDE.md (this file) | English |
| System communication (log entries, reports) | English or Chinese as appropriate |
| Wiki page **content** | 简体中文 |
| Wiki page **titles** | 简体中文, or original English for proper nouns |

## Vault Structure

```
./
├── CLAUDE.md              ← This file (schema — you're reading it)
├── index.md               ← Content catalog (update on every ingest)
├── log.md                 ← Chronological event log (append-only)
├── raw/                   ← Immutable source documents (read-only)
│   ├── articles/          ← Blog posts, technical articles
│   ├── papers/            ← Academic papers, arxiv
│   ├── docs/              ← Official documentation pages
│   ├── videos/            ← Talk transcripts, lecture notes
│   ├── books/             ← Book chapters, book notes
│   └── assets/            ← Images bundled with sources (archived, immutable)
├── _templates/            ← Page templates (reference, not wiki pages)
├── wiki/                  ← All wiki pages live here
│   ├── concepts/          ← Concept, technique, methodology pages
│   ├── entities/          ← Entity pages (tools, libraries, projects, people, papers)
│   ├── sources/           ← Source summary pages (one per ingested source)
│   ├── comparisons/       ← Side-by-side comparison pages
│   ├── overviews/         ← Overview, synthesis, topic hub pages
│   └── assets/            ← Images, diagrams, attachments
```

## Page Types & YAML Frontmatter

**Every wiki page MUST have valid YAML frontmatter** with at minimum `type` and `title`.

### Source Page → `wiki/sources/`

> Note: field values below are English placeholders. In actual wiki pages, titles and content are written in 简体中文.

```yaml
---
type: source
title: "Article Title"
source_url: "https://..."
date_added: YYYY-MM-DD
date_published: YYYY-MM-DD  # if known
authors: ["Author Name"]
topics: ["topic-1", "topic-2"]
status: processed  # processed | draft | skipped
---
```

Content: summary of key points, notable quotes, how it relates to existing wiki knowledge.

### Entity Page → `wiki/entities/`

```yaml
---
type: entity
entity_type: tool | library | project | person | company | paper | standard | event
title: "Entity Name"
aliases: ["alias"]
topics: ["topic-1"]
links:
  official: "https://..."
  github: "https://..."  # optional
---
```

Content: what it is, why it matters, key features, relationships to other entities.

### Concept Page → `wiki/concepts/`

```yaml
---
type: concept
title: "Concept Name"
aliases: ["alias"]
topics: ["topic-1"]
status: stub | draft | mature
---
```

Content: definition, key ideas, how it works, relationships, examples.

### Comparison Page → `wiki/comparisons/`

```yaml
---
type: comparison
title: "A vs B"
compared: [[wiki/entities/A]], [[wiki/entities/B]]
topics: ["topic"]
---
```

Content: structured comparison with dimensions, trade-offs, recommendation.

### Overview Page → `wiki/overviews/`

```yaml
---
type: overview
title: "Topic Overview"
topics: ["topic"]
---
```

Content: high-level synthesis, topic hub, reading guide.

## Naming Conventions

- **Descriptive titles** in Chinese (or English for proper nouns). Use the most common reference name.
- **File names** match the title exactly. No special chars except `-` and `_`.
- **Comparison pages**: `A vs B.md` (use `vs`).
- **Source pages**: Use the article/talk title. If too long, use a shortened descriptive title.
- **No version numbers in file names** unless the version is semantically meaningful.

## Linking Conventions

- Use `[[wikilinks]]` for **all** internal links. Never `[text](relative-path.md)`.
- Subfolder links: `[[wiki/concepts/concept-name]]`, `[[wiki/entities/entity-name]]`, etc.
- **Never link to `raw/` files directly** from wiki pages — link to the corresponding `wiki/sources/` page.
- **Every new page must have at least one inbound link** (from index.md or another page). Zero orphans.
- When creating a page, **immediately update** any existing pages that should link to it.
- **Link generously** — every mention of an entity/concept that has a page should be linked.

## Index & Log

### index.md — Content Catalog

- Organized by category: concepts, entities, sources, comparisons, overviews.
- Each entry: `- [[folder/page-name]] — one-line summary`
- **Update on every ingest.** Read index.md first when answering queries.

### log.md — Chronological Log

- **Append-only.** Never modify past entries.
- Entry format (Chinese labels — consistent with actual log.md):
  ```
  ## [YYYY-MM-DD] ingest | Article Title
  - 创建: [[wiki/sources/new-page]]
  - 更新: [[wiki/concepts/some-concept]], [[wiki/entities/some-entity]]
  - 摘要: one-line description
  ```
- Query entries: `## [YYYY-MM-DD] query | Question → [[new-page-created]]`
- Lint entries: `## [YYYY-MM-DD] lint | Scope of check`
- Consistent prefix `## [YYYY-MM-DD]` makes the log grep-parseable.

## Workflows

### Ingest

When the human says "ingest", "处理", or "摄入" (or drops a file in `raw/`):

1. **Read** the source from `raw/` (or URL).
2. **Discuss** key takeaways with the human. Ask what they find important or surprising.
3. **Create** a `wiki/sources/` page using the template from `_templates/t-source.md`. Replace all `{{placeholder}}` variables with actual values — never leave template placeholders in a published page.
4. **Update `index.md`** — add to sources section.
5. **Identify** entities, concepts, comparisons mentioned. For each:
   - Page exists → update with new info, **note contradictions explicitly**
   - No page → create a stub (`status: stub`, at minimum: definition + link to source)
6. **Update** relevant overview pages if the source adds significant perspective.
7. **Append** entry to `log.md`.
8. **Report** what was created and updated — use a concise checklist.

### Query

When the human asks a question:

1. **Read `index.md`** to identify relevant pages.
2. **Read** the relevant pages (use parallel reads).
3. **Synthesize** an answer with `[[wikilinks]]` as inline citations.
4. If the answer yields valuable knowledge, **propose filing it** as a new wiki page (comparison, concept, or overview). Ask before creating.

### Lint

When the human says "lint" or "检查":

1. **Scan for**:
   - Contradictions between pages
   - Stale claims superseded by newer sources
   - **Orphan pages** — search with `grep -r "\[\[page-name\]\]" wiki/ index.md` to find pages with zero inbound links
   - Important concepts mentioned but lacking their own page (read index.md + scan recent sources)
   - Missing cross-references between related pages
   - Data gaps that a quick web search could fill
2. **Report** findings as a structured list with `[[links]]`.
3. **Propose fixes**. Apply only after human approval.

### Self-Evolution

If a convention isn't working, **propose updating this CLAUDE.md**. The human decides.

## Best Practices

1. **One source at a time** (default). Batch only when explicitly asked.
2. **Read before write** — always read current page state before editing.
3. **Stubs are fine** — a one-paragraph stub with links beats no page. Mark `status: stub`.
4. **Note contradictions explicitly** (content is Chinese in actual wiki pages, structure shown here):
   ```markdown
   > ⚠️ CONTRADICTION: [[wiki/sources/A]] claims X, but [[wiki/sources/B]] claims Y. Needs verification.
   ```
5. **Keep pages focused** — split if a page exceeds ~300 lines or covers multiple distinct topics.
6. **Dataview-friendly frontmatter** — `type`, `topics`, `status`, `entity_type` are queryable.
7. **Images → `wiki/assets/`** — use `![[wiki/assets/image-name.png]]`.
8. **When unsure, ask** — don't guess about the human's preferences or emphasis.
