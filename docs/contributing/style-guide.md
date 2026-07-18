# Documentation style guide

This style guide defines the standard we aim for across the project documentation – the README, MkDocs site, contributor docs, working documents, and everything else. Use it as the default for all new content, and as a reference when revising existing pages.

## Design goals

- **Accurate, discoverable, maintainable.** Docs should describe the project as it is, be easy to find, and be cheap to keep up to date.
- **Concise and practical.** Get to the point quickly. Prefer concrete examples over long prose explanations. Every page should help the reader accomplish something or understand a concept they need.

## Tone of voice

We write in a **direct, professional, and approachable** tone. The guiding principle: help the reader move forward with as little friction as possible.

- Contractions are acceptable where they read naturally: "doesn't", "won't", "It's", "That's", "Don't". Do not force them, and do not avoid them.
- Avoid overly formal or academic phrasing. Sentences stay direct and plain. Prefer "use" over "utilise", "start" over "commence", "show" over "demonstrate" (except where "demonstrate" is the precise word).
- Be honest about limitations and trade-offs. We call out work in progress, open questions, and decisions still to be made explicitly rather than glossing over them.

## Target audience

The documentation is written for **contributors** working on marketing for Django – members of the Marketing Working Group, volunteers on the website redesign, and the broader Django community.

- We assume familiarity with Django as a project and an interest in marketing, communication, or web content work. We do not assume a developer background.
- Contributor docs assume familiarity with the project's development tooling (`uv`, `just`, `mkdocs`). We link to those tools' documentation rather than re-explaining them.
- Where a process touches Django project governance or infrastructure (`djangoproject.com`, DSF working groups, Slack channels), we name the relevant team and link to its canonical source rather than describing it from scratch.

## Content structure

### Page layout

Every page follows a predictable shape:

1. **H1 page title** – concise, descriptive, in Sentence case.
2. **Opening paragraph** – one or two sentences that tell the reader what the page covers and whether they are in the right place.
3. **Sections** – H2 for major sections, H3 for sub-sections within an H2. Use H4 and below sparingly; if a section needs five levels, consider splitting the page.

### Code examples

