# Skill reviews

A skill-by-skill review of the skills most relevant to our work, grouped by repository. For the shortlist and how to use it, see [recommended skills](recommended-skills.md).

> ⚠️ This page is a **draft**. About 70 of the roughly 850 skills across the 13 repositories are covered here – the ones relevant to strategy, the Foundation, or community. The rest (ads, SEO, pricing, sales tooling, software delivery) were checked by name and description only.

## How to read the tables

- **Verdict** – _Recommended_ (on the shortlist), _Consider_ (useful, but something else is better or it needs heavy adaptation), _Borrow from_ (worth mining for ideas rather than using as is), or _Skip_.
- **Useful to agents** – whether the skill gives an agent something it wouldn't do unprompted: a method with steps, rules about evidence, a defined output, checks before finishing. _High_ means it does all of that. _Medium_ means a solid structure but few rules. _Low_ means a template or a list of things to consider.
- **Evals** – _Cases_ means test prompts with expected behavior are published. _Trigger_ means tests that the skill activates on the right requests. _Output_ means tests of output quality. _Results_ means scored results are published. _None_ means no tests.

Portability and licensing are the same for every skill in a repository, so they are stated once per repository.

## coreyhaines31/marketingskills

Portable: follows the [Agent Skills specification](https://agentskills.io/specification.md), with plugins for Claude Code and Codex. MIT license.

| Skill                  | Verdict     | Useful to agents | Evals | Notes                                                                                                         |
| :--------------------- | :---------- | :--------------- | :---- | :------------------------------------------------------------------------------------------------------------ |
| `product-marketing`    | Recommended | High             | Cases | Shared context document with JTBD, switching forces, and a changelog. Can draft itself from repository files. |
| `customer-research`    | Recommended | High             | Cases | Three modes; mining public communities fits us. Confidence labels and sample-bias warnings.                   |
| `competitor-profiling` | Borrow from | High             | Cases | Strong evidence rules ("not observed is not absent"). Prefers paid scraping and SEO services.                 |
| `competitors`          | Skip        | Medium           | Cases | Comparison pages for search traffic. Django doesn't publish "versus" pages.                                   |
| `marketing-plan`       | Skip        | High             | Cases | 13-section plan built on a revenue funnel and funding stages. Wrong shape for us.                             |
| `marketing-council`    | Consider    | Medium           | Cases | Simulated panel of well-known marketers who disagree. A cheap way to stress-test a draft, not a method.       |
| `site-architecture`    | Consider    | High             | Cases | Page hierarchy and navigation. Relevant to the website redesign rather than the strategy.                     |
| `content-strategy`     | Consider    | High             | Cases | Content pillars and prioritization. Relevant to the blog's editorial line.                                    |
| `copywriting`          | Consider    | High             | Cases | Page copy with a "no AI tells" section. For the redesign.                                                     |
| `community-marketing`  | Consider    | Medium           | Cases | Community as a growth channel for a company. Good principles, generic playbooks.                              |
| `events`               | Consider    | Medium           | Cases | Short. Measures events by sales pipeline.                                                                     |
| `launch`               | Consider    | High             | Cases | Could inform release announcements.                                                                           |
| `public-relations`     | Consider    | Medium           | Cases | Press and crisis communication.                                                                               |

The remaining 37 skills (ads, SEO, pricing, paywalls, cold email, and similar) don't apply to our work.

## adam-lagerhausen/b2b-marketing-skills

Portable: plain Markdown with only `name` and `description` front matter; a Claude Code plugin is included. MIT license.

| Skill                             | Verdict     | Useful to agents | Evals | Notes                                                                                                          |
| :-------------------------------- | :---------- | :--------------- | :---- | :------------------------------------------------------------------------------------------------------------- |
| `positioning-messaging-framework` | Recommended | High             | None  | Forces segment choices, exactly three pillars, eight pressure tests. Has a worked example.                     |
| `ai-pmm-reviewer`                 | Recommended | High             | None  | Separates positioning, messaging, evidence, and wording problems. Lists generic AI phrasing.                   |
| `voice-of-customer-synthesis`     | Consider    | High             | None  | Excellent method for turning raw notes into JTBD and exact language. Assumes sales calls; works on forum data. |
| `category-point-of-view`          | Consider    | High             | None  | A point of view on the market. Could shape "why Django now" in the 2026 framing.                               |
| `b2b-pmm-orchestrator`            | Borrow from | Medium           | None  | Routes requests to "the smallest useful artifact". A good pattern for a Django equivalent.                     |
| `customer-story-engine`           | Consider    | High             | None  | For case studies of organizations using Django.                                                                |
| `launch-tier-framework`           | Skip        | High             | None  | Launch sizing across sales and product teams.                                                                  |
| `sales-narrative-deck`            | Skip        | High             | None  | Sales decks.                                                                                                   |
| `demo-storyline`                  | Skip        | High             | None  | Sales demos.                                                                                                   |

## jonathimer/devmarketing-skills

Portable: follows the Agent Skills specification. MIT license. Not maintained since its single commit.

| Skill                        | Verdict     | Useful to agents | Evals | Notes                                                                                          |
| :--------------------------- | :---------- | :--------------- | :---- | :--------------------------------------------------------------------------------------------- |
| `developer-audience-context` | Recommended | Medium           | None  | Developer-specific context fields. Merge into the shared context document.                     |
| `open-source-marketing`      | Consider    | Low              | None  | Sensible principles, then mostly README and issue templates.                                   |
| `developer-advocacy`         | Consider    | Medium           | None  | Conference proposals, podcasts, a monthly report template.                                     |
| `power-user-cultivation`     | Consider    | Medium           | None  | Champion programs and contributor experience.                                                  |
| `community-building`         | Consider    | Medium           | None  | Chat and forum community strategy.                                                             |
| `competitor-tracking`        | Skip        | Low              | None  | A checklist of what to monitor. Our own skill is stricter.                                     |
| `developer-listening`        | Consider    | Low              | None  | Where to monitor developer conversations.                                                      |
| `docs-as-marketing`          | Consider    | Medium           | None  | Docs as an adoption channel. Relevant to marketing contributions to the docs.                  |
| `github-presence`            | Consider    | Low              | None  | README and repository discoverability.                                                         |
| `hacker-news-strategy`       | Consider    | Medium           | None  | Channel etiquette; also `reddit-engagement`, `developer-newsletter`, and `linkedin-technical`. |

The remaining skills (pricing, signup, free tiers, SDK design, ads) don't apply.

## realjaymes/marketingagentskills

Written for Claude first (some Claude Code-only front matter, Claude app install instructions); content is plain Markdown. MIT license.

| Skill                       | Verdict  | Useful to agents | Evals | Notes                                                                                               |
| :-------------------------- | :------- | :--------------- | :---- | :-------------------------------------------------------------------------------------------------- |
| `competitive-intelligence`  | Consider | High             | None  | Gather, SWOT, battlecard, validate. The permissive fallback for SWOT. Battlecards are sales-facing. |
| `product-marketing-metrics` | Consider | High             | None  | Metric tree with leading and lagging indicators. Six worked examples, all commercial.               |
| `icp-persona`               | Consider | Medium           | None  | Four persona templates. `foundation-persona` is stricter about evidence.                            |
| `product-positioning`       | Skip     | Low              | None  | Fill-in template demanding seven bullets per section. Produces volume, not choices.                 |
| `product-messaging`         | Skip     | Low              | None  | Generates 20 or more tagline options across seven formulas.                                         |
| `storytelling-framework`    | Consider | Medium           | None  | One story structure with several output modes.                                                      |
| `customer-segments`         | Skip     | Low              | None  | Template. `developer-segmentation` is far stronger.                                                 |
| `marketing-advantages`      | Skip     | Medium           | None  | Product-led growth and virality levers.                                                             |
| `press-release`             | Consider | Medium           | None  | Includes a newsworthiness check.                                                                    |

## pmalliance/product-marketing-skills

Claude-specific in packaging and wording; content is portable. MIT license, with two different copyright holders named.

| Skill                       | Verdict     | Useful to agents | Evals | Notes                                                                                                       |
| :-------------------------- | :---------- | :--------------- | :---- | :---------------------------------------------------------------------------------------------------------- |
| `positioning-map`           | Recommended | High             | None  | Cross-competitor view of crowded and unclaimed positioning. Every claim must cite a page.                   |
| `message-consistency-check` | Recommended | High             | None  | Compares our message across all public surfaces and ranks mismatches.                                       |
| `claim-check`               | Recommended | High             | None  | Each claim marked supported, thin, or unsupported. "Do not soften a verdict to be reassuring."              |
| `messaging-positioning`     | Consider    | Medium           | None  | April Dunford's method plus a message house. Solid, but ships as a zip file; `obviously-awesome` is deeper. |
| `customer-research`         | Consider    | Medium           | None  | 850 lines covering personas, JTBD, and interview guides. Zip file. Built around interviews.                 |
| `customer-language-bank`    | Consider    | High             | None  | Ranks the words an audience uses. Would work on forum and survey text.                                      |
| `competitive-intelligence`  | Skip        | Medium           | None  | Battlecards and comparison pages. Zip file.                                                                 |
| `win-loss-reasons`          | Skip        | High             | None  | Needs sales call transcripts. Same for `objection-library`.                                                 |

## samber/developer-relations-skills

Portable: plugins for Claude Code, Codex, Cursor, and Gemini. MIT license.

| Skill                        | Verdict     | Useful to agents | Evals | Notes                                                                                          |
| :--------------------------- | :---------- | :--------------- | :---- | :--------------------------------------------------------------------------------------------- |
| `devrel-competitor-analysis` | Recommended | High             | Cases | Public evidence only. Scope scales to the hours available.                                     |
| `developer-segmentation`     | Recommended | High             | Cases | Sized, ranked segments and a written anti-segment.                                             |
| `developer-journey-map`      | Consider    | High             | Cases | Discovery to advocacy, one "leak" to fix. For the community pillar.                            |
| `oss-sponsors-fundraising`   | Consider    | High             | Cases | Sponsor tiers with sourced figures. For the Foundation pillar.                                 |
| `oss-contributor-onboarding` | Consider    | High             | Cases | Path to a first merged contribution, with a rubric.                                            |
| `developer-champions`        | Consider    | High             | Cases | Unpaid ambassador program.                                                                     |
| `devrel-strategy`            | Consider    | High             | Cases | Program-level planning; also `devrel-metrics` and `devrel-content-calendar`. Not read in full. |
| `oss-governance`             | Skip        | High             | Cases | Django's governance is settled.                                                                |

## deanpeters/Product-Manager-Skills

Portable by design (Claude, Codex, and ChatGPT installs). CC BY-NC-SA 4.0: usable, but not to be copied or adapted into this workspace.

| Skill                           | Verdict     | Useful to agents | Evals | Notes                                                                               |
| :------------------------------ | :---------- | :--------------- | :---- | :---------------------------------------------------------------------------------- |
| `swot-analysis`                 | Recommended | High             | None  | Sourced, labeled, capped, and ends in crossings. The best SWOT skill reviewed.      |
| `jobs-to-be-done`               | Consider    | High             | None  | 390 lines with examples. `define-jtbd-canvas` is shorter and permissively licensed. |
| `positioning-workshop`          | Consider    | High             | None  | Facilitated five-question workshop ending in a Geoffrey Moore statement.            |
| `competitive-research-snapshot` | Consider    | High             | None  | Part of a cited research chain with `market-landscape-scan`. Not read in full.      |
| `stakeholder-mapping`           | Consider    | High             | None  | With `stakeholder-identification`. For the Foundation pillar. Not read in full.     |

## wondelai/skills

Portable: plain skill folders with installs for several agents. MIT license.

| Skill                        | Verdict     | Useful to agents | Evals | Notes                                                                                     |
| :--------------------------- | :---------- | :--------------- | :---- | :---------------------------------------------------------------------------------------- |
| `obviously-awesome`          | Recommended | High             | None  | April Dunford's five steps, a canvas, and eight reference files including a team session. |
| `good-strategy-bad-strategy` | Recommended | High             | None  | Diagnosis, guiding policy, coherent actions. Use as a review of the strategy draft.       |
| `jobs-to-be-done`            | Consider    | Medium           | None  | "Hiring" and switching framing. Not read in full.                                         |
| `storybrand-messaging`       | Consider    | Medium           | None  | Story-based messaging. Not read in full.                                                  |

## product-on-purpose/pm-skills

Claude and Codex plugins plus generic installs; some skills rely on Claude Code subagents. Apache 2.0 license.

| Skill                           | Verdict     | Useful to agents | Evals           | Notes                                                                      |
| :------------------------------ | :---------- | :--------------- | :-------------- | :------------------------------------------------------------------------- |
| `define-jtbd-canvas`            | Recommended | High             | Trigger         | Short, with a template, a worked example, and a "when not to use" section. |
| `foundation-persona`            | Recommended | High             | Trigger         | Marketing mode. Assumptions and confidence are explicit.                   |
| `foundation-okr-writer`         | Recommended | High             | Trigger, output | Five modes including audit. Refuses to invent baselines.                   |
| `measure-okr-grader`            | Consider    | High             | Trigger, output | Scores OKRs at the end of a cycle. Not read in full.                       |
| `discover-competitive-analysis` | Skip        | Medium           | Trigger, output | Generic. Our own skill is more specific.                                   |
| `discover-stakeholder-summary`  | Consider    | Medium           | Trigger         | Stakeholder needs and influence. Not read in full.                         |

## phuryn/pm-skills

Claude-first (`$ARGUMENTS`, slash commands), with a Codex plugin. MIT license.

| Skill               | Verdict     | Useful to agents | Evals | Notes                                                                         |
| :------------------ | :---------- | :--------------- | :---- | :---------------------------------------------------------------------------- |
| `product-vision`    | Recommended | Low              | None  | The only vision skill found. 52 lines; output is raw material for discussion. |
| `stakeholder-map`   | Consider    | Low              | None  | Power / interest grid. 51 lines.                                              |
| `swot-analysis`     | Skip        | Low              | None  | A checklist of prompts per quadrant, no evidence rules.                       |
| `brainstorm-okrs`   | Skip        | Low              | None  | `foundation-okr-writer` is far stronger.                                      |
| `positioning-ideas` | Skip        | Low              | None  | Generates five positioning ideas. Not a method.                               |

## sector-skills/nonprofit-skills

Portable: plain Markdown. MIT license. Written for US non-profits.

| Skill                              | Verdict     | Useful to agents | Evals | Notes                                                                  |
| :--------------------------------- | :---------- | :--------------- | :---- | :--------------------------------------------------------------------- |
| `nonprofit-brand-messaging`        | Recommended | High             | None  | Messaging house with mission, vision, pillars, and proof. For the DSF. |
| `nonprofit-corporate-sponsorships` | Consider    | Medium           | None  | Tier design and pitch structure. Not read in full.                     |
| `nonprofit-donor-pipeline`         | Consider    | Medium           | None  | Donor stages and conversion tracking.                                  |
| `nonprofit-program-design`         | Consider    | Medium           | None  | Logic models and theory of change.                                     |
| `nonprofit-volunteer-management`   | Skip        | Low              | None  | 70 lines; too thin to help.                                            |

## anthropics/knowledge-work-plugins and wdavidturner/product-skills

`anthropics/knowledge-work-plugins` is Claude-specific and Apache 2.0. `wdavidturner/product-skills` is portable and MIT.

| Skill                               | Verdict  | Useful to agents | Evals   | Notes                                                                     |
| :---------------------------------- | :------- | :--------------- | :------ | :------------------------------------------------------------------------ |
| `competitive-brief` (Anthropic)     | Skip     | Medium           | None    | Generic competitor research. Our own skill is more specific.              |
| `grant-rfp-writer` (Anthropic)      | Consider | Medium           | None    | Grant discovery and drafting. Not read in full.                           |
| `positioning-canvas` (wdavidturner) | Consider | Medium           | Results | A 105-line take on April Dunford's canvas with "common mistake" patterns. |
| `okrs` (wdavidturner)               | Skip     | Medium           | Results | `foundation-okr-writer` is stronger.                                      |
