# Marketing skills

A review of publicly available agent skills for marketing, to find the ones worth using for our [marketing strategy](../marketing-strategy/README.md) work. Agent skills are Markdown instruction files that teach an AI assistant a specific method, such as running a SWOT analysis.

> ⚠️ This page is a **draft**. Scores are one reviewer's judgment from reading 13 repositories on 2026-10-09. We have not yet run any of the recommended skills on Django material.

## Summary

- **No single repository fits Django.** Almost all are written for commercial software companies. The best results come from picking individual skills across ten repositories.
- **Product strategy is well covered.** We found a strong skill for every format in our [strategy draft](../marketing-strategy/draft/README.md) except a vision statement, where the only option is thin.
- **The five repositories we started with miss our gaps.** None has a usable SWOT, vision, or OKR skill, and none addresses non-profits. Searching further turned up eight more repositories, three of which now rank in our top five.
- **Few skills are tested.** Five repositories ship evals, and only one publishes results. "Has evals" here means test cases exist, not that the skill is proven to work.
- **Licensing is mostly simple.** Twelve repositories are MIT or Apache 2.0. One of the best (`deanpeters/Product-Manager-Skills`) is non-commercial and share-alike: fine to use, but anything we copy or adapt from it keeps that license.

## Recommended skills

Our shortlist for product strategy, in the order the strategy draft needs them. See [recommended skills](recommended-skills.md) for why each was chosen and how to adapt it.

| Strategy step             | Skill                             | Repository                              |
| :------------------------ | :-------------------------------- | :-------------------------------------- |
| Shared context            | `product-marketing`               | `coreyhaines31/marketingskills`         |
| Shared context            | `developer-audience-context`      | `jonathimer/devmarketing-skills`        |
| Audiences                 | `developer-segmentation`          | `samber/developer-relations-skills`     |
| Audiences                 | `foundation-persona`              | `product-on-purpose/pm-skills`          |
| Audience research         | `customer-research`               | `coreyhaines31/marketingskills`         |
| JTBD                      | `define-jtbd-canvas`              | `product-on-purpose/pm-skills`          |
| Competitors analysis      | `devrel-competitor-analysis`      | `samber/developer-relations-skills`     |
| Competitors analysis      | `positioning-map`                 | `pmalliance/product-marketing-skills`   |
| SWOT                      | `swot-analysis`                   | `deanpeters/Product-Manager-Skills`     |
| Positioning               | `obviously-awesome`               | `wondelai/skills`                       |
| Positioning and messaging | `positioning-messaging-framework` | `adam-lagerhausen/b2b-marketing-skills` |
| Messaging (DSF)           | `nonprofit-brand-messaging`       | `sector-skills/nonprofit-skills`        |
| Current state audit       | `message-consistency-check`       | `pmalliance/product-marketing-skills`   |
| Current state audit       | `claim-check`                     | `pmalliance/product-marketing-skills`   |
| Vision statement          | `product-vision`                  | `phuryn/pm-skills`                      |
| OKRs                      | `foundation-okr-writer`           | `product-on-purpose/pm-skills`          |
| Review                    | `good-strategy-bad-strategy`      | `wondelai/skills`                       |
| Review                    | `ai-pmm-reviewer`                 | `adam-lagerhausen/b2b-marketing-skills` |

If we only try three, start with `obviously-awesome`, `swot-analysis`, and `define-jtbd-canvas`: they map directly to the methodology section of the draft and need nothing but the material we already have.

## Repository scores

Scores out of 10. The overall score weights product marketing at 40% and the other three criteria at 20% each. Build quality (usefulness to agents, evals, portability, licensing) is rated separately. See [repository reviews](repository-reviews.md) for the reasoning behind each number.

