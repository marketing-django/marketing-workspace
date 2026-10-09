# Recommended skills

The 18 skills we recommend for product strategy work, grouped by the step of the [strategy draft](../marketing-strategy/draft/README.md) they support, followed by shorter lists for the Foundation and community pillars. For the scores behind the choices, see [repository reviews](repository-reviews.md).

> ⚠️ This page is a **draft**. Recommendations come from reading the skills, not from running them. Treat each one as "worth a trial", not "proven".

## How we chose

A skill made the shortlist when it:

- Covers a format our draft or [research notes](../marketing-strategy/research/formats.md) already call for.
- Matches our [quality guidelines](../contributing/quality-assurance.md): starts from evidence, forces choices, and marks what is unsourced.
- Works without paid tools, sales data, or customer interviews we can't run.
- Can be read and adapted by a contributor without a developer background.

Where two skills cover the same format, we picked the one with stricter evidence rules, then the more permissive license.

## Adaptations every skill needs

All of these skills assume a company selling a product. Before using any of them for Django, give the agent this translation, ideally once in a shared context document:

| The skill says      | For Django, read                                                              |
| :------------------ | :---------------------------------------------------------------------------- |
| Customer, buyer     | Developer or organization adopting Django                                     |
| Purchase, deal, win | Choosing Django for a project                                                 |
| Pricing, revenue    | Not applicable for the framework; sponsorship and donations for the DSF       |
| Sales team, reps    | Community advocates, speakers, authors of tutorials                           |
| Churn               | Teams migrating away, or developers who try Django and don't continue         |
| Company, team       | The Django project, the DSF, and volunteer working groups                     |
| Customer interviews | Public evidence: surveys, the Django Forum, conference talks, community posts |

## Shared context

Do this first. Most other skills look for a context file and ask fewer questions when they find one.

