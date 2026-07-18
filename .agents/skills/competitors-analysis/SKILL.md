---
name: competitors-analysis
description: "Use when running Django competitor analysis against one of the competitors in docs/marketing-strategy/competitors-analysis/index.md. Loads the refined sourcing and analysis prompts, runs the two-step source-map then full-analysis workflow, and produces filled templates ready to commit."
version: 0.1.0
author: Django Marketing Working Group
license: MIT
metadata:
  hermes:
    tags: [marketing, competitors-analysis, django, strategy, prompts]
    related_skills: []
---

# Competitor analysis

## Overview

This skill drives the Django competitor analysis workflow defined in [`docs/marketing-strategy/competitors-analysis/index.md`](../../../docs/marketing-strategy/competitors-analysis/index.md). It produces two artefacts per competitor:

1. A **source map** (`template-competitor-source-map.md`) — the auditable list of sources to draw from.
2. A **competitor analysis** (`template-competitor-analysis.md`) — the full positioning, messaging, and capacity review.

The two prompts below are the refined, context-aware versions of the prompts in `index.md`. Always use these over the rough versions in `index.md`. The docs stay as reference; this skill is the source of truth for how to run the workflow.

## When to use

- A Marketing Working Group contributor asks to "run competitor analysis on X"
- A new competitor enters the shortlist in `index.md` and needs the two-step pass
- Refreshing an existing competitor analysis that has gone stale (date reviewed > 6 months, or major rebrand/funding event)

**Don't use for:**

- Ad-hoc "what does competitor X say about Y" questions — answer directly, don't run the full workflow
- Landscaping work that crosses more than one competitor at a glance — that belongs in a comparison view, not a single-competitor analysis

## Context the analysis must acknowledge

Every analysis is shaped by the following project context. State this to the analyst at the start of every prompt — it appears in the prompts below.

- **Who this is for.** The Django Software Foundation's Marketing Working Group, which owns the marketing strategy per the [charter](../../../docs/marketing-strategy/governance/marketing-wg-charter.md). This is a working document, not a published page.
- **Why we're doing it.** From the [marketing-strategy index](../../../docs/marketing-strategy/index.md): a top-down strategy to focus limited contributor marketing resources on the right problems, and to unblock the [website redesign](https://github.com/django/djangoproject.com/issues/2287) — including information architecture and content refresh across all online properties (social, events, blog, docs).
- **The goal of competitor analysis.** Understand the landscape well enough to make good marketing decisions: copy what works, diverge where Django's strengths lie, close gaps where possible. Developers don't pick frameworks in a vacuum; Django must be comparable.
- **Who we benchmark against.** The competitor shortlist in `index.md` — currently Next.js (± Payload, Supabase), FastAPI, Ruby on Rails, Laravel, plus TBC options (DIY React, NestJS, SvelteKit). Relevance is overlap with Django on: language ecosystem, architectural philosophy, use cases. Confirm the analyst is reviewing one competitor from this shortlist — not an arbitrary choice.
- **The lens we evaluate through.** The five personas in [`draft/personas.md`](../../../docs/marketing-strategy/draft/personas.md) — Alex (donor), Brooklyn (marketing exec / decision-maker), Zain (new developer), Danny (existing Django developer), Erica (ecosystem contributor). Brooklyn's evaluation axes are particularly load-bearing for competitor analysis: **relevancy, reliance, community/support, ease of hiring**.
- **Priority differentiators.** Batteries included, security, stability. The analysis template also covers admin UIs, community/ecosystem, and accessibility (i18n + l10n) — assess every one; flag the three priority axes explicitly in the "Key insight for Django positioning" section.
- **Output_style.** Follow the [documentation style guide](../../../docs/contributing/style-guide.md): Sentence case, American English, en dash separators with surrounding spaces, inline links, no links inside headings, callouts only when they change how the reader proceeds. Mark every produced analysis as a draft with a top-of-page blockquote until the Marketing WG reviews it.
- **Date and verification.** Information should be correct as of July 2026. We don't need live data, but every claim must cite specific evidence: actual taglines, quotes, star counts, page content. Flag anything the analyst can't verify rather than asserting it.

## Workflow

Run in two steps, per competitor. Step 1 must complete before step 2 — the source map is the input to the analysis.

### Step 1 — Source map (sourcing)

Produce a filled `template-competitor-source-map.md` for one competitor from the shortlist.

Use the prompt below. Save the output as `competitors-analysis/<competitor-slug>/source-map.md`.