| Repository                              | Product | Non-profit | Community | Volunteer-driven | Overall | Build quality | License         |
| :-------------------------------------- | :------ | :--------- | :-------- | :--------------- | :------ | :------------ | :-------------- |
| `samber/developer-relations-skills` \*  | 6       | 6          | 9         | 6                | **6.6** | 8             | MIT             |
| `coreyhaines31/marketingskills`         | 7       | 3          | 6         | 5                | **5.6** | 9             | MIT             |
| `deanpeters/Product-Manager-Skills` \*  | 8       | 3          | 2         | 4                | **5.0** | 7             | CC BY-NC-SA 4.0 |
| `wondelai/skills` \*                    | 7       | 2          | 3         | 6                | **5.0** | 6             | MIT             |
| `jonathimer/devmarketing-skills`        | 5       | 2          | 8         | 5                | **5.0** | 5             | MIT             |
| `adam-lagerhausen/b2b-marketing-skills` | 7       | 2          | 2         | 6                | **4.8** | 6             | MIT             |
| `phuryn/pm-skills` \*                   | 6       | 3          | 2         | 5                | **4.4** | 5             | MIT             |
| `sector-skills/nonprofit-skills` \*     | 2       | 8          | 4         | 6                | **4.4** | 5             | MIT             |
| `realjaymes/marketingagentskills`       | 6       | 2          | 2         | 5                | **4.2** | 5             | MIT             |
| `pmalliance/product-marketing-skills`   | 7       | 2          | 1         | 4                | **4.2** | 5             | MIT             |
| `product-on-purpose/pm-skills` \*       | 6       | 3          | 1         | 5                | **4.2** | 9             | Apache 2.0      |
| `anthropics/knowledge-work-plugins` \*  | 5       | 3          | 2         | 5                | **4.0** | 6             | Apache 2.0      |
| `wdavidturner/product-skills` \*        | 6       | 1          | 1         | 4                | **3.6** | 6             | MIT             |

\* Not in the original list of five; found during this review.

How to read this:

- **Overall scores are low on purpose.** A repository built for selling software subscriptions can't score well on non-profit, community, and volunteer criteria. A low overall score doesn't mean its best skills are weak – four of the bottom seven repositories contribute to the shortlist.
- **For product marketing alone**, the leaders are `deanpeters/Product-Manager-Skills` (8), then `coreyhaines31/marketingskills`, `wondelai/skills`, `adam-lagerhausen/b2b-marketing-skills`, and `pmalliance/product-marketing-skills` (all 7).
- **For the Foundation pillar**, only `sector-skills/nonprofit-skills` and the sponsorship skills in `samber/developer-relations-skills` are relevant.
- **For the community pillar**, `samber/developer-relations-skills` and `jonathimer/devmarketing-skills` stand well apart from the rest.

## What we recommend doing next

1. **Try the top three skills on real material** – for example `swot-analysis` on the existing [Django self-audit](../marketing-strategy/competitors-analysis/django-self-audit.md) – and judge the output before adopting anything.
2. **Write a Django context document first.** Most skills read a shared product context file before doing anything. Ours should replace buyers, pricing, and revenue with adopters, sponsors, and contributors, so that every skill inherits the right framing.
3. **Adapt the copies we now have.** The 18 shortlisted skills are in `.agents/skills/`, as published upstream. Our own [competitors analysis skill](../marketing-strategy/competitors-analysis/README.md) is already more specific and stricter on sourcing than any public equivalent. The same approach – trimming each copy to a short Django-specific skill that keeps the method – will serve us better than generic ones.
4. **Decide whether to keep the non-commercial skill.** `swot-analysis` is in `.agents/skills/` under its own CC BY-NC-SA 4.0 license, not this workspace's MIT license. A permissive fallback exists, noted in [recommended skills](recommended-skills.md).

## In this section

- [Recommended skills](recommended-skills.md) – the shortlist with reasoning, adaptations needed, and skills for the Foundation and community pillars.
- [Repository reviews](repository-reviews.md) – the scoring criteria and a review of each repository.
- [Skill reviews](skill-reviews.md) – a skill-by-skill table: usefulness to agents, evals, portability, licensing.
- [Working notes](notes.md) – method, limits of this review, and open questions.
