---
name: competitors-analysis
description: "Use when running Django competitor analysis against one of the competitors in docs/marketing-strategy/competitors-analysis/index.md. Loads the refined sourcing and analysis prompts, runs the two-step source-map then full-analysis workflow, and produces filled templates ready to commit."
version: 0.2.0
author: Django marketing strategy contributors
license: MIT
metadata:
  hermes:
    tags: [marketing, competitors-analysis, django, strategy, prompts]
    related_skills: []
---

# Competitor analysis

## Overview

This skill drives the Django competitor analysis workflow defined in [`docs/marketing-strategy/competitors-analysis/index.md`](../../../docs/marketing-strategy/competitors-analysis/index.md). It produces **one file per competitor** at `competitors-analysis/<competitor-slug>.md`, containing two sections — **Sourcing** and **Analysis** — plus a header and a review log.

The two prompts below are the refined, context-aware versions of the prompts in `index.md`. Always use these over the rough versions in `index.md`. The docs stay as reference; this skill is the source of truth for how to run the workflow.

## When to use

- A contributor working on the Django marketing strategy asks to "run competitor analysis on X"
- A new competitor enters the shortlist in `index.md` and needs the two-step pass
- Refreshing an existing competitor file that has gone stale (date reviewed > 6 months, or major rebrand/funding event)

**Don't use for:**

- Ad-hoc "what does competitor X say about Y" questions — answer directly, don't run the full workflow
- Landscaping work that crosses more than one competitor at a glance — that belongs in a comparison view, not a single-competitor analysis

## Context the analysis must acknowledge

Every analysis is shaped by the following project context. State this to the analyst at the start of every prompt — it appears in the prompts below.

- **Who this is for.** A Django marketing strategy working group, proposed in the [draft charter](../../../docs/marketing-strategy/governance/marketing-wg-charter.md). The group is a proposal — it does not exist as an active body yet, so this skill assumes a Marketing Working Group will own the work once constituted, not that it owns it today. This is a working document, not a published page.
- **Why we're doing it.** From the [marketing-strategy index](../../../docs/marketing-strategy/index.md): a top-down strategy to focus limited contributor marketing resources on the right problems, and to unblock the [website redesign](https://github.com/django/djangoproject.com/issues/2287) — including information architecture and content refresh across all online properties (social, events, blog, docs).
- **The goal of competitor analysis.** Understand the landscape well enough to make good marketing decisions: copy what works, diverge where Django's strengths lie, close gaps where possible. Developers don't pick frameworks in a vacuum; Django must be comparable.
- **Who we benchmark against.** The competitor shortlist in `index.md` — currently Next.js (± Payload, Supabase), FastAPI, Ruby on Rails, Laravel, plus TBC options (DIY React, NestJS, SvelteKit). Relevance is overlap with Django on: language ecosystem, architectural philosophy, use cases. Confirm the analyst is reviewing one competitor from this shortlist — not an arbitrary choice.
- **Whose audiences we assess.** The analysis identifies and characterizes the **competitor's** audiences — who the competitor explicitly speaks to, in what language, and at what scale. This is a read of the competitor's own targeting, not a projection of Django's audiences onto them. Django's personas are a separate artefact under [`draft/personas.md`](../../../docs/marketing-strategy/draft/personas.md) and are not the lens here.
- **Priority differentiators.** Batteries included, security, stability. The analysis template also covers admin UIs, community/ecosystem, and accessibility (i18n + l10n) — assess every one; flag the three priority axes explicitly in the "Key insight for Django positioning" section.
- **Output style.** Follow the [documentation style guide](../../../docs/contributing/style-guide.md): Sentence case, American English, en dash separators with surrounding spaces, inline links, no links inside headings, callouts only when they change how the reader proceeds. Mark every produced file as a draft with a top-of-page blockquote until it is reviewed by the group that takes on the marketing strategy work.
- **Date and verification.** Information should be correct as of July 2026. We don't need live data, but every claim must cite specific evidence: actual taglines, quotes, star counts, page content. Flag anything the analyst can't verify rather than asserting it.