```text
I need your product marketing expertise to help me with competitor analysis
for the Django web framework, as part of a new product marketing strategy
owned by the Django Software Foundation's Marketing Working Group.

Context the analysis must acknowledge:
- This is a working document that feeds a top-down marketing strategy, which
  in turn unblocks the djangoproject.com website redesign, information
  architecture and content refresh, and our other online properties (social,
  events, blog, docs).
- Goal of the competitor analysis: understand the landscape well enough to
  make good marketing decisions. Copy what works, diverge where Django's
  strengths lie, close gaps where possible. Developers don't pick frameworks
  in a vacuum — Django must be comparable.
- Competitor shortlist and relevance criterion (overlap with Django on
  language ecosystem, architectural philosophy, use cases):
  Next.js (± Payload, Supabase), FastAPI, Ruby on Rails, Laravel,
  TBC: DIY React, NestJS, SvelteKit.
- We evaluate every competitor through Django's five personas (Alex/donor,
  Brooklyn/marketing exec, Zain/new developer, Danny/existing developer,
  Erica/ecosystem contributor). Brooklyn's evaluation axes — relevancy,
  reliance, community/support, ease of hiring — are the primary lens.
- Priority differentiators to surface later: batteries included, security,
  stability.

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
(purpose, key content, navigation role, cadence where relevant).

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

**Completion criterion:** every section of the template is filled, every source has a date of last review, and "Why it matters for Django" is specific to this competitor on all six sections.

### Step 2 — Competitor analysis

Produce a filled `template-competitor-analysis.md` for the same competitor, using the step-1 source map as the input list of sources.

Use the prompt below. Save the output as `competitors-analysis/<competitor-slug>/analysis.md`.

```text
I need your product marketing expertise to help me with competitor analysis
for the Django web framework. This is part of creating a new product
marketing strategy for Django, owned by the Marketing Working Group of the
Django Software Foundation. We are reviewing 5 competitors. Analyze the
product marketing of [competitor] as a competitor to Django.

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

Evaluate through Django's five personas (Alex/donor, Brooklyn/marketing
exec, Zain/new developer, Danny/existing developer, Erica/ecosystem
contributor). Brooklyn's evaluation axes — relevancy, reliance,
community/support, ease of hiring — define what "good" looks like for the
positioning sections of the analysis.

Priority differentiators to surface explicitly in the "Key insight for
Django positioning" closing section: batteries included, security,
stability. The template also asks for positions on admin UIs,
community/ecosystem, and accessibility (i18n + l10n) — assess every one
honestly; these are part of Django's positioning set, not optional.

Here is the mapping of sources I think are relevant for this competitor
analysis:
[paste the completed source map from step 1]

Base your analysis on the sources in that source map — website(s), docs,
blog, social presence, GitHub, and public content. Cite specific evidence
for each claim: actual taglines, quotes, star counts, page content.
Flag anything you can't verify rather than asserting it. Cite the source
URL inline.

We pick competitors to review that are comparable on capabilities or goals.
Relevance is overlap with Django on language ecosystem, architectural
philosophy, use cases.

Here is the template of what I am after for the output of your analysis,
please fill every section:
docs/marketing-strategy/competitors-analysis/template-competitor-analysis.md

In particular:
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

**Completion criterion:** every section of `template-competitor-analysis.md` is filled, every claim cites a source URL, unverified claims are flagged, priority differentiators are addressed in the insight section, and the page carries a draft-status blockquote at the top.

## Common pitfalls

1. **Skipping the source map.** Step 2 without step 1 produces an analysis with no auditable trail. Always complete the source map first and reference it as the source list in the analysis prompt.

2. **Running the workflow on a competitor not on the shortlist.** Confirm against `index.md` — if the competitor isn't listed, propose adding it there first (with a relevance note) and get Marketing WG sign-off before running.

3. **Generic "Why it matters for Django" callouts.** The step-1 callouts must be specific to the competitor — not the same boilerplate about IA patterns and social proof on all six sections. If you can't find something distinctive, say so.

4. **Asserting unverifiable claims.** Adoption numbers, funding rounds, and team sizes are frequently out of date or wrong. Cite the source URL and the date of review; flag anything you can't verify rather than guessing.

5. **Treating the six differentiator axes as optional.** Only the three priority ones (batteries included, security, stability) get extra weight in the insight section, but admin UIs, accessibility, and community/ecosystem all get assessed in full. Don't skip them because the competitor is quiet on them — "not addressed" is itself an insight for Django's positioning.

6. **Forgetting the AI section.** "What they say about AI" is its own section and high-signal in 2026. Rate it explicitly: leading / cautious / silent, plus the specific claims.

7. **Hard-wrapping the analysis output.** Follow the style guide — let prettier handle wrapping. Run `just format` before committing.

8. **Publishing without the draft callout.** Every produced analysis is a draft until the Marketing WG reviews it. Top-of-page blockquote per the style guide, every time.

## Verification checklist

- [ ] Source map saved at `competitors-analysis/<competitor-slug>/source-map.md`
- [ ] All six source-map sections filled, each with a specific "Why it matters for Django" callout
- [ ] Every source has a URL and a date of last review (July 2026 baseline)
- [ ] Analysis saved at `competitors-analysis/<competitor-slug>/analysis.md`
- [ ] Every section of `template-competitor-analysis.md` is filled, including AI and all six differentiator axes
- [ ] Every claim cites an inline source URL; unverified claims are flagged
- [ ] "Key insight for Django positioning" surfaces the three priority differentiators (batteries included, security, stability)
- [ ] Draft-status blockquote at the top of the analysis page
- [ ] File passes `just format` (prettier on Markdown)
- [ ] Date reviewed and reviewer name filled in the template footer
- [ ] If introducing a new competitor, the shortlist in `index.md` is updated with the relevance note
