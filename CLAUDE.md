# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What This Repo Is

An [Obsidian](https://obsidian.md) vault that serves as the documentation site for the [Breadcrumbs plugin](https://github.com/SkepticMystic/breadcrumbs). Published at https://publish.obsidian.md/breadcrumbs-docs.

No build step, no tests, no package.json. All content is Markdown. "Deploying" means syncing via Obsidian Publish through the Obsidian app.

## Content Structure

- **`Home.md`** — entry point / landing page
- **`Concepts.md`** — core terminology (Graph, Edge Attributes, Traversal, Edge Sorters)
- **`Edge Fields.md`** / **`Field Groups.md`** — how users define typed link fields
- **`Explicit Edge Builders/`** — docs for each builder (Typed Links, Folder Notes, Tag Notes, etc.)
- **`Implied Edge Builders/`** — docs for inferred/transitive relationships
- **`Views/`** — Matrix, Tree, Trail, Page, Codeblocks, Previous-Next views
- **`Commands/`** — each Obsidian command documented separately
- **`Suggesters/`** — autocomplete helpers
- **`Guides/`** — use-case walkthroughs (Daily Notes, Personal Relationship Management)
- **`Announcements/`** — release notes / changelog entries
- **`Images/`** — screenshots referenced via Obsidian wikilinks (`![[filename.png]]`)

## Key Conventions

### Obsidian Markdown
- Internal links use wikilink syntax: `[[Note Name]]` or `[[Note Name|display text]]`
- Image embeds: `![[Image Name.png]]`
- Callouts use `> [!TYPE]` syntax (INFO, EXAMPLE, WARNING, etc.)
- Frontmatter YAML for aliases and metadata (e.g., `aliases: [Reference]`)

### Cross-linking
- Notes reference each other liberally via wikilinks — check existing notes for the canonical link target name before adding new links
- `next:: [[note]]` inline Dataview fields are used for sequential navigation (README lists this as a TODO to add more)

### Installed Plugins (relevant to editing)
- **obsidian-linter** — linting rules apply; keep Markdown clean
- **breadcrumbs** — the plugin being documented is also installed in this vault for dogfooding
- **copy-publish-url** / **cmdr** — publish workflow helpers (not relevant to content editing)

## Open TODOs (from README)

- Add more images for the Views section
- Add `next:: [[note]]` fields to each note
- Search "TODO" in notes for smaller tasks
