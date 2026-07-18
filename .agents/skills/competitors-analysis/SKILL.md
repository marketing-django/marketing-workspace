---
name: competitors-analysis
description: "Use when running Django competitor analysis against one of the competitors in docs/marketing-strategy/competitors-analysis/index.md. Loads the refined sourcing and analysis prompts, runs the two-step source-map then full-analysis workflow, and produces a curated comparison-ready analysis backed by a full draft."
version: 0.3.0
author: Django marketing strategy contributors
license: MIT
metadata:
  hermes:
    tags: [marketing, competitors-analysis, django, strategy, prompts]
    related_skills: []
---

# Competitor analysis

## Overview

This skill drives the Django competitor analysis workflow defined in [`docs/marketing-strategy/competitors-analysis/index.md`](../../../docs/marketing-strategy/competitors-analysis/index.md). It produces **two files per competitor**:

- A **curated analysis** at `competitors-analysis/<competitor-slug>.md` — the primary file, terse and comparison-ready, sized so a reviewer can scan one section per screen. This is the file the marketing strategy work actually consumes.
- A **full draft** at `competitors-analysis/<competitor-slug>-full.md` — the long-form, exhaustive working draft that sits behind the curated file. Every claim in the curated file must be traceable to a passage in the full draft. The full draft is the audit trail for the curation choices; it is not published.

The curated file carries the `## Sourcing`, `## Analysis`, and `## Review log` sections in a single place. The full draft carries the same shape but with expansive prose for each field — the material the curated file is carved from.

The two prompts below are the refined, context-aware versions of the prompts in `index.md`. Always use these over the rough versions in `index.md`. The docs stay as reference; this skill is the source of truth for how to run the workflow.

## Output style — non-negotiable

These rules override anything else in the skill or the templates when they conflict:

1. **Terse, comparison-ready cells.** Fill each field of `template-competitor-analysis.md` with **one short paragraph or a compact bulleted list**, not multi-paragraph essays. The benchmark is your own refined comparison table: each cell is scannable in a few lines, every claim is a clause with a link, and reading the whole file should take minutes, not half an hour. A field that runs to three paragraphs is a drafting failure — push the long version into `<competitor-slug>-full.md` and keep the one-liner or list in the curated file.
2. **Every non-trivial claim cites an inline source link.** Use `[claim text](https://primary-url)` form, linking to the primary, authoritative property (the competitor's own site, repo, blog, docs) — not aggregators or third-party surveys when a primary source exists. Taglines, quotes, star counts, release versions, CVE IDs, funding rounds, and adoption figures all require a link. If you quote a sentence, link the quote to the page it came from. If only a third-party source is available, link it and mark the claim `_directional_`. A claim without a link is a claim that needs one.
3. **Quote, don't paraphrase, for headline claims.** When a tagline, a positioning sentence, or a release-post framing is the evidence, quote it verbatim and link the quote to its source URL. Paraphrasing a tagline loses precision and audibility.
4. **Flag rather than assert uncertainty.** Adoption numbers, funding amounts (where undisclosed), team sizes, and follower counts drift fast. Cite the source URL with the date of review; if you cannot authoritatively confirm, mark `_unconfirmed_` or `_directional_` in place — do not guess.
5. **No boilerplate.** "Why it matters for Django" callouts and the differentiator-axes positions must be specific to the competitor — if the same sentence could appear in another competitor's file, rewrite it or delete it.
6. **Style guide applies.** Sentence case headings, American English, en dash "–" with surrounding spaces as separator, inline links only (no bare URLs), no links inside headings, callouts only when they change how the reader proceeds. Mark every produced file as a draft with a top-of-page blockquote. Run `just format` before declaring done.

### What "terse and comparison-ready" looks like

A good curated-file cell (the bar to hit):

> **What they say about stability (LTS, battle-tested)** — **Claiming stability defensively while positioning against it in practice**. The Showcase page leads with "Battle-tested in Production" ([showcase](https://nextjs.org/showcase)), but the release model says otherwise: default branch is `canary` ([repo](https://github.com/vercel/next.js)), 3,753 releases with breaking changes per minor (Next.js 16 broke async params and image defaults, [16 blog](https://nextjs.org/blog/next-16)), and **no LTS, no multi-year support commitment**. The Jul 13, 2026 "formal security release process" post ([blog](https://nextjs.org/blog/next-security-release-program)) reads as a corrective to the late-2025 CVEs. _Versus Django's LTS, DSF-governed cadence — see differentiator axis._

One paragraph, three inline links, a quoted tagline, a flag. Anything longer belongs in `-full.md`.

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

Run in five phases per competitor, writing into **two files**: the curated analysis at `competitors-analysis/<competitor-slug>.md` (primary, terse) and the full draft at `competitors-analysis/<competitor-slug>-full.md` (backup, exhaustive). Two phases are human-review gates that must not be skipped.

- **Step 1** — Sourcing section created in both files (full draft carries the exhaustive source map; curated file carries a compact version with the same URLs).
- **Step 2 — Human review of sourcing** (gate, note lands in the curated file's Review log).
- **Step 3** — Analysis section created in both files. The full draft fills every template field with long-form prose; the curated file distills each field to one paragraph or a compact list with inline source links.
- **Step 4 — Human review of analysis** (gate, note lands in the curated file's Review log).
- **Step 5** — Final polish: header summary on the curated file, draft callout on both, `just format`.

The competitor slug is lowercase-kebab (hyphen-separated): `next-js.md` + `next-js-full.md`, `fastapi.md` + `fastapi-full.md`, `ruby-on-rails.md` + `ruby-on-rails-full.md`, `laravel.md` + `laravel-full.md`. Beacon: the existing `fastapi.md` and `ruby-on-rails.md` are pre-two-tier (single file); when refreshing them, split into the two-file shape and migrate the long-form prose into a new `-full.md`.

### File structure — curated file (primary)

The curated file at `<competitor-slug>.md` is what reviewers and downstream strategy work consume. Every section stays terse — one paragraph or a compact list per field, every claim linked.

```markdown
# Competitor analysis: <competitor>

> Status: draft — pending review by whoever takes on the marketing strategy work (proposed Marketing Working Group, once constituted). Date reviewed: <date>. Full long-form draft: [`<competitor-slug>-full.md`](./<competitor-slug>-full.md).

## Summary

<2-3 sentences: who this competitor is, why it's on Django's competitor shortlist, and the most important takeaway. Written in step 5; leave a placeholder until then.>

## Sourcing

<!-- Compact version of the source map. Same six sections, same URLs as the -full.md draft, but each "What it contains" cell is one line and the "Why it matters for Django" callout is at most two sentences. -->

## Analysis

<!-- Curated version of template-competitor-analysis.md. Each field is one short paragraph or a compact bulleted list with inline source links. Long-form prose lives in <competitor-slug>-full.md. -->

## Review log

<!-- Every review note appended here in steps 2 and 4 -->
```

### File structure — full draft (backup)

The full draft at `<competitor-slug>-full.md` is the exhaustive working material. Same `# Competitor analysis: <competitor>` H1, same draft-status blockquote (pointing back to the curated file), same `## Sourcing`, `## Analysis`, `## Review log` shape — but each field is filled with the long-form prose, full quotes, full reasoning passages, and cull-able candidate claims that the curated file is carved from. This is where multi-paragraph essays, full RSC-protocol explanations, and exhaustive sub-bullets live. Dates and inline source links still apply; the output-style rules above still apply except for the terseness rule.

### Step 1 — Sourcing

Create both files (curated `<competitor-slug>.md` and full `<competitor-slug>-full.md`) with the headers above (the curated file with a placeholder Summary; the full draft with a placeholder Summary pointing back to the curated file). Produce a filled `template-competitor-source-map.md` for one competitor from the shortlist and paste the full version under the full draft's `## Sourcing` section. Then paste a compact version (one-line "What it contains" cells, two-sentence callouts, same URLs) under the curated file's `## Sourcing` section.

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

Every non-trivial claim in your sourcing must carry an inline source
link (`[claim](url)`) to a primary, authoritative URL — not an
aggregator. Taglines and quotes are quoted verbatim and linked to the
page they appear on. Star counts, release versions, funding figures,
and follower counts all require a link and a date of review. If you
cannot authoritatively confirm a figure, mark it `_unconfirmed_` or
_directional_ rather than guessing.

Be thorough and cross-check sources for authoritativeness (link to primary
URLs, not aggregators). Note the date each source was last reviewed. We do
not need live data but want information correct as of July 2026.

Output format: fill every section of
docs/marketing-strategy/competitors-analysis/template-competitor-source-map.md
and return the completed markdown. This becomes the full draft
(`-full.md`); a compact version (one-line cells, two-sentence callouts,
same URLs) goes in the curated file.
```

**Completion criterion:** both files exist (`<competitor-slug>.md` and `<competitor-slug>-full.md`) with their headers and placeholder Summaries; the full draft's `## Sourcing` section contains a filled source map where every section is filled, every source has a URL and a date of last review, and every "Why it matters for Django" callout is specific to this competitor; the curated file's `## Sourcing` section carries a compact version with the same URLs, one-line cells, and two-sentence callouts.

### Step 2 — Human review of sourcing (gate)

A human reviewer checks the sourcing section before it feeds the analysis. This is not optional — step 3 does not start until the reviewer signs off.

The reviewer (anyone coordinating the marketing strategy work; can be the same person who ran step 1) checks:

- Every source URL resolves to a primary, authoritative property (not an aggregator or a stale mirror).
- Every non-trivial claim in the full draft carries an inline source link to a primary URL; unverifiable figures are marked `_unconfirmed_` or `_directional_` rather than asserted.
- The "last reviewed" date is present on every source and is within an acceptable window (defaults to July 2026 baseline; flag anything older).
- Every "Why it matters for Django" callout is specific to this competitor — not boilerplate observations that could apply to any framework.
- The curated file's `## Sourcing` section is a faithful compact version of the full draft — same URLs, one-line cells, two-sentence callouts; no source dropped during curation without an explicit note.
- The list of sources is plausibly sufficient to answer the analysis template — surface gaps before paying for the analysis step.

The reviewer applies any edits directly inside the `## Sourcing` section, then appends a review note to the `## Review log` section:

```markdown
- Step 2 (sourcing): <name>, <date> — <one-line summary of changes / sign-off>
```

**Completion criterion:** the Review log contains a step 2 sign-off entry, and any edits are applied inside `## Sourcing` before step 3 begins.

### Step 3 — Analysis

Produce a filled `template-competitor-analysis.md` for the same competitor, using the **reviewed** sourcing section from step 2 as the input list of sources. Use the sourcing section as written after the step-2 review — not a stale snapshot.

Fill the **full draft** (`<competitor-slug>-full.md`) first — every field of the template with long-form prose, full quotes, full reasoning. Then distil each field into the **curated file** (`<competitor-slug>.md`): one short paragraph or a compact bulleted list per field, every non-trivial claim carrying an inline source link. The distilled version is what reviewers read; the full draft is the audit trail.

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
content. Flag anything you can't verify rather than asserting it. Cite
the source URL inline as `[claim](url)` — every non-trivial claim gets a
link. Quote taglines and positioning sentences verbatim, linked to the
page they appear on. If only a third-party source is available, link it
and mark the claim `_directional_`.

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
  Each topic is a short clause with a link to where it shows up
  (a blog post URL, a homepage section, a release note).
- "Positions on key Django differentiators" — for each axis (batteries
  included, admin UIs, community/ecosystem, stability, accessibility,
  security): are they claiming it, ignoring it, or positioning against it?
  Quote them where possible, and link the quote to its source URL.
- "What they say about AI" — call out whether they're leading with AI,
  cautious, or silent, and what specifically they claim. Link to the
  specific claim (release post, homepage hero, conference talk).
- "Key insight for Django positioning" — surface the three priority
  differentiators (batteries included, security, stability) plus anything
  else worth owning relative to this competitor.

We do not need live data but want information correct as of July 2026.
Return the completed markdown template — that goes in the full draft
(`<competitor-slug>-full.md`). A terse, comparison-ready distilled
version (one paragraph or compact list per field, same inline source
links) goes in the curated file (`<competitor-slug>.md`).
```

**Completion criterion:** the full draft's `## Analysis` section contains a filled `template-competitor-analysis.md` where every section is filled with long-form prose, every claim cites a source URL inline, unverified claims are flagged, priority differentiators are addressed in the insight section, and the page carries a draft-status blockquote at the top. The curated file's `## Analysis` section contains a terse, comparison-ready version — one paragraph or compact list per field, same inline source links — that a reviewer can scan in minutes.

### Step 4 — Human review of analysis (gate)

A human reviewer signs off the analysis before step 5. This is not optional.

The reviewer checks:

- Every claim in the **curated file** cites an inline source URL pulled from the reviewed sourcing section (or a follow-on citation added during step 3). A claim without a link is sent back.
- The curated file's fields are genuinely terse — one paragraph or a compact list per field. Any field running to three paragraphs is sent back (push it to the full draft).
- Every claim in the **full draft** similarly carries an inline source URL; long-form prose is acceptable here but a missing link is not.
- Unverifiable claims are explicitly flagged (`_unconfirmed_` / `_directional_`), not silently asserted.
- All six differentiator axes are addressed (priority three + admin UIs, community/ecosystem, accessibility), and the AI section is filled with an explicit stance (leading / cautious / silent) plus specific claims with links.
- The audience read reflects the competitor's own materials, not a projection of Django's audiences.
- The "Key insight for Django positioning" surfaces the three priority differentiators and is actionable for the strategy work downstream.
- Every claim in the curated file is traceable to a passage in the full draft (spot-check two or three).

The reviewer applies any edits directly inside the `## Analysis` section, then appends a review note to the `## Review log` section:

```markdown
- Step 4 (analysis): <name>, <date> — <one-line summary of changes / sign-off>
```

**Completion criterion:** the Review log contains a step 4 sign-off entry, and any edits are applied inside `## Analysis` before step 5 begins.

### Step 5 — Final polish

Finalize both files so they're ready to share or commit. This step does not add new analysis — it polishes the headers and verifies the structure.

- Write the **Summary** at the top of the curated file: 2-3 sentences on who this competitor is, why it's on Django's shortlist, and the most important takeaway from the analysis. If the step 2 or step 4 reviewer changed something that affects downstream interpretation, mention it briefly.
- Confirm the **draft status blockquote** is present and dated on both files. The curated file's blockquote links to the full draft; the full draft's blockquote links back to the curated file.
- Confirm the **Review log** in the curated file records both step 2 and step 4 reviewers (names, dates, summaries). The full draft's Review log mirrors the curated one.
- Run `just format` so prettier formats both files consistently.
- Fill the file footer fields if the analysis template includes `### Reviewed by` / `### Date reviewed` — these live inside the `## Analysis` section of the curated file and should be filled by the step 4 reviewer. The full draft carries its own footer pointing to the same reviewer/date.

**Completion criterion:** both files at `competitors-analysis/<competitor-slug>.md` and `competitors-analysis/<competitor-slug>-full.md` have complete headers (title, draft callout, dated, cross-linked to each other), the curated file has a 2-3 sentence Summary, populated Sourcing and Analysis sections (compact in the curated file, exhaustive in the full draft), a Review log with both step 2 and step 4 entries in both files, and both pass `just format`.

## Common pitfalls

1. **Mixing up which file is primary.** The curated file at `<competitor-slug>.md` is what reviewers and downstream strategy work consume; the full draft at `<competitor-slug>-full.md` is the audit trail. Both must exist, both must be saved, and the curated file's blockquote must link to the full draft (and vice versa). Don't produce only the full draft, and don't let the curated file drift away from the full draft's content — every curated claim must trace to a passage in the full draft.

2. **Producing only long-form prose in the curated file.** The curated file must be terse: one paragraph or a compact bulleted list per field. If a field runs to three paragraphs, that paragraph belongs in the full draft and the curated cell should be a clause with a link. A curated file that is as long as the full draft is a drafting failure.

3. **Skipping the human-review gates (steps 2 and 4).** These are not optional handoffs. Sourcing must be reviewed before the analysis consumes it, and analysis must be reviewed before step 5 polishes. If the reviewer is not available, the workflow pauses, not skips.

4. **Running the workflow on a competitor not on the shortlist.** Confirm against `index.md` — if the competitor isn't listed, propose adding it there first (with a relevance note) and get a check from whoever is coordinating the marketing strategy work before running.

5. **Generic "Why it matters for Django" callouts.** The step-1 callouts must be specific to the competitor — not the same boilerplate about IA patterns and social proof on all six sections. If you can't find something distinctive, say so.

6. **Claims without inline source links.** Every non-trivial claim — taglines, quotes, star counts, release versions, CVE IDs, funding rounds, adoption figures — must carry an inline `[claim](url)` link to a primary, authoritative URL. A bare assertion with no link is a claim that needs a link; send it back. Paraphrasing a tagline instead of quoting the verbatim wording (with a link) loses precision — quote the headline claims.

7. **Asserting unverifiable claims.** Adoption numbers, funding rounds, and team sizes are frequently out of date or wrong. Cite the source URL and the date of review; mark anything you can't verify as `_unconfirmed_` or `_directional_` rather than guessing.

8. **Treating the six differentiator axes as optional.** Only the three priority ones (batteries included, security, stability) get extra weight in the insight section, but admin UIs, accessibility, and community/ecosystem all get assessed in full. Don't skip them because the competitor is quiet on them — "not addressed" is itself an insight for Django's positioning.

9. **Forgetting the AI section.** "What they say about AI" is its own section and high-signal in 2026. Rate it explicitly: leading / cautious / silent, plus the specific claims, each linked to a source URL (release post, homepage hero, conference talk).

10. **Hard-wrapping the file.** Follow the style guide — let prettier handle wrapping. Run `just format` before committing, on both files.

11. **Paraphrasing or abridging review notes.** Step 2 and step 4 review notes land verbatim in `## Review log` of the curated file; the full draft carries a copy. If a reviewer's edits are summarised away, the file loses its audit trail — the whole point of the dual-file structure.

12. **Publishing without the draft callout.** Every produced file is a draft until reviewed by whoever takes on the marketing strategy work (the proposed Marketing Working Group, once constituted). Top-of-page blockquote per the style guide, every time, on both files. The curated file's blockquote links to the full draft; the full draft's blockquote links back.

## Verification checklist

### File structure

- [ ] Two files per competitor at `competitors-analysis/<competitor-slug>.md` (curated) and `competitors-analysis/<competitor-slug>-full.md` (full draft), both lowercase-kebab slug
- [ ] Curated file header: `# Competitor analysis: <competitor>` → draft-status blockquote linking to `-full.md` → `## Summary` → `## Sourcing` → `## Analysis` → `## Review log`
- [ ] Full draft header: same H1 → draft-status blockquote linking back to the curated file → same section order
- [ ] Draft-status blockquote at the top of both files, dated

### Step 1 — Sourcing

- [ ] Placeholder Summary present at top of curated file (filled in step 5); full draft's Summary also a placeholder pointing back to the curated file
- [ ] Full draft's `## Sourcing` contains a filled source map
- [ ] Curated file's `## Sourcing` is a compact version of the full draft — one-line "What it contains" cells, two-sentence "Why it matters for Django" callouts, same URLs
- [ ] All six source-map sections present in both, each with a specific "Why it matters for Django" callout
- [ ] Every source has a URL and a date of last review (July 2026 baseline)

### Step 2 — Human review of sourcing (gate)

- [ ] Reviewer checked URL authoritativeness, inline source-link coverage on claims, dates, callout specificity, curated↔full fidelity, and source-list completeness
- [ ] Review log entry recorded in the curated file: `Step 2 (sourcing): <name>, <date> — <summary>`; full draft carries a copy
- [ ] Any edits applied inside `## Sourcing` of both files before step 3 begins

### Step 3 — Analysis

- [ ] Full draft's `## Analysis` contains a filled `template-competitor-analysis.md` with long-form prose per field
- [ ] Curated file's `## Analysis` contains a terse, comparison-ready distillation — one paragraph or compact list per field, same inline source links
- [ ] Both built on the reviewed `## Sourcing` section from step 2 (not a stale snapshot)
- [ ] Every section of the analysis template is filled in both, including AI and all six differentiator axes
- [ ] Every non-trivial claim cites an inline source URL `[claim](url)` in both files; unverified claims are flagged
- [ ] Taglines, positioning sentences, and quotes are verbatim and linked to the page they appear on
- [ ] Audience read reflects the competitor's own materials, not Django's personas
- [ ] "Key insight for Django positioning" surfaces the three priority differentiators (batteries included, security, stability)

### Step 4 — Human review of analysis (gate)

- [ ] Reviewer checked inline citations on every curated claim, terseness of the curated file (no three-paragraph fields), full-draft inline citations, flagged/unverifiable claims, all differentiator axes, AI stance, audience framing, and insight actionability
- [ ] Spot-check: 2–3 curated claims trace to a passage in the full draft
- [ ] Review log entry recorded in the curated file: `Step 4 (analysis): <name>, <date> — <summary>`; full draft carries a copy
- [ ] Any edits applied inside `## Analysis` of both files before step 5 begins
- [ ] `### Reviewed by` and `### Date reviewed` filled in the curated file's analysis template footer; full draft's footer mirrors them

### Step 5 — Final polish

- [ ] 2-3 sentence Summary written at the top of the curated file
- [ ] Draft-status blockquote present and dated on both files, cross-linked
- [ ] Review log records both step 2 and step 4 reviewers with names and dates, in both files
- [ ] Both files pass `just format` (prettier on Markdown)

### Project hygiene

- [ ] If introducing a new competitor, the shortlist in `index.md` is updated with the relevance note
