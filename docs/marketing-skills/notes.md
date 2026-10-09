# Working notes

Method, limits, and open questions behind the [marketing skills review](README.md). Read this if you want to check or repeat the work.

> ⚠️ This page is a **draft** and a work in progress. It records how the review was done and what it leaves unanswered.

## Method

1. Cloned the five repositories we started with into a local, untracked folder (`local/marketing/skills/`) on 2026-10-09.
2. Listed every skill with its description, length, and supporting files, and checked each repository for evals, tests, CI, plugin manifests, and license files.
3. Read the skills relevant to product strategy, then scored each repository against the criteria in [repository reviews](repository-reviews.md).
4. Searched GitHub, skill directories, and curated lists for repositories covering the gaps, cloned eight more, and repeated steps 2 and 3 in less depth.
5. Chose the shortlist using the rules in [recommended skills](recommended-skills.md).

An AI agent (Claude) did the reading and drafting. The search for additional repositories was delegated to a second agent, whose findings on the shortlisted skills were then checked against the files.

## Limits of this review

- **Nothing was run.** Every judgment comes from reading skill files. A skill that reads well can still perform badly, and the reverse.
- **Scores are one reviewer's judgment.** They are useful for ranking and for starting a discussion, not as measurements. A second reviewer would likely move individual scores by a point.
- **Depth varies.** The 18 shortlisted skills were read in full or nearly so, except `developer-segmentation` and `foundation-persona`, where we read the first section and the structure. Skills marked "not read in full" in [skill reviews](skill-reviews.md) were judged on description, headings, and length.
- **The additional repositories got less attention** than the original five. Repositories listed as "considered and not reviewed" were judged on names and descriptions only.
- **The search was incomplete.** GitHub search hit rate limits for some queries (non-profit and community management terms in particular), and one skill directory was only queried for three terms.
- **Figures are a snapshot.** Star counts, contributor counts, and last-commit dates are as of 2026-10-09. Several of these repositories change daily.

## What we checked about evals

"Evals" means different things across repositories:

| Repository                          | What exists                                                                                    |
| :---------------------------------- | :--------------------------------------------------------------------------------------------- |
| `coreyhaines31/marketingskills`     | Test prompts with assertions for all 50 skills. No runner or results in the repository.        |
| `samber/developer-relations-skills` | Test prompts for all 56 skills and a runner script. No results committed, nothing in CI.       |
| `product-on-purpose/pm-skills`      | Trigger tests for 53 skills, output scenarios for 12, and CI workflows to run them (advisory). |
| `wdavidturner/product-skills`       | Three prompts per skill with scored results for two agents, from January 2026.                 |
| `realjaymes/marketingagentskills`   | Test prompts for 2 of 32 skills.                                                               |
| All others                          | None. Some validate file format and metadata in CI, which is not a test of quality.            |

No repository shows evidence that a skill improves results compared with the same agent working without it. If we adopt skills, a small before-and-after comparison on Django material would tell us more than any of the above.

## Observations

- **Many repositories copy one another.** `coreyhaines31/marketingskills` is the template for at least three others here (shared context document, front matter, trigger phrases in descriptions), and several large collections appear to reuse its skills.
- **The shared context document is the common pattern.** Five repositories build one before anything else. It is the natural place to encode what makes Django different from a commercial product.
- **Length is not quality.** The most useful skills were often under 250 lines with a clear method and checks. Several 400–600 line skills are reference material that an agent already knows.
- **Evidence rules are what separate good from average.** The skills we recommend nearly all require sources, label inference, and refuse to invent numbers – the same things our [quality guidelines](../contributing/quality-assurance.md) ask of contributors.
- **Our own competitors analysis skill compares well.** It has stricter sourcing, human review gates, and a Django-specific template. None of the public competitor skills would replace it.

## Gaps nobody covers

- A vision or mission statement skill with any rigor.
- Marketing for a free, community-governed open source project, as opposed to a company's open source product.
- Running marketing with volunteers: handing work over, part-time capacity, review by a working group.
- Individual donor fundraising for an open source foundation (the donor pyramid in our research notes).
- Brand voice for a community with many independent voices.

These are candidates for skills we write ourselves.

## Open questions

- Is a non-commercial, share-alike skill acceptable in this repository? `swot-analysis` is copied under its own license; this decides whether it stays.
- How do we keep the copies in `.agents/skills/` current? Each records the upstream commit it came from, but nothing checks for updates.
- Who reviews agent output produced with these skills before it reaches the strategy draft?
- Should the Django context document live in the [knowledge base](../knowledge-base/README.md), so that it serves people as well as agents?

## Local copies

The 13 repositories are cloned under `local/marketing/skills/`, which is not tracked in git. The six core `pmalliance/product-marketing-skills` skills ship as zip files and need unpacking before they can be read.

| Folder                         | Repository                              | Commit reviewed        |
| :----------------------------- | :-------------------------------------- | :--------------------- |
| `b2b-marketing-skills`         | `adam-lagerhausen/b2b-marketing-skills` | `cce1043` (2026-06-20) |
| `developer-relations-skills`   | `samber/developer-relations-skills`     | `98ed86d` (2026-09-28) |
| `devmarketing-skills`          | `jonathimer/devmarketing-skills`        | `500b44b` (2026-03-03) |
| `knowledge-work-plugins`       | `anthropics/knowledge-work-plugins`     | `ae1513e` (2026-10-07) |
| `marketingagentskills`         | `realjaymes/marketingagentskills`       | `7859da9` (2026-10-07) |
| `marketingskills`              | `coreyhaines31/marketingskills`         | `1efedbc` (2026-10-08) |
| `nonprofit-skills`             | `sector-skills/nonprofit-skills`        | `7d8a2ca` (2026-09-16) |
| `pm-skills`                    | `phuryn/pm-skills`                      | `8607e3b` (2026-09-14) |
| `Product-Manager-Skills`       | `deanpeters/Product-Manager-Skills`     | `1b5a524` (2026-09-01) |
| `product-marketing-skills`     | `pmalliance/product-marketing-skills`   | `2ed9bde` (2026-07-10) |
| `product-on-purpose-pm-skills` | `product-on-purpose/pm-skills`          | `1cef1a9` (2026-09-10) |
| `product-skills`               | `wdavidturner/product-skills`           | `103d654` (2026-01-18) |
| `wondelai-skills`              | `wondelai/skills`                       | `c172996` (2026-09-10) |