- **[`product-marketing`](https://github.com/coreyhaines31/marketingskills/tree/main/skills/product-marketing)** (`coreyhaines31/marketingskills`, MIT) – builds a single context document covering audience, JTBD, competitive landscape, differentiation, the four forces of switching, verbatim audience language, and proof points, with a changelog. It can draft a first version from files in a repository, which suits this workspace. Skip the pricing and sales objection sections.
- **[`developer-audience-context`](https://github.com/jonathimer/devmarketing-skills/tree/main/skills/developer-audience-context)** (`jonathimer/devmarketing-skills`, MIT) – the same idea with developer-specific fields: role, seniority, stack, where developers spend time, and "build it yourself" as an alternative. Use it as a source of sections to merge into the document above rather than keeping two files.

## Audiences and jobs to be done

- **[`developer-segmentation`](https://github.com/samber/developer-relations-skills/tree/main/skills/developer-segmentation)** (`samber/developer-relations-skills`, MIT) – turns "developers" into three to five named, sized, and ranked segments, plus one segment we explicitly decide not to serve. That last part answers our guideline that a strategy should say what we won't do.
- **[`foundation-persona`](https://github.com/product-on-purpose/pm-skills/tree/main/skills/foundation-persona)** (`product-on-purpose/pm-skills`, Apache 2.0) – produces personas with explicit assumptions and confidence levels. Has a marketing mode. Use after segmentation, one persona per priority segment.
- **[`customer-research`](https://github.com/coreyhaines31/marketingskills/tree/main/skills/customer-research)** (`coreyhaines31/marketingskills`, MIT) – its "digital watering hole" mode mines public forums, Reddit, and Hacker News for what people say unprompted, with confidence labels and warnings about sample bias. This is the realistic way for us to gather evidence for JTBD without an interview program.
- **[`define-jtbd-canvas`](https://github.com/product-on-purpose/pm-skills/tree/main/skills/define-jtbd-canvas)** (`product-on-purpose/pm-skills`, Apache 2.0) – a canvas per job: who, in what circumstance, the job statement, functional, emotional, and social jobs, competing solutions, and hiring criteria. Short, with a template and a worked example. It expects insights to trace to research, so run `customer-research` first.

## Competitors analysis

Our own [competitors analysis skill](../marketing-strategy/competitors-analysis/README.md) stays the primary tool. These two add what it doesn't cover.

- **[`devrel-competitor-analysis`](https://github.com/samber/developer-relations-skills/tree/main/skills/devrel-competitor-analysis)** (`samber/developer-relations-skills`, MIT) – benchmarks docs and quickstart quality, repository health, community responsiveness, content cadence, and event presence from public signals, and returns a "close, ignore, or counter" verdict per gap. Useful for the "is onboarding easier elsewhere?" question in our research notes.
- **[`positioning-map`](https://github.com/pmalliance/product-marketing-skills/tree/main/pmm-signal-pack/skills/positioning-map)** (`pmalliance/product-marketing-skills`, MIT) – reads every competitor's public messaging side by side and reports which claims are crowded and which credible angles nobody is making. Our skill works one competitor at a time; this is the cross-competitor comparison view, and it can be fed the analyses we already have for FastAPI, Next.js, and Ruby on Rails.

## SWOT

- **[`swot-analysis`](https://github.com/deanpeters/Product-Manager-Skills/tree/main/skills/swot-analysis)** (`deanpeters/Product-Manager-Skills`, CC BY-NC-SA 4.0) – every entry needs a source and a Fact / Inference label, each quadrant is capped at five ranked entries, and the output ends with strength–opportunity and weakness–threat "crossings". It also catches the most common SWOT mistake: listing something we would have to do as an "opportunity". It works on a competitor as well as on ourselves.

> The license allows us to use this skill but not to copy or adapt it into this MIT-licensed workspace. If that is a problem, the SWOT step inside [`competitive-intelligence`](https://github.com/realjaymes/marketingagentskills/tree/main/skills/competitive-intelligence) (`realjaymes/marketingagentskills`, MIT) is the best permissive fallback: shorter, but it also requires every SWOT line to lead to a concrete use.

## Positioning and messaging

- **[`obviously-awesome`](https://github.com/wondelai/skills/tree/main/obviously-awesome)** (`wondelai/skills`, MIT) – April Dunford's method, which our research notes already favor: competitive alternatives, unique attributes, value, best-fit audience, market category. Includes a ten-row positioning canvas and a team exercise that would suit a working group session. Ignore its 0–10 scoring.
- **[`positioning-messaging-framework`](https://github.com/adam-lagerhausen/b2b-marketing-skills/tree/main/skills/positioning-messaging-framework)** (`adam-lagerhausen/b2b-marketing-skills`, MIT) – takes positioning through to exactly three messaging pillars, each with a reason to believe, then pressure-tests the result. The "logo-swap test" (would this still read as true with FastAPI's name on it?) is the single most useful check we found. Use it after `obviously-awesome`, to turn the canvas into messaging.
- **[`nonprofit-brand-messaging`](https://github.com/sector-skills/nonprofit-skills/tree/main/nonprofit-skills-library/skills/communications-marketing/nonprofit-brand-messaging)** (`sector-skills/nonprofit-skills`, MIT) – a "messaging house" with mission and vision at the base, a positioning statement, and pillars that each need a proof point. Use it for the DSF's own messaging, where product positioning methods fit poorly.

## Current state audit

- **[`message-consistency-check`](https://github.com/pmalliance/product-marketing-skills/tree/main/pmm-signal-pack/skills/message-consistency-check)** (`pmalliance/product-marketing-skills`, MIT) – reads all public surfaces together and reports where the category, lead value, audience, and proof differ between them. Point it at djangoproject.com, the docs landing pages, the repository README, and social profiles for the channel inventory in the draft.
- **[`claim-check`](https://github.com/pmalliance/product-marketing-skills/tree/main/pmm-signal-pack/skills/claim-check)** (`pmalliance/product-marketing-skills`, MIT) – extracts every claim we make and marks it supported, thin, or unsupported against evidence. A direct way to apply "starts with evidence, not opinion" to our existing copy and to new messaging before it ships.

## Vision statement

- **[`product-vision`](https://github.com/phuryn/pm-skills/tree/main/pm-product-strategy/skills/product-vision)** (`phuryn/pm-skills`, MIT) – drafts three to five vision options and picks one, checking each is inspiring, achievable, and emotional. It is 52 lines and has no evidence rules, so treat its output as raw material for a discussion. This is the weakest slot on the shortlist: no repository had a strong vision skill, and a short Django-specific one would be easy to write.

## Goals and measurement

- **[`foundation-okr-writer`](https://github.com/product-on-purpose/pm-skills/tree/main/skills/foundation-okr-writer)** (`product-on-purpose/pm-skills`, Apache 2.0) – drafts or audits OKRs, moves activities out of key results ("if it can go in your backlog, it is not an outcome"), and refuses to invent baselines or targets. Its audit mode can be run on the draft OKRs in our research notes as they stand.

## Review

Run these on drafts before asking people for their time.

- **[`good-strategy-bad-strategy`](https://github.com/wondelai/skills/tree/main/good-strategy-bad-strategy)** (`wondelai/skills`, MIT) – checks a strategy for a diagnosis, a guiding policy that rules things out, and coordinated actions, and flags goals presented as strategy. Close to our own guidelines on taking a stance.
- **[`ai-pmm-reviewer`](https://github.com/adam-lagerhausen/b2b-marketing-skills/tree/main/skills/ai-pmm-reviewer)** (`adam-lagerhausen/b2b-marketing-skills`, MIT) – reviews a draft for whether the problem is positioning, messaging, evidence, or wording, and lists generic AI phrasing to remove. Worth running on anything an agent helped write.

## Beyond product strategy

Not part of the shortlist, but the best we found for the other pillars. All MIT licensed.

### Foundation and fundraising

- [`oss-sponsors-fundraising`](https://github.com/samber/developer-relations-skills/tree/main/skills/oss-sponsors-fundraising) (`samber/developer-relations-skills`) – sponsorship tiers for individuals and companies, with sourced figures and a check on how much sponsor-facing work we can sustain.
- [`nonprofit-corporate-sponsorships`](https://github.com/sector-skills/nonprofit-skills/tree/main/nonprofit-skills-library/skills/fundraising-development/nonprofit-corporate-sponsorships), [`nonprofit-donor-pipeline`](https://github.com/sector-skills/nonprofit-skills/tree/main/nonprofit-skills-library/skills/fundraising-development/nonprofit-donor-pipeline), and [`nonprofit-program-design`](https://github.com/sector-skills/nonprofit-skills/tree/main/nonprofit-skills-library/skills/programs-impact/nonprofit-program-design) (`sector-skills/nonprofit-skills`) – sponsor tiers, donor stages (the closest thing to a donor pyramid), and theory of change.
- [`stakeholder-map`](https://github.com/phuryn/pm-skills/tree/main/pm-execution/skills/stakeholder-map) (`phuryn/pm-skills`) – a power / interest grid with a communication plan, matching the Mendelow's matrix format in our research notes.

### Community and outreach

- [`developer-journey-map`](https://github.com/samber/developer-relations-skills/tree/main/skills/developer-journey-map) and [`oss-contributor-onboarding`](https://github.com/samber/developer-relations-skills/tree/main/skills/oss-contributor-onboarding) (`samber/developer-relations-skills`) – the contributor journey map our research notes call for, from discovery through contribution to advocacy.
- [`developer-champions`](https://github.com/samber/developer-relations-skills/tree/main/skills/developer-champions) (`samber/developer-relations-skills`) – an unpaid ambassador program, relevant to "turn existing Django developers into active advocates".
- [`open-source-marketing`](https://github.com/jonathimer/devmarketing-skills/tree/main/skills/open-source-marketing) and [`developer-advocacy`](https://github.com/jonathimer/devmarketing-skills/tree/main/skills/developer-advocacy) (`jonathimer/devmarketing-skills`) – general guides to promoting an open source project and to talks, podcasts, and calls for proposals.

### Volunteer operations

No repository has a skill for running marketing with volunteers. Three ideas are worth borrowing instead:

- Asking for an effort ceiling up front and cutting scope to fit, as `samber/developer-relations-skills` does.
- Declaring a supervision level per skill (unsupervised, review, expert required), as `sector-skills/nonprofit-skills` does.
- Built-in human review gates, which our own competitors analysis skill already has.
