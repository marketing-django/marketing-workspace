# Repository reviews

One review per skills repository: what it contains, how it scores against our four criteria, and how well it is built. Read the [marketing skills summary](README.md) first for the scores side by side.

The first five repositories are the ones we set out to review. The eight after that turned up while searching for skills that cover our gaps (SWOT, vision, OKRs, non-profit, open source community) and are reviewed in less depth.

> ⚠️ This page is a **draft**. Scores are one reviewer's judgment from reading the repositories on 2026-10-09, not the result of running the skills. See [how to read the scores](#how-to-read-the-scores).

## How to read the scores

Each repository gets a score out of 10 on four criteria, built from the sub-criteria below. The overall score weights product marketing at 40% and the other three at 20% each, because product marketing is our current focus.

| Criterion                  | Sub-criteria                                                                                                                                                                                                                                             |
| :------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Product marketing          | Coverage of the formats in our [strategy draft](../marketing-strategy/draft/README.md) (competitors analysis, JTBD, SWOT, positioning, messaging, personas, vision, OKRs). Fit for a free, open source developer framework. Evidence and sourcing rules. |
| Non-profit marketing       | Fundraising, donor, or sponsor content. Mission-led framing. How much of the commercial material transfers to the DSF.                                                                                                                                   |
| Community marketing        | Open source and developer community content. Advocacy, events, and contributor programs. Channels a diffuse community uses.                                                                                                                              |
| Volunteer-driven marketing | Works without paid tools or budgets. Light enough for part-time contributors. Built-in review steps. Stays maintained and easy to install.                                                                                                               |

A separate **build quality** rating covers what makes a skill dependable regardless of topic: usefulness to agents, evals, portability across agents, and licensing. It is not part of the overall score.

Scores of 1–3 mean "little or nothing relevant", 4–6 "useful with adaptation", 7–8 "strong fit", 9–10 "could be adopted as is". Almost every repository is written for commercial software companies, which is why scores above 8 are rare.

## Original five repositories

### coreyhaines31/marketingskills