## Workflow

Run in five phases per competitor, all writing into **one file** at `competitors-analysis/<competitor-slug>.md`. Two phases are human-review gates that must not be skipped.

- **Step 1** — Sourcing section created in `<competitor-slug>.md`
- **Step 2 — Human review of sourcing** (gate, note lands in the file's Review log)
- **Step 3** — Analysis section created in the same `<competitor-slug>.md`
- **Step 4 — Human review of analysis** (gate, note lands in the file's Review log)
- **Step 5** — Final polish: header summary, draft callout, `just format`

The competitor slug is lowercase-kebab: `nextjs.md`, `fastapi.md`, `ruby-on-rails.md`, `laravel.md`, plus `diy-react.md`, `nestjs.md`, `sveltekit.md` once confirmed.

### File structure

Every competitor file uses this shape from the start. Steps 1 and 3 fill in the two sections; steps 2 and 4 add review notes; step 5 polishes the header.

```markdown
# Competitor analysis: <competitor>

> Status: draft — pending review by whoever takes on the marketing strategy work (proposed Marketing Working Group, once constituted). Date reviewed: <date>.

## Summary

<2-3 sentences: who this competitor is, why it's on Django's competitor shortlist, and the most important takeaway. Written in step 5; leave a placeholder until then.>

## Sourcing

<!-- Filled in step 1 from template-competitor-source-map.md, reviewed in step 2 -->

## Analysis

<!-- Filled in step 3 from template-competitor-analysis.md, reviewed in step 4 -->

## Review log

<!-- Every review note appended here in steps 2 and 4 -->
```

### Step 1 — Sourcing

Create the competitor file with the header above (placeholder Summary), then produce a filled `template-competitor-source-map.md` for one competitor from the shortlist and paste it under the `## Sourcing` section.

Use the prompt below.

```text
I need your product marketing expertise to help me with competitor analysis
for the Django web framework. This is part of a new product marketing strategy
for Django; a Marketing Working Group is proposed in
docs/marketing-strategy/governance/marketing-wg-charter.md but is not yet
constituted, so this is working material toward that group forming, not a
document owned or published by it.

Context the analysis must acknowledge:
- This is a working document that feeds a top-down marketing strategy,
  which in turn unblocks the djangoproject.com website redesign,
  information architecture and content refresh, and our other online
  properties (social, events, blog, docs).
- Goal of the competitor analysis: understand the landscape well enough
  to make good marketing decisions. Copy what works, diverge where
  Django's strengths lie, close gaps where possible. Developers don't pick
  frameworks in a vacuum — Django must be comparable.
- Competitor shortlist and relevance criterion (overlap with Django on
  language ecosystem, architectural philosophy, use cases):
  Next.js (± Payload, Supabase), FastAPI, Ruby on Rails, Laravel,
  TBC: DIY React, NestJS, SvelteKit.
- Priority differentiators to surface later in the full analysis:
  batteries included, security, stability.

We are reviewing 5 competitors. Please help me identify relevant sources to
audit for this competitor: [competitor].

Audit across these six surfaces — match each to the corresponding section
in the template:
  1. Website(s) & flagship properties
  2. Documentation
  3. Blog
  4. GitHub presence
  5. Social presence
  6. Public content & events

For each source: name it, give the URL, and describe what it contains
(purpose, key content, navigation role, cadence where relevant). Where a
source signals a specific audience the competitor is speaking to (e.g.
enterprise buyers, individual learners, ops teams), note that — but only
as observation of their positioning, not as a mapping to Django's own
audiences.

Fill the "Why it matters for Django" callout on every section — 2-3
sentences on what's worth benchmarking: IA patterns, conversion framing,
social proof placement, learning journeys, contributor concentration,
platform mix, etc. Be specific to this competitor; don't copy generic
observations across all six.

Be thorough and cross-check sources for authoritativeness (link to primary
URLs, not aggregators). Note the date each source was last reviewed. We do
not need live data but want information correct as of July 2026.

Output format: fill every section of
docs/marketing-strategy/competitors-analysis/template-competitor-source-map.md
and return the completed markdown.
```

**Completion criterion:** the file exists at `competitors-analysis/<competitor-slug>.md` with the header and a placeholder Summary; the `## Sourcing` section contains a filled source map where every section is filled, every source has a date of last review, and every "Why it matters for Django" callout is specific to this competitor.

### Step 2 — Human review of sourcing (gate)

A human reviewer checks the sourcing section before it feeds the analysis. This is not optional — step 3 does not start until the reviewer signs off.

The reviewer (anyone coordinating the marketing strategy work; can be the same person who ran step 1) checks:

- Every source URL resolves to a primary, authoritative property (not an aggregator or a stale mirror).
- The "last reviewed" date is present on every source and is within an acceptable window (defaults to July 2026 baseline; flag anything older).
- Every "Why it matters for Django" callout is specific to this competitor — not boilerplate observations that could apply to any framework.
- The list of sources is plausibly sufficient to answer the analysis template — surface gaps before paying for the analysis step.

The reviewer applies any edits directly inside the `## Sourcing` section, then appends a review note to the `## Review log` section:

```markdown
- Step 2 (sourcing): <name>, <date> — <one-line summary of changes / sign-off>
```

**Completion criterion:** the Review log contains a step 2 sign-off entry, and any edits are applied inside `## Sourcing` before step 3 begins.

### Step 3 — Analysis

Produce a filled `template-competitor-analysis.md` for the same competitor, using the **reviewed** sourcing section from step 2 as the input list of sources. Use the sourcing section as written after the step-2 review — not a stale snapshot. Paste the result under the `## Analysis` section of the competitor file.

Use the prompt below.

```text
I need your product marketing expertise to help me with competitor analysis
for the Django web framework. This is part of creating a new product
marketing strategy for Django. A Marketing Working Group is proposed in
docs/marketing-strategy/governance/marketing-wg-charter.md but is not yet
constituted — this is working material toward that group forming. We are
reviewing 5 competitors. Analyze the product marketing of [competitor] as
a competitor to Django.

Context the analysis must acknowledge:
- This feeds a top-down marketing strategy that will unblock the
  djangoproject.com website redesign, information architecture refresh,
  and our other online properties (social, events, blog, docs).
- Goal: understand the landscape well enough to make good marketing
  decisions — copy what works, diverge where Django's strengths lie, close
  gaps where possible. Developers don't pick frameworks in a vacuum.
- Competitors are chosen for overlap with Django on language ecosystem,
  architectural philosophy, use cases. [competitor] is on the shortlist
  because: [reason — confirm before proceeding].

Identify and characterize [competitor]'s own audiences — who they
explicitly speak to, in what language, and at what scale. Read their
targeting from their materials; do not project Django's audiences onto
them. Django's personas (under docs/marketing-strategy/draft/personas.md)
are a separate artefact and are not a lens for this analysis.

Priority differentiators to surface explicitly in the "Key insight for
Django positioning" closing section: batteries included, security,
stability. The template also asks for positions on admin UIs,
community/ecosystem, and accessibility (i18n + l10n) — assess every one
honestly; these are part of Django's positioning set, not optional.

Here is the mapping of sources for this competitor analysis (this
sourcing has been human-reviewed; use it as the authoritative source list):
[paste the reviewed ## Sourcing contents from steps 1-2]

Base your analysis on the sources in that sourcing section — website(s),
docs, blog, social presence, GitHub, and public content. Cite specific
evidence for each claim: actual taglines, quotes, star counts, page
content. Flag anything you can't verify rather than asserting it. Cite the
source URL inline.

We pick competitors to review that are comparable on capabilities or goals.
Relevance is overlap with Django on language ecosystem, architectural
philosophy, use cases.

Here is the template of what I am after for the output of your analysis,
please fill every section:
docs/marketing-strategy/competitors-analysis/template-competitor-analysis.md

In particular:
- "Audience" section — identify the competitor's top 3 audiences from
  their own materials (homepage, docs landing, case studies, social),
  rank by emphasis, note the audience language they use
  (users / customers / community / developers / partners), and rate the
  community-vs-customer relationship (Community-led / Hybrid /
  Customer-led) with evidence.
- "Top 10 topics" — list the 10 things they talk about consistently across
  website, content, and social. These become the basis for gap analysis.
- "Positions on key Django differentiators" — for each axis (batteries
  included, admin UIs, community/ecosystem, stability, accessibility,
  security): are they claiming it, ignoring it, or positioning against it?
  Quote them where possible.
- "What they say about AI" — call out whether they're leading with AI,
  cautious, or silent, and what specifically they claim.
- "Key insight for Django positioning" — surface the three priority
  differentiators (batteries included, security, stability) plus anything
  else worth owning relative to this competitor.

We do not need live data but want information correct as of July 2026.
Return the completed markdown template.
```

**Completion criterion:** the `## Analysis` section contains a filled `template-competitor-analysis.md` where every section is filled, every claim cites a source URL, unverified claims are flagged, priority differentiators are addressed in the insight section, and the page carries a draft-status blockquote at the top (already in the file header from step 1).

### Step 4 — Human review of analysis (gate)

A human reviewer signs off the analysis before step 5. This is not optional.

The reviewer checks:

- Every claim cites an inline source URL pulled from the reviewed sourcing section (or a follow-on citation added during step 3).
- Unverifiable claims are explicitly flagged, not silently asserted.
- All six differentiator axes are addressed (priority three + admin UIs, community/ecosystem, accessibility), and the AI section is filled with an explicit stance (leading / cautious / silent) plus specific claims.
- The audience read reflects the competitor's own materials, not a projection of Django's audiences.
- The "Key insight for Django positioning" surfaces the three priority differentiators and is actionable for the strategy work downstream.

The reviewer applies any edits directly inside the `## Analysis` section, then appends a review note to the `## Review log` section:

```markdown
- Step 4 (analysis): <name>, <date> — <one-line summary of changes / sign-off>
```

**Completion criterion:** the Review log contains a step 4 sign-off entry, and any edits are applied inside `## Analysis` before step 5 begins.

### Step 5 — Final polish

Finalize the file so it's ready to share or commit. This step does not add new analysis — it polishes the header and verifies the structure.

- Write the **Summary** at the top: 2-3 sentences on who this competitor is, why it's on Django's shortlist, and the most important takeaway from the analysis. If the step 2 or step 4 reviewer changed something that affects downstream interpretation, mention it briefly.
- Confirm the **draft status blockquote** in the header is present and dated.
- Confirm the **Review log** records both step 2 and step 4 reviewers (names, dates, summaries).
- Run `just format` so prettier formats the Markdown consistently.
- Fill the file footer fields if the analysis template includes `### Reviewed by` / `### Date reviewed` — these live inside the `## Analysis` section and should be filled by the step 4 reviewer.

**Completion criterion:** the file at `competitors-analysis/<competitor-slug>.md` has a complete header (title, draft callout, dated), a 2-3 sentence Summary, populated Sourcing and Analysis sections, a Review log with both step 2 and step 4 entries, and passes `just format`.

## Common pitfalls

1. **Splitting a competitor across multiple files.** Each competitor lives in **one** file at `competitors-analysis/<competitor-slug>.md` with `## Sourcing` and `## Analysis` sections. Don't create separate `source-map.md`, `analysis.md`, or `report.md` files — the audit trail is the single file's review log.

2. **Skipping the human-review gates (steps 2 and 4).** These are not optional handoffs. Sourcing must be reviewed before the analysis consumes it, and analysis must be reviewed before step 5 polishes. If the reviewer is not available, the workflow pauses, not skips.

3. **Running the workflow on a competitor not on the shortlist.** Confirm against `index.md` — if the competitor isn't listed, propose adding it there first (with a relevance note) and get a check from whoever is coordinating the marketing strategy work before running.

4. **Generic "Why it matters for Django" callouts.** The step-1 callouts must be specific to the competitor — not the same boilerplate about IA patterns and social proof on all six sections. If you can't find something distinctive, say so.

5. **Asserting unverifiable claims.** Adoption numbers, funding rounds, and team sizes are frequently out of date or wrong. Cite the source URL and the date of review; flag anything you can't verify rather than guessing.

6. **Treating the six differentiator axes as optional.** Only the three priority ones (batteries included, security, stability) get extra weight in the insight section, but admin UIs, accessibility, and community/ecosystem all get assessed in full. Don't skip them because the competitor is quiet on them — "not addressed" is itself an insight for Django's positioning.

7. **Forgetting the AI section.** "What they say about AI" is its own section and high-signal in 2026. Rate it explicitly: leading / cautious / silent, plus the specific claims.

8. **Hard-wrapping the file.** Follow the style guide — let prettier handle wrapping. Run `just format` before committing.

9. **Paraphrasing or abridging review notes.** Step 2 and step 4 review notes land verbatim in `## Review log`. If a reviewer's edits are summarised away, the file loses its audit trail — the whole point of the single-file structure.

10. **Publishing without the draft callout.** Every produced file is a draft until reviewed by whoever takes on the marketing strategy work (the proposed Marketing Working Group, once constituted). Top-of-page blockquote per the style guide, every time.

## Verification checklist

### File structure

- [ ] One file per competitor at `competitors-analysis/<competitor-slug>.md` (lowercase-kebab slug)
- [ ] Header: `# Competitor analysis: <competitor>` → draft-status blockquote → `## Summary` → `## Sourcing` → `## Analysis` → `## Review log`
- [ ] Draft-status blockquote at the top with a date

### Step 1 — Sourcing

- [ ] Placeholder Summary present at top of file (filled in step 5)
- [ ] `## Sourcing` contains a filled source map
- [ ] All six source-map sections present, each with a specific "Why it matters for Django" callout
- [ ] Every source has a URL and a date of last review (July 2026 baseline)

### Step 2 — Human review of sourcing (gate)

- [ ] Reviewer checked URL authoritativeness, dates, callout specificity, and source-list completeness
- [ ] Review log entry recorded: `Step 2 (sourcing): <name>, <date> — <summary>`
- [ ] Any edits applied inside `## Sourcing` before step 3 begins

### Step 3 — Analysis

- [ ] `## Analysis` contains a filled `template-competitor-analysis.md`
- [ ] Built on the reviewed `## Sourcing` section from step 2 (not a stale snapshot)
- [ ] Every section of the analysis template is filled, including AI and all six differentiator axes
- [ ] Every claim cites an inline source URL; unverified claims are flagged
- [ ] Audience read reflects the competitor's own materials, not Django's personas
- [ ] "Key insight for Django positioning" surfaces the three priority differentiators (batteries included, security, stability)

### Step 4 — Human review of analysis (gate)

- [ ] Reviewer checked citations, flagged/unverifiable claims, all differentiator axes, AI stance, audience framing, and insight actionability
- [ ] Review log entry recorded: `Step 4 (analysis): <name>, <date> — <summary>`
- [ ] Any edits applied inside `## Analysis` before step 5 begins
- [ ] `### Reviewed by` and `### Date reviewed` filled in the analysis template footer

### Step 5 — Final polish

- [ ] 2-3 sentence Summary written at the top of the file
- [ ] Draft-status blockquote present and dated
- [ ] Review log records both step 2 and step 4 reviewers with names and dates
- [ ] File passes `just format` (prettier on Markdown)

### Project hygiene

- [ ] If introducing a new competitor, the shortlist in `index.md` is updated with the relevance note