- Code blocks use fenced syntax (` ``` `) with a language identifier: `sh`, `bash`, `txt`, `markdown`.
- Examples should be self-contained where possible: a reader should be able to copy, paste, and run them.
- Inline comments inside code blocks are acceptable when they clarify non-obvious lines, but keep them short. Match the comment style used in the surrounding codebase (see [Contribution Guidelines](../CONTRIBUTING.md)).
- Prefer showing the happy path first. Document edge cases, fallbacks, and advanced configuration in a separate sub-section or callout.

### Tables

- Use Markdown tables for structured reference data: sub-project scope, working group responsibilities, channel mappings, governance decision rights.
- Every column should have a header row.
- Keep table cells short. If a cell needs a paragraph of explanation, move it into prose below the table.

### Callouts and blockquotes

We use Markdown blockquotes for short, scoped callouts:

- **Draft or status notes** at the top of a page:

  ```markdown
  > ⚠️ This page is a **draft**. It reflects the working group's current thinking and may change without notice.
  ```

- **Source attribution** for content imported from elsewhere:

  ```markdown
  > Source: [Marketing Working Group charter](https://github.com/django/dsf-working-groups/pull/60). Last updated 2026-07-18.
  ```

- **Closing remarks** at the end of a procedure:

  ```markdown
  > As a last step, post a note in the `#marketing` Slack channel so other contributors can review the change.
  ```

Keep callouts to one or two sentences. Use them when the information directly affects how the reader proceeds, not as a general aside.

## Links

- Use **inline links** in prose. Prefer `[link text](url)` over bare URLs.
- Link to internal documentation with **relative paths**: `[contribution guidelines](CONTRIBUTING.md)`, `[marketing strategy index](../marketing-strategy/index.md)`.
- On first or prominent mention of a key concept, team, or external resource, link to its canonical source. Repeat links only when the repetition genuinely helps scanning in a longer section.
- External links should point to **official, stable resources**: the Django project's website, the DSF working groups repository, the Django Forum, official tool documentation. Avoid linking to transient content (forum threads, personal gists) unless there is no canonical alternative.
- Link text should be descriptive. Avoid "click here" or "this link". Prefer the title of the target page.
- Do not add links inside headings. They are harder to identify for screen reader users and break heading navigation.

## Headings and titles

- **H1** is used exactly once per page, for the page title.
- **H2** is the primary sectioning level within a page.
- **H3** is used for sub-sections within an H2. Use deeper levels only when the content genuinely requires it.
- Headings use **Sentence case**: "Getting started", "Website redesign", "Working group charter", not "Getting Started" or "Working Group Charter".
- Heading text is **plain**. Do not apply bold, italics, code formatting, or links inside headings.
- Prefer **noun phrases** for reference and conceptual pages ("Knowledge base", "Project architecture", "Governance"). Prefer **verb-first phrasing** for task-oriented pages or sub-sections within procedures ("Draft a strategy", "Update website content").
- Keep headings concise. A heading should fit on a single line and give the reader enough context to decide whether to read the section.

## Terminology and language choices

### Spelling

We use **American English** spelling in prose: `normalization`, `organized`, `behavior`, `color`, `center`. This is consistent with the spelling used in Django's own documentation.

Exceptions:

- **Proper nouns and product names** keep their own spelling regardless of locale.
- When a prose sentence refers to a specific code symbol, use the symbol's exact spelling.
- Content imported from external sources (for example, a charter from the `django/dsf-working-groups` repository) keeps its original spelling. Record this with `source:` and `last_updated:` front matter rather than rewriting the source.

### Capitalization

- **Sentence case** for headings and titles, always.
- Capitalize proper nouns: Django, Django Software Foundation, Wagtail, Python, Markdown, MkDocs.
- "the workspace" is lowercase – it is the project's shorthand for `marketing-workspace`, not a proper noun.
- Sub-project names are capitalized when announced or listed ("Knowledge base", "Marketing strategy", "Website redesign"), lowercase when used inline ("the knowledge base", "the marketing strategy", "the website redesign").
- Working group names are capitalized. Spell the name out in full on first mention ("Marketing Working Group"), with the abbreviation in parentheses ("Marketing Working Group (WG)") only if you will use it later; subsequent mentions can use the short form ("the marketing WG") or the abbreviation ("the WG"). Generic references stay lowercase ("a working group", "other working groups").
- Specific governance bodies and roles are capitalized: "the Steering Council", "the Board", "the Chair", "Co-Chair".

### Punctuation

- Use an **en dash** (`–`) with surrounding spaces as a separator in lists and inline definitions, matching the existing docs:

  ```markdown
  - **Draft outline** – the high-level structure of the marketing strategy.
  - **Governance** – documents that establish how the working group operates.
  ```

- Avoid hard-wrapping lines in prose. Let the editor handle wrapping, and run `just format` (prettier) before committing so Markdown is formatted consistently.
- Comments in code blocks follow the same rule as source code: avoid hard-wrapping, except at full stops or other natural punctuation breaks.

### Referring to the reader

- We say "you" and "your". We do not say "the user" when addressing the reader of the documentation.
- "Contributors" or "members" refers to other people working on this workspace, not the reader: "Django contributors", "working group members", "community members".

### Referring to the project

- "the workspace" – the preferred shorthand for `marketing-workspace` in prose.
- "this project" – acceptable when distinguishing from the Django project itself.
- "Django" – refers to the open source web framework. Always capitalized.
- "the Django project" – refers to the open source effort as a whole (governance, community, release management). Lowercase "project".
- "the DSF" – short form for the Django Software Foundation, after first mention.

### Django marketing terminology

- **Django Software Foundation (DSF)** – spelled out on first mention, abbreviated thereafter.
- **Marketing Working Group** – the team responsible for marketing strategy and activities. Always spelled out on first mention; "the marketing WG" or "the WG" afterwards.
- **djangoproject.com** – lowercase URL form when referring to the website. Do not capitalize the domain.
- **Slack** – capitalized, refers to the DSF Slack workspace. Mention specific channels with the hash in code formatting: `` `#marketing` ``, `` `#website` ``.
- **Django Forum** – capitalized, the official discussion forum at `forum.djangoproject.com`.
- **knowledge base / marketing strategy / website redesign** – the three sub-projects of this workspace. See [Capitalization](#capitalization) for spelling rules.
- **blog** – lowercase. The official Django blog hosted on `djangoproject.com`.

### Modal verbs

- Use **"can"** for capability: "You can join the `#marketing` channel on the DSF Slack."
- Use **"should"** for recommendations: "Draft documents should be marked as drafts with a callout at the top of the page."
- Reserve **"must"** for hard requirements, especially around governance: "Page updates that change the marketing strategy must be reviewed by the Marketing Working Group before publication."
- Use **"may"** for possibility or optional behaviors: "You may want to share the change in the next working group meeting."

## Warnings, notes, and edge cases

We document limitations and open questions directly in the relevant page, not hidden in a separate caveats section.

- State limitations as facts, not apologies: "There is no workaround if a working group decision is still pending – the page stays in draft until then."
- Call out **draft** or **work in progress** status at the top of the page with a blockquote, so readers see the status before investing in the content. Add `source:` and `last_updated:` front matter when the page mirrors an external document.
- When a process differs between working groups or channels, say so explicitly: "Website content reviews are handled by the website WG, while marketing campaign content is reviewed by the marketing WG."
- Governance-relevant information lives alongside the relevant page and is cross-linked from [CONTRIBUTING.md](../CONTRIBUTING.md) where it affects how contributors collaborate.