[coreyhaines31/marketingskills](https://github.com/coreyhaines31/marketingskills) – 50 skills covering most of commercial software marketing, by Corey Haines and 45 other contributors. By far the most used and most actively maintained repository in this review.

| Product | Non-profit | Community | Volunteer-driven | Overall | Build quality |
| :------ | :--------- | :-------- | :--------------- | :------ | :------------ |
| 7       | 3          | 6         | 5                | **5.6** | 9             |

- **Product marketing (7).** `product-marketing` builds a shared context document (audience, JTBD, competitive landscape, differentiation, switching forces, customer language) that every other skill reads first – the same pattern we would want for Django. `customer-research` and `competitor-profiling` have explicit evidence rules: confidence labels, "not observed is not absent", never state a competitor's motive. No SWOT or vision skill, and positioning is a section of the context document rather than a method. Examples and defaults assume a paid SaaS product with a sales funnel.
- **Non-profit (3).** Nothing written for fundraising or donors. `emails`, `co-marketing`, and `public-relations` transfer with adaptation. `marketing-plan` is organized around the AARRR revenue funnel and funding rounds, which doesn't map to the DSF.
- **Community (6).** `community-marketing`, `events`, `social`, `content-strategy`, and `referrals` (ambassador programs) are all relevant, but they treat community as a growth channel for a company rather than the thing itself.
- **Volunteer-driven (5).** Easy to install and kept current (last commit 2026-10-08). Several research skills prefer paid services (Firecrawl, DataForSEO), though they document a free fallback. Many skills assume budgets and tooling we don't have.
- **Build quality (9).** Follows the open [Agent Skills specification](https://agentskills.io/specification.md) and installs to the cross-agent `.agents/skills/` folder, with plugin manifests for Claude Code and Codex. Every skill ships an `evals/evals.json` file – 413 test prompts with 2,488 assertions in total. These are test definitions: we found no committed results and no CI job that runs them. CI does validate skill format, versioning, and the bundled command-line tools. Skills warn agents to treat fetched web pages as untrusted input. MIT license.

Worth knowing: the repository is funded by "verified partners" whose tools are listed alongside neutral options. The maintainers state that partners don't influence what the skills recommend.

### adam-lagerhausen/b2b-marketing-skills

[adam-lagerhausen/b2b-marketing-skills](https://github.com/adam-lagerhausen/b2b-marketing-skills) – nine product marketing skills by a single practitioner, written as methods with quality bars rather than as templates.

| Product | Non-profit | Community | Volunteer-driven | Overall | Build quality |
| :------ | :--------- | :-------- | :--------------- | :------ | :------------ |
| 7       | 2          | 2         | 6                | **4.8** | 6             |

- **Product marketing (7).** The best-written positioning and research skills we reviewed. `positioning-messaging-framework` forces segment choices, names the real alternative (often the status quo), limits output to three messaging pillars, and ends with pressure tests such as the "logo-swap test". `voice-of-customer-synthesis` separates what people said from what we infer, and writes JTBD statements with functional, emotional, and social jobs. `ai-pmm-reviewer` reviews drafts for generic AI language. Everything is framed around B2B sales: buyers, deals, sales decks.
- **Non-profit (2), community (2).** No relevant content. `customer-story-engine` could be adapted for sponsor or user stories.
- **Volunteer-driven (6).** No tools, no paid services, plain Markdown. A small set that one person can learn in an afternoon. `b2b-pmm-orchestrator` routes a vague request to "the smallest useful artifact", which suits part-time contributors.
- **Build quality (6).** No evals, but every skill has a worked example and there is a full nine-step case study. Skills use only `name` and `description` front matter, so they work in any agent. A Claude Code plugin manifest is included. Young and low-traffic: 14 commits, one author, last commit 2026-06-20. MIT license.

### jonathimer/devmarketing-skills

[jonathimer/devmarketing-skills](https://github.com/jonathimer/devmarketing-skills) – 34 skills for marketing to developers, modeled on `coreyhaines31/marketingskills`. The only repository in the original five that addresses our audience and open source directly.

| Product | Non-profit | Community | Volunteer-driven | Overall | Build quality |
| :------ | :--------- | :-------- | :--------------- | :------ | :------------ |
| 5       | 2          | 8         | 5                | **5.0** | 5             |

- **Product marketing (5).** `developer-audience-context` is a developer-specific version of the shared context document: role, seniority, stack, where developers spend time, verbatim language, current alternatives including "build it yourself". `competitor-tracking` and `alternatives-pages` are relevant. No positioning, messaging, JTBD, or SWOT method. A third of the skills cover things we don't have: pricing, signup flows, free tiers, SDK design.
- **Non-profit (2).** A few mentions of GitHub Sponsors, nothing on fundraising.
- **Community (8).** The strongest set for our community pillar: `open-source-marketing`, `community-building`, `developer-advocacy` (conference talks, calls for proposals), `power-user-cultivation` (champion programs and contributor experience), plus channel skills for Hacker News, Reddit, and newsletters. The tone – "developers have a finely-tuned BS detector" – matches how we need to write.
- **Volunteer-driven (5).** No tool dependencies. Skills are long reference guides (300–600 lines) full of generic templates, which costs context and reviewer time. Not maintained: a single commit on 2026-03-03.
- **Build quality (5).** No evals, no examples beyond one reference file, no versioning history. Follows the Agent Skills specification and is portable. MIT license.

### realjaymes/marketingagentskills

[realjaymes/marketingagentskills](https://github.com/realjaymes/marketingagentskills) – 32 skills converted from one consultant's template library, mixing product marketing with automation and video tooling.

| Product | Non-profit | Community | Volunteer-driven | Overall | Build quality |
| :------ | :--------- | :-------- | :--------------- | :------ | :------------ |
| 6       | 2          | 2         | 5                | **4.2** | 5             |

- **Product marketing (6).** Broad coverage of our formats: `product-positioning`, `product-messaging`, `icp-persona`, `customer-segments`, `product-marketing-metrics`, and `competitive-intelligence` – the only skill in the original five with an explicit SWOT step. Quality is uneven. `competitive-intelligence` and `product-marketing-metrics` are careful (sources, confidence ratings, `[proof needed]` placeholders). `product-positioning` and `product-messaging` are fill-in templates that require "at least 7 bullet points" per section and 20+ tagline options, which produces volume rather than choices.
- **Non-profit (2), community (2).** No relevant content.
- **Volunteer-driven (5).** No paid tools needed for the strategy skills. Actively maintained by one person (last commit 2026-10-07). About a third of the repository is unrelated to our work (n8n, Clay, Remotion, ad creative).
- **Build quality (5).** Evals for 2 of 32 skills, one of which is a fork of a `coreyhaines31/marketingskills` skill. Worked examples for the newer skills, marked as illustrative. Written for Claude first – installation is documented for Claude apps and some skills use Claude Code-only front matter (`argument-hint`) – but the content is plain Markdown. MIT license.

### pmalliance/product-marketing-skills

[pmalliance/product-marketing-skills](https://github.com/pmalliance/product-marketing-skills) – twelve product marketing skills in two sets: six "core" skills, and a six-skill "signal pack" for reading large bodies of evidence.

| Product | Non-profit | Community | Volunteer-driven | Overall | Build quality |
| :------ | :--------- | :-------- | :--------------- | :------ | :------------ |
| 7       | 2          | 1         | 4                | **4.2** | 5             |

- **Product marketing (7).** `messaging-positioning` is the only skill in the original five built explicitly on April Dunford's _Obviously Awesome_ method, which our [research on formats](../marketing-strategy/research/formats.md) already favors. `customer-research` covers personas, JTBD, and voice of customer in one long skill. Three signal pack skills fit work we need to do on public material: `positioning-map` (lay every competitor's positioning side by side, find crowded and unclaimed ground), `claim-check` (does evidence support each claim we make), and `message-consistency-check` (does djangoproject.com say the same thing everywhere). The other three need sales call transcripts we don't have.
- **Non-profit (2), community (1).** No relevant content.
- **Volunteer-driven (4).** The six core skills ship only as zipped `.skill` packages, so they can't be read or reviewed on GitHub, and changes don't show up in diffs. Instructions assume the Claude apps.
- **Build quality (5).** No evals or examples. The signal pack is explicit about its evidence standard ("a claim is only marked supported when a specific piece of proof is cited") and gives a fallback for smaller models. Claude-specific in packaging and wording, portable in content. Four commits, last on 2026-07-10. MIT license, but the two license files name different copyright holders (Maja Voje / GTM Strategist at the root, Product Marketing Alliance for the signal pack) – worth confirming before we redistribute anything.

## Additional repositories

Found through GitHub search, skill directories, and "awesome" lists. For these we read the skills relevant to our work in full or in part, and relied on descriptions and headings for the rest.

### samber/developer-relations-skills

[samber/developer-relations-skills](https://github.com/samber/developer-relations-skills) – 56 developer relations skills by one author, including a set written from the open source maintainer's side. The best overall fit for Django of everything we reviewed, and almost unknown (2 stars).

| Product | Non-profit | Community | Volunteer-driven | Overall | Build quality |
| :------ | :--------- | :-------- | :--------------- | :------ | :------------ |
| 6       | 6          | 9         | 6                | **6.6** | 8             |

- **Product marketing (6).** `devrel-competitor-analysis` benchmarks competitors on exactly the surfaces our [competitors analysis](../marketing-strategy/competitors-analysis/README.md) cares about – docs, repository health, community, content cadence, events – using public evidence only. `developer-segmentation` produces sized, ranked segments and a written "anti-segment". `developer-journey-map` runs from discovery to contribution and advocacy. No positioning, messaging, or SWOT skill.
- **Non-profit (6).** `oss-sponsors-fundraising` designs sponsorship tiers for individuals and companies with sourced figures, and asks how much sponsor-facing work the maintainers can absorb "in a bad month". `oss-governance` covers foundations and fiscal hosts. Nothing on individual donors or grants beyond a "grant lane".
- **Community (9).** `oss-contributor-onboarding`, `developer-champions` (unpaid ambassador programs), `developer-meetup-program`, `developer-community-health`, `oss-launch`, and `oss-distribution-strategy`.
- **Volunteer-driven (6).** Skills ask for an effort ceiling and deadline up front and cut scope to match. No paid tools. Skills are long (200–375 lines) and cross-reference each other, so the author recommends installing the whole set. Written mostly for companies with a developer relations team.
- **Build quality (8).** Every skill has an `evals/evals.json` file, and the repository includes a runner to execute them – though no results are committed and nothing runs in CI. Skills separate sourced figures from their own defaults and say which is which. Installs in Claude Code, Codex, Cursor, and Gemini. One contributor, last commit 2026-09-28. MIT license.

### deanpeters/Product-Manager-Skills

[deanpeters/Product-Manager-Skills](https://github.com/deanpeters/Product-Manager-Skills) – 77 product management skills, with the most rigorous research and strategy methods we found. The license is the catch.

| Product | Non-profit | Community | Volunteer-driven | Overall | Build quality |
| :------ | :--------- | :-------- | :--------------- | :------ | :------------ |
| 8       | 3          | 2         | 4                | **5.0** | 7             |

- **Product marketing (8).** `swot-analysis` is the best SWOT skill we reviewed: every entry needs a source and a Fact / Inference label, quadrants are capped at five ranked entries, and it ends with strength–opportunity and weakness–threat "crossings" so the SWOT leads somewhere. Also `jobs-to-be-done`, `positioning-workshop` (Geoffrey Moore format), a chain of competitive research skills, and three stakeholder mapping skills. No vision or OKR skill.
- **Non-profit (3), community (2).** Stakeholder mapping transfers to the Foundation pillar. Nothing else.
- **Volunteer-driven (4).** Licensed [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/): non-commercial use only, and adaptations must carry the same license. Using the skills as they are is fine for us. Anything we copy or adapt keeps that license, so it can't be folded into this workspace's MIT-licensed content. Skills depend on shared "protocol" skills, so they work best installed as a set.
- **Build quality (7).** No evals, but scripts validate metadata and trigger phrases. Deliberately portable: avoids Claude-only syntax and documents Codex and ChatGPT installs. Six contributors, last commit 2026-09-01.

### wondelai/skills

[wondelai/skills](https://github.com/wondelai/skills) – 65 skills, each distilling one business or design book into a method with reference files.

| Product | Non-profit | Community | Volunteer-driven | Overall | Build quality |
| :------ | :--------- | :-------- | :--------------- | :------ | :------------ |
| 7       | 2          | 3         | 6                | **5.0** | 6             |

- **Product marketing (7).** `obviously-awesome` is the most complete implementation of April Dunford's positioning method we found: the five steps, a ten-row positioning canvas, and eight reference files including a team exercise and interview script. `jobs-to-be-done`, `good-strategy-bad-strategy` (diagnosis, guiding policy, coherent actions – a useful check on a strategy draft), and `storybrand-messaging` are also relevant. Each skill scores the work out of 10, which is a gimmick we would ignore.
- **Non-profit (2), community (3).** `contagious` (word of mouth) and `drive-motivation` are loosely relevant.
- **Volunteer-driven (6).** Each skill is self-contained. No tools needed. Two thirds of the repository is unrelated (software design, UX).
- **Build quality (6).** No evals. Good use of reference files loaded only when needed. Portable, with install instructions for several agents. The repository holds every skill twice (once under `plugins/`). MIT license; the methods come from commercially published books, credited in each skill.

### product-on-purpose/pm-skills

[product-on-purpose/pm-skills](https://github.com/product-on-purpose/pm-skills) – 68 product management skills with the most serious testing of any repository here.

| Product | Non-profit | Community | Volunteer-driven | Overall | Build quality |
| :------ | :--------- | :-------- | :--------------- | :------ | :------------ |
| 6       | 3          | 1         | 5                | **4.2** | 9             |

- **Product marketing (6).** `foundation-okr-writer` is the strongest OKR skill we reviewed: it separates outcomes from work, refuses to invent baselines or targets, and audits existing OKRs. `define-jtbd-canvas` and `foundation-persona` both insist on tracing back to research and label assumptions. `discover-competitive-analysis` is generic. No positioning, messaging, or SWOT skill; most of the repository is about software delivery.
- **Non-profit (3), community (1).** `discover-stakeholder-summary` transfers.
- **Volunteer-driven (5).** Individual skills are clean and come with a template and a completed example. The surrounding machinery (hooks, subagents, workflow commands, a project memory file) is more than we need.
- **Build quality (9).** 53 of 68 skills have trigger tests, 12 have output-quality scenarios, and CI workflows exist to run both (advisory, and gated on cost). Each skill says when not to use it and which skill to use instead. Claude and Codex plugins, plus generic installs. Six contributors. Apache 2.0 license.

### phuryn/pm-skills

[phuryn/pm-skills](https://github.com/phuryn/pm-skills) – 69 short product management skills by Paweł Huryn. Very popular, and the widest coverage of our formats, but shallow.

| Product | Non-profit | Community | Volunteer-driven | Overall | Build quality |
| :------ | :--------- | :-------- | :--------------- | :------ | :------------ |
| 6       | 3          | 2         | 5                | **4.4** | 5             |

- **Product marketing (6).** Has a skill for nearly every format in our draft: `swot-analysis`, `product-vision`, `brainstorm-okrs`, `user-personas`, `value-proposition`, `competitor-analysis`, `positioning-ideas`, `stakeholder-map`. Most are 50–150 line prompt templates ("you are a veteran product leader…") with a checklist of things to consider and no evidence rules. `product-vision` is the only vision skill in the whole review, and it is 52 lines.
- **Non-profit (3), community (2).** `stakeholder-map` (power / interest grid) matches the Mendelow's matrix format in our research notes.
- **Volunteer-driven (5).** Short and easy to understand. Each skill links to the author's paid newsletter for further reading.
- **Build quality (5).** No skill evals; CI checks manifests and counts only. Claude-first: skills use `$ARGUMENTS` and slash commands, with a Codex plugin added. Three contributors, last commit 2026-09-14. MIT license.

### sector-skills/nonprofit-skills

[sector-skills/nonprofit-skills](https://github.com/sector-skills/nonprofit-skills) – 102 skills for non-profit operations. The only repository we found that addresses the Foundation pillar directly.

| Product | Non-profit | Community | Volunteer-driven | Overall | Build quality |
| :------ | :--------- | :-------- | :--------------- | :------ | :------------ |
| 2       | 8          | 4         | 6                | **4.4** | 5             |

- **Product marketing (2).** Only `nonprofit-brand-messaging` – but it is a good fit for the DSF side: a "messaging house" with mission and vision at the foundation, a positioning statement, three or four pillars each needing a proof point, and a voice guide.
- **Non-profit (8).** `nonprofit-donor-pipeline`, `nonprofit-donor-retention`, `nonprofit-corporate-sponsorships`, `nonprofit-annual-report`, `nonprofit-donation-page-copy`, `nonprofit-grant-writing`, and `nonprofit-program-design` (theory of change, which our research notes list for the Foundation pillar). Written for US charities, so tax and compliance details need checking against the DSF's situation.
- **Community (4).** `nonprofit-volunteer-management` (thin), `nonprofit-coalition-building`, `nonprofit-storytelling`.
- **Volunteer-driven (6).** Every skill declares a supervision level – unsupervised, review, or expert required – with a one-line reason. That is a useful idea for any skill volunteers run.
- **Build quality (5).** No evals. New and unproven: 2 stars, 18 commits, 8 of them authored by an AI agent. Plain Markdown in the same format as `coreyhaines31/marketingskills`. MIT license.

### anthropics/knowledge-work-plugins

[anthropics/knowledge-work-plugins](https://github.com/anthropics/knowledge-work-plugins) – Anthropic's plugins for office work in Claude, 252 skills across marketing, product management, sales, and more.

| Product | Non-profit | Community | Volunteer-driven | Overall | Build quality |
| :------ | :--------- | :-------- | :--------------- | :------ | :------------ |
| 5       | 3          | 2         | 5                | **4.0** | 6             |

- **Product marketing (5).** Two `competitive-brief` skills (marketing and product management), `campaign-plan`, `brand-review`, and `synthesize-research`. Competent and generic. No SWOT, vision, OKR, or positioning method.
- **Non-profit (3).** `grant-rfp-writer` covers grant discovery and drafting.
- **Community (2), volunteer-driven (5).** Nothing specific. Skills expect connectors to workplace tools.
- **Build quality (6).** No evals. The most Claude-specific repository here: plugins, slash commands, and connector placeholders. Well maintained (32 contributors, last commit 2026-10-07). Apache 2.0 license, with some partner plugins under MIT.

### wdavidturner/product-skills

[wdavidturner/product-skills](https://github.com/wdavidturner/product-skills) – 20 short product strategy skills derived from podcast interviews.

| Product | Non-profit | Community | Volunteer-driven | Overall | Build quality |
| :------ | :--------- | :-------- | :--------------- | :------ | :------------ |
| 6       | 1          | 1         | 4                | **3.6** | 6             |

- **Product marketing (6).** `positioning-canvas` (April Dunford, with "common mistake" patterns), `jobs-to-be-done`, `okrs`, and `strategic-narrative`. Each is under 110 lines plus pattern files. A lighter alternative to the `wondelai/skills` versions.
- **Volunteer-driven (4).** Not maintained since 2026-01-18.
- **Build quality (6).** The only repository with committed eval results: three prompts per skill, scored for Claude and Codex. MIT license, but the repository also bundles 297 podcast transcripts whose redistribution rights are unclear.

## Considered and not reviewed

Looked at by name and description only. None changed the shortlist.

| Repository                                                                                                      | Why not                                                                                          |
| :-------------------------------------------------------------------------------------------------------------- | :----------------------------------------------------------------------------------------------- |
| [alirezarezvani/claude-skills](https://github.com/alirezarezvani/claude-skills)                                 | Very large collection; marketing skills appear derived from `coreyhaines31/marketingskills`.     |
| [RefoundAI/lenny-skills](https://github.com/RefoundAI/lenny-skills)                                             | Podcast-derived, overlaps `wdavidturner/product-skills`. Best next candidate if we want more.    |
| [aaron-he-zhu/aaron-marketing-skills](https://github.com/aaron-he-zhu/aaron-marketing-skills)                   | Mostly ads, email, and SEO operations. A "narrative" set on messaging may be worth a later look. |
| [kostja94/marketing-skills](https://github.com/kostja94/marketing-skills)                                       | SEO, page types, and channels – execution, not strategy.                                         |
| [OpenClaudia/openclaudia-skills](https://github.com/OpenClaudia/openclaudia-skills)                             | SEO, content, email, and ads execution.                                                          |
| [ericosiu/ai-marketing-skills](https://github.com/ericosiu/ai-marketing-skills)                                 | Growth and outbound sales automation.                                                            |
| [getagentseal/founder-playbook](https://github.com/getagentseal/founder-playbook)                               | Book distillations; overlaps `wondelai/skills`, which is broader.                                |
| [samber/dev-event-organizer-skills](https://github.com/samber/dev-event-organizer-skills)                       | Conferences and meetups. Relevant if DjangoCon marketing comes into scope.                       |
| [benjaminjackson/nonprofit-fundraising-skills](https://github.com/benjaminjackson/nonprofit-fundraising-skills) | Two skills only (donor stewardship, donor newsletter).                                           |
| [anthropics/skills](https://github.com/anthropics/skills)                                                       | General document and development skills; nothing on strategy.                                    |
