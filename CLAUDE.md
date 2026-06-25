# CLAUDE.md — Lope Docs

Context for Claude when working in this repo. Keep it current as the docs evolve.

## What this repo is

The **public documentation site for Lope** (the recruiter-first product formerly
codenamed **Kaktus**). It is a **Mintlify** site. Content is written for
**recruiters, sourcers, and client partners — not engineers**.

- Repo / remote: `dfwteinos/docs`, default branch `main`.
- Framework: Mintlify (`mint` CLI), theme `mint`, brand primary `#9E2DFF`.
- Hosting: the connected Mintlify project **auto-deploys on every push to `main`**.
  There is no manual build/deploy step.
- The product code lives next door in `../KaktusProd` (see its own `CLAUDE.md`).
  Use it to verify real UI labels and flows — but never leak engineering detail
  (schemas, env vars, file paths) into recruiter-facing pages.

## How navigation works (important)

`docs.json` is the single source of truth for the site's nav. **A page only
appears on the site if it is listed in `docs.json`.** Creating an `.mdx` file is
not enough — add it to the right group under `navigation.tabs`.

Two tabs: **Lope Docs** (main) and **Changelog**.

### Active content (in nav, edit these)
- `projects/lope/getting-started/` — welcome, lope-overview
- `projects/lope/daily-work/` — automation-integrations, lope-pipeline
- `projects/lope/functionalities/` — candidates-data, ai-features, teamspaces, collaboration
- Guides (Import Candidates): `1-manual-insertion`, `2-chrome-extension`, `3-cv-import`, `4-csv-import`
- Core Concepts: `workspaces`, `teamspaces`, `clients`, `jobs`
- AI Scout: `how-ai-scout-works`, `writing-effective-search-prompts`, `understanding-match-scores-and-explainability`
- Integrations & Settings: `inviting-team-members`, `custom-fields-for-candidates`
- `changelog/changelog`

### Orphan / scaffolding (NOT in nav — leftover Mintlify starter template)
`quickstart`, `development`, `add-candidates-manually`, `import-from-csv`,
`import-from-cvs`, `from-linked-in-chrome-extension`, and everything under
`api-reference/`, `essentials/`, `ai-tools/`, `snippets/`. Don't treat these as
live docs. The `api-reference/` section still uses developer blocks
(`ResponseField`, `ParamField`, `CodeGroup`) from the template — that's the one
place those belong; don't copy that style into recruiter pages.

## Writing conventions

The full style guide is `.cursor/rules.md`. Summary:

- **Audience:** busy recruiters comfortable with SaaS, not with engineering jargon.
- **Voice:** conversational, confident, plain language. Short sentences (under 20 words).
  Lead every page with a one-paragraph value/outcome statement, then 3–5 scannable
  H2 sections. Headings start at H2.
- **Focus on what users see** (tabs, buttons, dashboards) and recruiter goals
  ("save time sourcing," "keep clients informed"). No code, API refs, schemas,
  CLI commands, or deployment talk in recruiter pages.
- Descriptive link text ("View the Chrome extension guide"), not "click here".
- Images always wrapped in `<Frame>` with descriptive alt text.

### Frontmatter
Every page needs YAML frontmatter. `title` is required; `description` strongly
recommended (used for SEO + search). Optional: `sidebarTitle`, `icon` (Font
Awesome name, e.g. `icon: user-plus`).

```mdx
---
title: "Clients"
description: "Clients are companies or hiring entities you recruit for."
sidebarTitle: "Clients"
---
```

### Components (Mintlify MDX)
Recruiter-friendly: `<Card>`/`<Columns>`/`<CardGroup>`, `<Steps>`/`<Step>`,
`<Note>` `<Tip>` `<Warning>` `<Check>` `<Info>`, `<Frame>`, `<Accordion>`/
`<AccordionGroup>`, `<Tooltip>`. Use `<Steps>` only for short hands-on flows
(fewer than 5 steps). Avoid developer blocks (`CodeGroup`, `ResponseField`, `ParamField`,
`RequestExample`, `ResponseExample`) outside `api-reference/`.

The changelog uses `Update` blocks with `label` and `tags` props, newest first.

## Previewing locally
```
npm i -g mint
mint dev          # serves http://localhost:3000, hot-reloads on save
```
If a page 404s locally, check it's listed in `docs.json`. `mint update` if the
CLI misbehaves.

## Git workflow & gotchas

- **Default workflow: Claude edits files; the human reviews and runs
  `git commit` / `git push`.** Confirm before changing this.
- **Line-ending churn:** the working tree may show ~all files as "modified" with
  whole-file diffs (equal insertions/deletions). That's CRLF↔LF noise, not real
  edits (`core.fileMode` is already `false`). Don't commit that churn — it buries
  real changes. To fix the root cause, normalize with a `.gitattributes`
  (`* text=auto`) or set `git config core.autocrlf true` and re-checkout. When
  editing, preserve a file's existing line endings.
- A stale `.git/index.lock` has been seen (likely held by Cursor/another tool);
  it can block git commands until removed by the human.
- `.gitignore` excludes `KaktusProd/` and `Lope_zip/` (brand assets).

## Terminology
- **Lope** = current product name. **Kaktus** = old internal codename; some older
  pages and the style-guide title still say Kaktus — prefer "Lope" in new copy.
- Hierarchy users see: **Workspace → Teamspace → Client → Job → Candidate**.
- Core features to name correctly: **AI Scout** (search), **AI Notetaker**
  (interview transcription), **Smart Reports**, **Chrome extension**,
  **2-way ATS integrations** (e.g. Bullhorn, Workable).
