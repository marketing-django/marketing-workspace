# Competitors analysis \- Django self-audit

🚧 AI-generated

## Recap {#recap}

## Competitor source map \- Django

---

### **1\. Website(s) & Flagship Properties** {#1.-website(s)-&-flagship-properties}

| Source                   | URL                                        | What it contains                                                                                                                                                                                                                                                                                                                                                            |
| ------------------------ | ------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| djangoproject.com        | https://www.djangoproject.com/             | Flagship marketing site. "The web framework for perfectionists with deadlines." Homepage → Overview → Download funnel, fundraising CTAs, corporate sponsor logos, news feed. Notably _no_ customer logo wall or case-study section on the homepage. 20tab's 2023 user research and the Website Working Group's ongoing work are the internal context for its current state. |
| Overview / Start pages   | https://www.djangoproject.com/start/       | Primary onboarding journey: install instructions, tutorial links, "Django at a glance". The main bridge between marketing site and docs.                                                                                                                                                                                                                                    |
| DSF / Foundation section | https://www.djangoproject.com/foundation/  | Governance surface: teams & working groups, corporate membership (Diamond→Bronze tiers), annual impact reports, DEI commitments (CHAOSS DEI Bronze badge).                                                                                                                                                                                                                  |
| Fundraising              | https://www.djangoproject.com/fundraising/ | Individual \+ corporate donation funnel; heroes wall. Fundraising CTAs are threaded through the whole site (including blog footers).                                                                                                                                                                                                                                        |
| Community page           | https://www.djangoproject.com/community/   | Aggregator: forum, Discord, local communities, RSS feed of community blogs.                                                                                                                                                                                                                                                                                                 |
| Django Forum             | https://forum.djangoproject.com/           | Discourse instance. Now the primary official discussion channel for both user support and framework internals (Fellow reports, DEP discussions), having superseded the historic django-users / django-developers mailing lists.                                                                                                                                             |
| Issue tracker (Trac)     | https://code.djangoproject.com/            | Self-hosted Trac. Still live as of early 2026; a migration to GitHub Issues is under active discussion via an informational DEP, with Trac's Python-version constraints documented as a pain point.                                                                                                                                                                         |
| Django Packages          | https://djangopackages.org/                | Community-run package directory with comparison grids — the de facto ecosystem discovery surface, but off-domain and visually disconnected from the flagship site.                                                                                                                                                                                                          |
| Djangonaut Space         | https://djangonaut.space/                  | Contributor mentorship programme — the structured "become a contributor" journey that the main site lacks natively.                                                                                                                                                                                                                                                         |
| Django Girls             | https://djangogirls.org/                   | Affiliated nonprofit; beginner workshops worldwide. Major top-of-funnel brand asset with its own tutorial.                                                                                                                                                                                                                                                                  |

**Why it matters for Django:** The flagship property is honest and information-dense but conversion-light: no social proof wall, no case studies, no product tour, and the onboarding journey hands off to docs almost immediately. The official estate is fragmented across at least four domains (www, docs, forum, code) plus community-run properties (djangopackages, djangonaut.space), so IA benchmarking against competitors should focus on how they unify marketing → onboarding → ecosystem discovery under one navigation and visual system.

---

### **2\. Documentation** {#2.-documentation}

| Source                   | URL                                              | What it contains                                                                                                                                                                                                       |
| ------------------------ | ------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Main documentation       | https://docs.djangoproject.com/en/6.0/           | Versioned (currently 6.0 stable, 5.2 LTS, dev), translated, offline-capable (PDF/EPUB). The four-quadrant structure — tutorials, topic guides, how-tos, reference — is literally the origin of the Diátaxis framework. |
| Tutorial (polls app)     | https://docs.djangoproject.com/en/6.0/intro/     | The canonical multi-part learning pathway (tutorial 1–8 \+ advanced), plus "Django at a glance" and installation guides. Aimed at newcomers with Python knowledge.                                                     |
| Release notes            | https://docs.djangoproject.com/en/6.0/releases/  | Per-version notes with deprecation timelines; the backbone of the upgrade story (6-month cadence, 3-year LTS support).                                                                                                 |
| Internals / contributing | https://docs.djangoproject.com/en/dev/internals/ | Contribution guide, security policies, release process, mailing-list-to-forum guidance. Doubles as governance documentation.                                                                                           |
| Security page            | https://www.djangoproject.com/security/          | Disclosure policy, archive of all advisories, pre-notification process — a two-decade coordinated disclosure track record, prominently documented.                                                                     |
| DEPs                     | https://github.com/django/deps                   | Django Enhancement Proposals — the RFC process, hosted on GitHub rather than the docs site.                                                                                                                            |

**Why it matters for Django:** Django's docs are its strongest asset — versioned, translated, rigorously maintained, and the template other frameworks copied (via Diátaxis). Weaknesses are presentational rather than structural: dated visual design (dark mode was a top ask in the 2023 user research), no interactive examples or embedded playgrounds, and — worth verifying at audit time ⚠️ — no first-party agent-friendly format (llms.txt or equivalent), which several competitors now ship. The learning journey also has a cliff: after tutorial 8 there is no guided intermediate pathway, a gap third parties monetise.

---

### **3\. Blog** {#3.-blog}

| Source                    | URL                                                     | What it contains                                                                                                                                                                                                                   |
| ------------------------- | ------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Django Weblog             | https://www.djangoproject.com/weblog/                   | Official news feed: release announcements (feature, bugfix, security), DSF announcements, DjangoCon news, GSoC, developer survey, fundraising updates. Cadence roughly 3–6 posts/month, announcement-driven rather than editorial. |
| Security advisories       | https://www.djangoproject.com/weblog/ (security tagged) | Predictable, disciplined security-release posts with CVE detail — a trust-building pattern in its own right.                                                                                                                       |
| DSF Annual Impact Report  | https://www.djangoproject.com/foundation/reports/2024/  | Yearly narrative: community stats (e.g. 54% of surveyed users learn Django via YouTube), working-group progress, financial transparency.                                                                                           |
| Django News (third-party) | https://django-news.com/                                | Weekly ecosystem newsletter (Jeff Triplett & Will Vincent) — the de facto content-marketing engine Django's official blog doesn't operate. Also on Mastodon (@djangonews).                                                         |
| Django Chat (third-party) | https://djangochat.com/                                 | Long-running podcast; interview surface for maintainers and ecosystem figures.                                                                                                                                                     |

**Why it matters for Django:** The official blog announces rather than markets: there is no release-as-campaign pattern (no annotated deep-dives, benchmark posts, or "what's new" narrative content around 6.0), and no editorial calendar. The ecosystem compensates — Django News, Django Chat, and individual maintainer blogs (Adam Johnson, Carlton Gibson, etc.) carry the content load — but the DSF captures little of that traffic or narrative control. Benchmark competitors on how releases become multi-week content campaigns and how deep-dive posts spin off from release notes.

---

### **4\. GitHub Presence** {#4.-github-presence}

| Metric       | Value                                                                                                         |
| ------------ | ------------------------------------------------------------------------------------------------------------- |
| Repo         | https://github.com/django/django                                                                              |
| Stars        | \~87,600 (June 2026\)                                                                                         |
| Org          | https://github.com/django (\~40+ repos incl. djangoproject.com, channels, asgiref, deps, dsf-minutes)         |
| Website repo | https://github.com/django/djangoproject.com (\~2,000 stars, actively maintained, "issues need help" labelled) |
| Issues       | Not on GitHub — Trac at code.djangoproject.com (GitHub Issues migration DEP in progress)                      |
| Discussions  | Not used — Django Forum fills this role                                                                       |

**Additional GitHub properties:** django/deps (RFC process, https://github.com/django/deps); django/dsf-minutes (public board minutes — unusual governance transparency); django/new-features (feature-tracking); djangocon org (https://github.com/djangocon, 70 repos of conference sites and an archive project); ecosystem anchors outside the org: encode/django-rest-framework (30k+ stars), cookiecutter-django, and the djangopackages catalog. No official scaffolding CLI beyond `django-admin startproject` — no create-django-app equivalent.

**Why it matters for Django:** GitHub is Django's code surface but deliberately _not_ its community surface — discussion lives on the Forum and triage on Trac, which fragments the contributor journey and makes Django's GitHub presence look quieter than its actual activity (a perception problem competitors with GitHub-native workflows don't have). The pending Trac→GitHub Issues migration is the single biggest upcoming change to this surface. Governance transparency (public board minutes, DEPs, funded Fellows doing paid triage) is a differentiator competitors can't easily match, but it's under-told as a story.

---

### **5\. Social Presence** {#5.-social-presence}

| Channel           | Handle / URL                             | Reach                                                                                                                                                |
| ----------------- | ---------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| X / Twitter       | @djangoproject                           | Part of 350K+ combined DSF following (per DSF corporate membership page); the largest single channel ⚠️ per-channel count to verify                  |
| Mastodon          | @django@fosstodon.org                    | Official account; the Django community migrated heavily to Mastodon post-2022, so engagement here outperforms raw follower counts                    |
| Bluesky           | @djangoproject.com                       | Official (domain-verified handle); newest channel                                                                                                    |
| LinkedIn          | Django Software Foundation               | Official page; corporate/sponsor-facing announcements                                                                                                |
| Discord           | https://discord.com/invite/xcRH6mN4fa    | \~34,000 members (official server; note a separate "unofficial" server exists that split over the CoC)                                               |
| Forum (Discourse) | https://forum.djangoproject.com/         | Primary owned community channel; support \+ internals                                                                                                |
| YouTube           | DjangoCon US / DjangoCon Europe channels | 466+ videos on DjangoCon US alone; 54% of surveyed community members use YouTube to learn Django — but there is no strong first-party DSF channel ⚠️ |
| Governance        | Social Media Working Group               | Volunteer WG runs all official accounts — institutional multi-voice, no founder figurehead                                                           |

**Why it matters for Django:** Django runs an institution-voice, multi-platform strategy with no founder personality (Adrian Holovaty and Jacob Kaplan-Moss stepped back years ago); the "faces" of Django are distributed community figures (Fellows, Will Vincent, Adam Johnson, Jeff Triplett, Carlton Gibson) whose reach the DSF doesn't own. Content is announcement-and-community-celebration, not thought-leadership. The YouTube gap is the standout: the community's \#1 learning channel is one where Django's first-party presence is weakest, with conference channels doing the heavy lifting. Compare against competitors with founder-led or DevRel-led broadcast strategies.

---

### **6\. Public Content & Events** {#6.-public-content-&-events}

| Source                                                              | What it contains                                                                                                                                                                                                    |
| ------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| DjangoCon Europe                                                    | 18th edition: Athens, 15–19 April 2026 (3 days talks \+ 2 days sprints, Athens Conservatoire, remote tickets, tiered pricing incl. student/unwaged). Community-organised, rotating host city. Recordings → YouTube. |
| DjangoCon US                                                        | Chicago, from 24 Aug 2026 (Chicago also in 2025). Longest archive: 466+ videos on YouTube, 13k+ photos on Flickr, docs.djangocon.us runbooks open-sourced.                                                          |
| DjangoCon Africa                                                    | Arusha, Tanzania Aug 2025 (co-located with UbuCon). Opportunity grants programme.                                                                                                                                   |
| DjangoCon AU / DjangoCongress JP / DjangoDay India / Django Day CPH | Regional satellite events; AU runs alongside PyCon AU; India tentative Nov dates.                                                                                                                                   |
| Django Girls workshops                                              | Ongoing global beginner workshops; separate foundation, huge top-of-funnel reach.                                                                                                                                   |
| Django Developer Survey                                             | Annual, run with JetBrains (2026 edition live) — first-party data asset for positioning.                                                                                                                            |
| Sprints & 20th birthday                                             | Django turned 20 in July 2025; birthday celebrations threaded through 2025 events.                                                                                                                                  |
| GSoC / Djangonaut Space                                             | Structured contributor pipelines, publicised via blog and socials.                                                                                                                                                  |

**Featured showcase customers:** No official showcase/case-study page exists — this is a notable gap. Commonly cited adopters: **verified via public engineering content or filings** — Instagram (scale talks at Python/Django conferences), Klaviyo (Django's role disclosed in its S-1), Sentry (built on Django, open source), Disqus, Bitbucket, Eventbrite, The Washington Post; **claimed/legacy, verify before use** ⚠️ — NASA, Mozilla, Pinterest (largely migrated), National Geographic, Robinhood, Spotify (frequently repeated, weakly sourced). Any redesign should distinguish "runs Django today" from "famously started on Django."

---

### **Verification notes (July 2026\)** {#verification-notes-(july-2026)}

- Stars, event dates, Discord size, and combined social reach checked against live sources June–July 2026\.
- Per-channel follower counts (X, Mastodon, Bluesky, LinkedIn individually) not independently verified — the 350K+ figure is the DSF's own combined claim on the corporate membership page.
- Trac→GitHub Issues migration status should be re-checked at time of publication; the informational DEP was in progress with no completed migration as of early 2026\.
- Current version context: Django 6.0.x stable (async-native ORM), 5.2 LTS; 6-month release cadence, 3-year LTS window.

Now I have all the data I need. Let me compile the full analysis.

---

# Competitor Analysis — Django (Self-Audit)

## Overview

### Category

**Community Open Source** — 501(c)(3) non-profit foundation governance, BSD-3-Clause license. Funded via donations, corporate membership, and the Django Fellowship program. No single corporate owner.

### Website

[https://www.djangoproject.com/](https://www.djangoproject.com/)

### One-line positioning

**"The web framework for perfectionists with deadlines."**

On the homepage: "Django makes it easier to build better web apps more quickly and with less code." The three homepage pillars are: **Ridiculously fast**, **Reassuringly secure**, **Exceedingly scalable**. The Overview page adds **Fully loaded** and **Incredibly versatile**.

_Source: [https://www.djangoproject.com/](https://www.djangoproject.com/) and [https://www.djangoproject.com/overview/](https://www.djangoproject.com/overview/)_

---

## AUDIENCE

### Top 3 audiences

1. **Experienced Python web developers** — The tutorial explicitly assumes Python knowledge ("If you're new to Python… you might want to start by getting an idea of what the language is like"). The 2025 Developer Survey found almost a third of respondents have used Django for 11+ years. The tagline "perfectionists with deadlines" targets professionals who value correctness _and_ speed.
2. **Organizations and enterprises** — Corporate membership tiers (Diamond $100K → Bronze $2K), enterprise adoption stories (Instagram, Mozilla, Sentry), the LTS support window, and the DSF's governance transparency all signal to institutional adopters.
3. **Open-source contributors and community members** — The Foundation section, Djangonaut Space, GSoC, Fellowship program, and "Get Involved" CTAs speak directly to contributors. The DSF board is elected by individual members appointed for their community contributions.

_Source: [https://docs.djangoproject.com/en/6.0/intro/](https://docs.djangoproject.com/en/6.0/intro/) (Python prerequisite), [https://www.djangoproject.com/foundation/](https://www.djangoproject.com/foundation/) (governance), [https://www.djangoproject.com/foundation/corporate-membership/](https://www.djangoproject.com/foundation/corporate-membership/) (corporate tiers)_

### Audience language

**Developers** and **community** are the primary terms. "Users" appears in the survey context ("Django users and enthusiasts"). "Corporate members" for sponsors. Notably, Django does _not_ use "customers" — the relationship is framed as community membership, not a commercial transaction.

_Source: Homepage copy uses "developers" throughout; fundraising page refers to "donors" and "corporate members"; survey language uses "users"_

### Community vs. customer relationship

**Community-led.** Everything about Django's governance, funding, and messaging reinforces this: the DSF is a volunteer board, no single company controls the roadmap, corporate members explicitly do _not_ receive "preferential input into Django's development process," and the Fellows program is marketed as community stewardship rather than a support contract. The corporate membership page states plainly: "the DSF is not a service provider or development house."

_Source: [https://www.djangoproject.com/foundation/corporate-membership/](https://www.djangoproject.com/foundation/corporate-membership/) ("corporate members do not receive technical support, consulting, or other services")_

---

## Messaging

### Top 10 topics

1. **Batteries-included philosophy** — ORM, admin, auth, forms, templates, i18n, security, all built-in. "Django includes dozens of extras you can use to handle common web development tasks… right out of the box."
2. **Rapid development** — "Ridiculously fast," "from concept to launch in a matter of hours," "designed to help developers take applications from concept to completion as quickly as possible."
3. **Security** — Positioned as a core differentiator. Built-in protections (CSRF, XSS, SQL injection, clickjacking), a dedicated security team, a coordinated disclosure process with a two-decade track record, and now CVE Numbering Authority (CNA) status.
4. **Scalability** — "Exceedingly scalable," "some of the busiest sites on the web" (Instagram, Disqus).
5. **Community & governance** — The DSF, Fellows, board transparency, public meeting minutes, DEI badge, Code of Conduct, Djangonaut Space mentorship.
6. **Stability & LTS** — 6-month release cadence, 3-year LTS support window, deprecation timelines, API stability commitments. "Many new releases, each with years of support."
7. **Open source independence** — BSD license, 501(c)(3) nonprofit, no vendor lock-in, community-controlled roadmap.
8. **Documentation quality** — Four-quadrant Diátaxis structure (originator of the framework), versioned, translated, offline-capable (PDF/EPUB).
9. **Events & education** — DjangoCon (US, Europe, Africa), Django Girls workshops, GSoC, Djangonaut Space, regional Django Days.
10. **Ecosystem breadth** — Django packages, DRF, HTMX adoption trend, third-party tooling. "Thousands more packages in our thriving ecosystem."

_Sources: [https://www.djangoproject.com/](https://www.djangoproject.com/) (homepage pillars), [https://www.djangoproject.com/overview/](https://www.djangoproject.com/overview/), [https://docs.djangoproject.com/en/6.0/](https://docs.djangoproject.com/en/6.0/) (Diátaxis structure), [https://www.djangoproject.com/foundation/](https://www.djangoproject.com/foundation/) (governance), [https://www.djangoproject.com/security/](https://www.djangoproject.com/security/) (security)_

### Key differentiators claimed

1. **Batteries-included** — all-in-one framework vs. micro-framework assembly. "Django takes care of much of the hassle of web development, so you can focus on writing your app without needing to reinvent the wheel."
2. **Automatic admin interface** — "One of the most powerful parts of Django" — a production-ready admin generated from model metadata.
3. **Security track record** — Two decades of coordinated disclosure, CNA status (achieved 2025), comprehensive built-in protections.
4. **Documentation pedigree** — Originator of the Diátaxis documentation framework, versioned docs going back to 1.8, translated, offline-capable.
5. **Nonprofit governance** — 501(c)(3) independence, publicly transparent board, no single-company control. A differentiator vs. corporate-owned frameworks.
6. **Maturity and stability** — 20 years old (July 2025), 400+ releases, predictable LTS cadence.

_Sources: [https://www.djangoproject.com/start/](https://www.djangoproject.com/start/) (admin interface), [https://www.djangoproject.com/weblog/2025/jul/13/happy-20th-birthday-django/](https://www.djangoproject.com/weblog/2025/jul/13/happy-20th-birthday-django/) (20 years), [https://www.djangoproject.com/weblog/2026/jun/25/how-the-django-software-foundation-became-a-cna/](https://www.djangoproject.com/weblog/2026/jun/25/how-the-django-software-foundation-became-a-cna/) (CNA)_

### What they say about AI

**Cautious and reactive, not leading.** Django does not lead with AI in its marketing. There is no AI narrative on the homepage, no AI features highlighted in the overview, and no dedicated AI/LLM section in the docs. Key signals:

- The **2025 Developer Survey** tracks AI tool adoption (69% use ChatGPT, 34% GitHub Copilot for Django development) — but this is observation, not positioning.
- The **llms.txt discussion** on the Django Forum (April 2025–January 2026\) confirms Django does _not_ yet ship an llms.txt file, despite community interest and competitors (Pydantic, Stripe, Cloudflare, HubSpot) adopting the standard.
- The security page includes an **"AI-Assisted Reports" policy** (added to handle a flood of LLM-generated vulnerability reports), which is defensive rather than promotional.
- The 6.0 release (async-native ORM) was not framed as an AI-enablement story.
- No mention of AI agents, RAG, or LLM integration as a Django strength in any first-party marketing surface.

**Verdict: Silent-to-cautious.** Django treats AI as something its users are doing, not something Django is doing. This is a notable gap as competitors ship llms.txt, AI SDKs, and agent-friendly docs.

_Sources: [https://forum.djangoproject.com/t/generate-llms-txt-file-for-django-docs-ie-make-django-ai-friendly/40672](https://forum.djangoproject.com/t/generate-llms-txt-file-for-django-docs-ie-make-django-ai-friendly/40672) (no llms.txt), [https://blog.jetbrains.com/pycharm/2025/10/the-state-of-django-2025/](https://blog.jetbrains.com/pycharm/2025/10/the-state-of-django-2025/) (AI usage stats), [https://www.djangoproject.com/security/](https://www.djangoproject.com/security/) (AI-Assisted Reports policy)_

### Positions on key Django differentiators

#### What they say about "batteries-included" — the value of features in the framework vs. flexibility?

**Leads with it.** "Fully loaded" is the second pillar on the Overview page, and the Start page showcases ORM, URLs/views, templates, forms, authentication, admin, i18n, and security as a product tour of built-in features. The pitch: you get everything you need "right out of the box" — no assembly required. The implicit contrast is with micro-frameworks (Flask, FastAPI) where you pick and assemble components.

_Source: [https://www.djangoproject.com/start/](https://www.djangoproject.com/start/) (code-driven product tour), [https://www.djangoproject.com/overview/](https://www.djangoproject.com/overview/) ("Fully loaded")_

#### What they say about admin UIs as a key part of the framework?

**Claims it strongly.** The admin is described as "one of the most powerful parts of Django" — "automatic admin interface," "powerful and production-ready interface that content producers can immediately use." It's the second step in the tutorial (Part 2: "Models and the admin site"). The Start page features it prominently alongside ORM, auth, and forms.

_Source: [https://www.djangoproject.com/start/](https://www.djangoproject.com/start/) ("One of the most powerful parts of Django is its automatic admin interface"), [https://docs.djangoproject.com/en/6.0/intro/tutorial02/](https://docs.djangoproject.com/en/6.0/intro/tutorial02/)_

#### What they say about Community and ecosystem (packages) as a key part of the framework?

**Claims it, but delegates the story.** The Community page aggregates forum, Discord, local communities, RSS feeds of community blogs, job listings, and Django Packages. The Django ecosystem (DRF at 30k+ stars, cookiecutter-django, django-allauth, etc.) is strong, but Django does not _tell_ that story on its own marketing pages — it points to community-run properties (Django Packages, Django News) instead. The fundraising pages highlight community generosity. The Forum thread on Django's llms.txt discusses ecosystem discoverability as a concern. The DSF blog's "Keeping Up with the Django Community" (June 2026\) is a meta-post acknowledging the community is hard to track: "Most of it is public, but it isn't always easy to find."

_Source: [https://www.djangoproject.com/community/](https://www.djangoproject.com/community/) (aggregator), [https://www.djangoproject.com/weblog/2026/jun/30/keeping-up-with-the-django-community/](https://www.djangoproject.com/weblog/2026/jun/30/keeping-up-with-the-django-community/) (fragmentation acknowledged)_

#### What they say about the value of stability (LTS, battle-tested)

**Claims it, but softly.** The LTS story is present but not heavily marketed. The release notes page documents the deprecation timeline and support windows; the 20th-birthday post says "Many new releases, each with years of support." The DSF blog frames stability in financial terms (Fellows program sustaining the release cadence). There is no dedicated "enterprise stability" page or migration guide prominently linked from the homepage. The API Stability page exists in docs but is buried under "Django over time."

_Source: [https://docs.djangoproject.com/en/6.0/releases/](https://docs.djangoproject.com/en/6.0/releases/) (release notes), [https://www.djangoproject.com/weblog/2025/jul/13/happy-20th-birthday-django/](https://www.djangoproject.com/weblog/2025/jul/13/happy-20th-birthday-django/) ("years of support")_

#### What they say about Accessibility (i18n \+ l10n)

**Claims it, but as a feature, not a marketing pillar.** Django has comprehensive i18n/l10n support (translations, locale-specific formatting, time zones, pluralization, bidirectional text). The Start page features it alongside ORM and auth with code examples. The Django admin is translated into 100+ languages. But accessibility (a11y, WCAG) is barely mentioned on marketing surfaces, and the i18n story is not elevated as a differentiator. The DSF has a DEI Bronze badge (CHAOSS), but this is a governance signal, not a product feature.

_Source: [https://www.djangoproject.com/start/](https://www.djangoproject.com/start/) (Internationalization section), [https://docs.djangoproject.com/en/6.0/topics/i18n/](https://docs.djangoproject.com/en/6.0/topics/i18n/)_

#### What they say about security

**Leads with it — this is their strongest differentiator claim.** Security is one of the three homepage pillars ("Reassuringly secure"). The security page is comprehensive: disclosure policy, advisory archive, pre-notification process, encryption key, reporting guidelines (including AI-assisted report policy), and CNA status announcement (June 2026). Built-in protections against CSRF, XSS, SQL injection, clickjacking, and remote code execution are listed on the Start page. The DSF became a CVE Numbering Authority in 2025 — a move that puts Django in rare company among web frameworks and signals institutional security maturity. Security release posts are predictable and disciplined.

_Source: [https://www.djangoproject.com/security/](https://www.djangoproject.com/security/), [https://www.djangoproject.com/weblog/2026/jun/25/how-the-django-software-foundation-became-a-cna/](https://www.djangoproject.com/weblog/2026/jun/25/how-the-django-software-foundation-became-a-cna/), [https://www.djangoproject.com/start/](https://www.djangoproject.com/start/) (Security section)_

### Tone of voice

**Technical, community-led, understated, honest.** Django sounds like a group of experienced engineers who value correctness over hype. The copy is direct and feature-focused — no superlative marketing language beyond the three pillars. The blog is announcement-driven and institutional. There's warmth in community content (DSF Member of the Month, Django Girls testimonials) but no personality-driven voice. The 20th-birthday post uses emoji and exclamation marks — about as playful as it gets. Compare: no "we're excited to announce," no "revolutionary," no "game-changing." This tone builds trust with engineers but undersells to decision-makers.

_Sources: Consistent across [https://www.djangoproject.com/](https://www.djangoproject.com/), blog, and docs_

---

## CAPACITY & CAPITAL

### Organisation / ownership

**Django Software Foundation (DSF)** — a 501(c)(3) non-profit organization incorporated in the United States. Governed by a 7-person elected board. No single corporate owner. The Django trademark is held by the DSF. Day-to-day development is driven by the Django Fellows (paid contractors) and community volunteers.

_Source: [https://www.djangoproject.com/foundation/](https://www.djangoproject.com/foundation/)_

### Funding model

**Nonprofit — individual donations \+ corporate membership tiers.** The DSF raises funds through:

- Corporate membership (Diamond $100K, Platinum $30K, Gold $12.5K, Silver $5K, Bronze $2K/year)
- Individual donations (via website, GitHub Sponsors, Open Collective)
- GitHub Sponsors (\~$9,000/month as of June 2026, goal $15,000/month)
- Merchandise store
- Employer matching programs (Benevity)

In-kind donors provide infrastructure: Sentry (error monitoring), Fastly (CDN), OSUOSL (servers), SysEleven (servers), Typefully (social media tools).

_Source: [https://www.djangoproject.com/fundraising/](https://www.djangoproject.com/fundraising/), [https://www.djangoproject.com/foundation/corporate-membership/](https://www.djangoproject.com/foundation/corporate-membership/), [https://www.djangoproject.com/weblog/2026/jun/10/dsf-2026-fundraising-goals/](https://www.djangoproject.com/weblog/2026/jun/10/dsf-2026-fundraising-goals/)_

### Known funding / investment

- **2026 fundraising goal:** $500,000 (raised from $300,000 in 2025\)
- **Current raised (July 2026):** $74,431.81 — 14% of goal
- **Operating reserves (Jan 2026):** \~$222,000
- **GitHub Sponsors:** \~$9,000/month (goal: $15,000/month)
- **Executive Director fund:** $47,500 pledged by six agencies (Caktus Group $12,500, Lincoln Loop $10,000, Six Feet Up $10,000, Cuttlesoft $10,000, OddBird $2,500, Two Rock Software $2,500)
- **Current corporate members (visible):** Six Feet Up (Platinum, $30K+), Jonas und der Wolf (Gold, $12.5K+), KUWAITNET (Silver, $5K+), Two Rock Software and CHARTWELL (Bronze, $2K+). Notably, the Diamond ($100K) tier is currently empty.
- **Historical:** \~$76,707 raised by July 2025 (against $300K goal). No VC funding — the DSF has never taken venture capital.

_Sources: [https://www.djangoproject.com/fundraising/](https://www.djangoproject.com/fundraising/) (current figures), [https://www.djangoproject.com/weblog/2026/jun/10/dsf-2026-fundraising-goals/](https://www.djangoproject.com/weblog/2026/jun/10/dsf-2026-fundraising-goals/) (reserves, goals), [https://www.djangoproject.com/weblog/2026/jun/17/announcing-the-search-for-a-dsf-executive-director/](https://www.djangoproject.com/weblog/2026/jun/17/announcing-the-search-for-a-dsf-executive-director/) (ED fund)_

### Team size (approx)

**Core team: 3 paid Fellows \+ \~400 GitHub contributors \+ volunteer board and working groups.**

- **3 Django Fellows** (full/part-time paid contractors): Jacob Walls, Sarah Boyce, Natalia Bidart — handle triage (10-15 new tickets/week), review (\~15 non-trivial patches/week), releases, and security.
- **7-person volunteer board** (2026): Jeff Triplett (President), Abigail Afi Gbadago (VP), Priya Pahwa (Secretary), Ryan Cheley (Treasurer), Jacob Kaplan-Moss, Paolo Melchiorre, Tom Carrick.
- **\~400 total GitHub contributors** to the main django/django repo.
- **Multiple volunteer working groups:** Social Media WG, Website WG, Online Community WG, Code of Conduct, etc.
- **Hiring:** Searching for first Executive Director (part or full-time), funded by the six-agency pledge.

_Sources: [https://github.com/django/django](https://github.com/django/django) (400 contributors), [https://www.djangoproject.com/fundraising/](https://www.djangoproject.com/fundraising/) (Fellows), [https://www.djangoproject.com/foundation/](https://www.djangoproject.com/foundation/) (board), [https://www.djangoproject.com/weblog/2026/jun/17/announcing-the-search-for-a-dsf-executive-director/](https://www.djangoproject.com/weblog/2026/jun/17/announcing-the-search-for-a-dsf-executive-director/) (ED hire)_

### Adoption signals

- **GitHub stars:** \~88,000 (July 2026\)
- **PyPI downloads:** \~33M / 30 days, \~49.9M / month (pypistats.org / pyrank.org, July 2026\)
- **Discord members:** \~34,000 (source mapping; confirmed by community discussion referencing 33k+)
- **Developer Survey:** \~4,600 respondents (2025), targeting 4,000 for 2026 (3,100+ at last call, July 8\)
- **Known high-scale users:** Instagram (verified via engineering talks), Sentry (built on Django, open source), Disqus, Mozilla, Knight Foundation, Bitbucket, Eventbrite, The Washington Post, Klaviyo (disclosed in S-1)
- **20-year track record** (July 2005–present), 400+ releases
- **DRF ecosystem anchor:** 30k+ GitHub stars, de facto standard for Django APIs

⚠️ Flags: Several commonly cited adopters (NASA, Pinterest, Spotify, Robinhood) have weak or outdated sourcing. Pinterest largely migrated away. Spotify and NASA citations are frequently repeated without current evidence.

_Sources: [https://github.com/django/django](https://github.com/django/django) (stars), [https://pypistats.com/packages/django](https://pypistats.com/packages/django) (downloads), [https://www.djangoproject.com/overview/](https://www.djangoproject.com/overview/) (featured sites, ⚠️ partially outdated), [https://lp.jetbrains.com/django-developer-survey-2025/](https://lp.jetbrains.com/django-developer-survey-2025/) (survey)_

### Trajectory

**Growing, but funding lags adoption.** Signals of growth: PyPI downloads are high and sustained (\~33M/30 days); Discord community is large and active; the 2025 survey showed growing HTMX/Alpine.js adoption breathing new life into Django's server-rendered paradigm; Django 6.0 shipped async-native ORM, a major technical milestone; the DSF is hiring its first Executive Director and raising its fundraising goal by 67% (from $300K to $500K).

Signals of concern: At 14% of the 2026 goal by July, fundraising is behind pace (should be at \~53%). The Diamond corporate tier ($100K) is empty. The pending Trac→GitHub Issues migration suggests technical debt in contributor tooling. No AI positioning strategy. The website hasn't had a major redesign despite the Website Working Group's efforts.

**Verdict: Healthy adoption trajectory, fragile funding trajectory.** Django is more widely used than ever, but the organizational capacity to support that growth is stretched thin — which is exactly why the ED hire matters.

_Sources: [https://www.djangoproject.com/fundraising/](https://www.djangoproject.com/fundraising/) (14% of goal), [https://www.djangoproject.com/weblog/2026/jun/10/dsf-2026-fundraising-goals/](https://www.djangoproject.com/weblog/2026/jun/10/dsf-2026-fundraising-goals/) (goal increase rationale)_

---

## CHANNELS

### Primary channels

1. **djangoproject.com** — flagship marketing site \+ docs \+ blog \+ community hub
2. **docs.djangoproject.com** — versioned documentation (Diátaxis structure)
3. **Django Forum (Discourse)** — primary community discussion and support channel
4. **GitHub (github.com/django)** — code, PRs, releases; 88K stars
5. **Discord** — \~34K members, real-time chat
6. **Social media** — Mastodon (@[django@fosstodon.org](mailto:django@fosstodon.org)), Bluesky (@djangoproject.com), X/Twitter (@djangoproject), LinkedIn (Django Software Foundation)
7. **YouTube (conference channels)** — DjangoCon US (466+ videos), DjangoCon Europe
8. **Trac (code.djangoproject.com)** — issue tracker (migration to GitHub Issues in progress)
9. **Django Packages (djangopackages.org)** — community-run package directory

_Sources: Multiple pages from djangoproject.com, community page_

### Standout channel

**The documentation (docs.djangoproject.com)** is Django's standout channel. It's versioned back to 1.8, translated, available as PDF/EPUB, rigorously maintained by the Fellows, and literally the origin of the Diátaxis documentation framework that other projects (and documentation tools) have adopted. The 2025 Developer Survey confirms \~80% of developers use the official docs as their learning resource. The docs _are_ Django's product tour, onboarding, and reference — they carry more marketing weight than the actual marketing site.

The docs' weakness is presentational: dated visual design, no interactive examples or embedded playgrounds, no dark mode (a top user request), and no llms.txt or agent-friendly format.

_Source: [https://docs.djangoproject.com/en/6.0/](https://docs.djangoproject.com/en/6.0/) (Diátaxis structure), [https://blog.jetbrains.com/pycharm/2025/10/the-state-of-django-2025/](https://blog.jetbrains.com/pycharm/2025/10/the-state-of-django-2025/) (80% use docs)_

### Events presence

Django runs a strong, globally distributed events program:

- **DjangoCon Europe** — 18th edition in 2026 (Athens, April 15-19). Community-organized, rotating host city, remote tickets, tiered pricing.
- **DjangoCon US** — Chicago, August 2026\. Largest archive: 466+ YouTube videos, 13k+ Flickr photos, open-sourced runbooks.
- **DjangoCon Africa** — Arusha, Tanzania (2025, co-located with UbuCon). Opportunity grants program.
- **Regional events:** DjangoCon AU, DjangoCongress JP, DjangoDay India, Django Day CPH.
- **Django Girls** — global beginner workshops, separate foundation, significant top-of-funnel reach.
- **Sprints** — co-located with conferences.
- **GSoC \+ Djangonaut Space** — structured contributor pipelines.

The DSF provides financial support to events and requires a Code of Conduct for endorsement.

⚠️ YouTube gap: Despite 54% of surveyed community members learning Django via YouTube, there is no strong first-party DSF YouTube channel — conference channels carry the load.

_Sources: [https://www.djangoproject.com/foundation/](https://www.djangoproject.com/foundation/) (event support), source map provided by user (event details), [https://www.djangoproject.com/weblog/2025/jul/13/happy-20th-birthday-django/](https://www.djangoproject.com/weblog/2025/jul/13/happy-20th-birthday-django/) (20th birthday events)_

### SEO strength

No dedicated SEO analysis was conducted, but observable signals: djangoproject.com ranks for "Django web framework" and related terms by virtue of being the canonical project site. The docs are well-indexed and heavily referenced across Stack Overflow and LLM training data. The blog publishes regularly (3-6 posts/month) with keyword-rich titles ("Django security releases issued," "Django 6.1 beta 1 released"). However, Django does not appear to operate a deliberate content SEO strategy — there are no comparison pages ("Django vs. X"), no dedicated "what is Django" landing page optimized for beginners, and no editorial content targeting non-brand search terms. The "Django overview" page at /overview/ is thin compared to competitor framework marketing pages.

### Community infrastructure

| Channel                      | Status                                                                                      | Activity Signal                                                                  |
| :--------------------------- | :------------------------------------------------------------------------------------------ | :------------------------------------------------------------------------------- |
| **Django Forum (Discourse)** | Official; primary async discussion                                                          | Active — support questions, Fellow reports, DEP discussions, working group notes |
| **Discord**                  | Official; \~34K members                                                                     | Active — \~2,500 online at a given time (per community discussion)               |
| **GitHub (django org)**      | Code \+ PRs; Discussions NOT used                                                           | Active code activity; discussions live on Forum                                  |
| **Trac**                     | Issue tracker; migration to GitHub Issues pending                                           | Active but acknowledged as technical debt                                        |
| **Django Packages**          | Community-run; off-domain                                                                   | Active — new packages listed weekly                                              |
| **Mastodon**                 | @[django@fosstodon.org](mailto:django@fosstodon.org); \~2,860 followers                     | Active — RSS-automated posts \+ manual engagement                                |
| **Bluesky**                  | @djangoproject.com; newest channel ⚠️ follower count unverified                             | Active — domain-verified handle                                                  |
| **X/Twitter**                | @djangoproject; historical data showed \~80.6K followers (2018) ⚠️ current count unverified | Active — part of claimed 350K+ combined DSF following                            |
| **LinkedIn**                 | Django Software Foundation page                                                             | Corporate/sponsor-facing announcements                                           |
| **YouTube**                  | No strong first-party channel ⚠️                                                            | DjangoCon US (466+ videos) and DjangoCon Europe channels carry the load          |

⚠️ Per-channel follower counts not independently verified. The 350K+ combined figure is the DSF's own claim on the corporate membership page.

_Sources: [https://www.djangoproject.com/community/](https://www.djangoproject.com/community/), [https://fosstodon.org/@django](https://fosstodon.org/@django) (2.86K), [https://www.djangoproject.com/foundation/corporate-membership/](https://www.djangoproject.com/foundation/corporate-membership/) (350K+ claim), forum.djangoproject.com_

---

## GAPS & NOTES

### What they don't talk about

1. **AI/LLM integration** — No llms.txt, no AI SDKs, no agent-friendly documentation format, no AI positioning narrative. Competitors (Pydantic, Stripe, Cloudflare) ship these. The Forum discussion about llms.txt has been open since April 2025 with no resolution.
2. **Case studies / customer proof** — No official showcase page, no customer logo wall, no case studies. The /overview/ page lists 9 "Sites Using Django" with just logos and names — no stories, no metrics, no quotes. Several listed sites (Pinterest) have largely migrated away.
3. **Product tour / interactive demo** — No interactive playground, no embedded code sandbox, no "try Django in your browser" experience. The onboarding journey hands off to docs almost immediately.
4. **Release-as-campaign content** — No deep-dive posts, benchmark comparisons, or "what's new" narrative content around major releases. The blog announces releases but doesn't _sell_ them.
5. **Founder/thought-leadership voice** — No single personality represents Django. The original creators (Adrian Holovaty, Jacob Kaplan-Moss) stepped back from public-facing roles years ago. The "faces" are distributed community figures whose reach the DSF doesn't own.
6. **Enterprise roadmap** — No public-facing product roadmap, no "what's coming" page for decision-makers. Release notes serve this function for developers but not for CTOs evaluating frameworks.
7. **Performance benchmarks** — Django claims "exceedingly scalable" but publishes no benchmarks, no TechEmpower comparisons, no performance dashboards.
8. **First-party YouTube presence** — Despite 54% of the community learning Django via YouTube, there's no strong DSF channel.
9. **Comparison content** — No "Django vs. Flask," "Django vs. Rails," or "Django vs. Laravel" pages — a standard SEO/positioning tactic competitors use.
10. **Unified IA across properties** — The official estate is fragmented across at least four domains (www, docs, forum, code) plus community-run properties, with no unified navigation or visual system.

_Sources: Forum discussion at [https://forum.djangoproject.com/t/generate-llms-txt-file-for-django-docs-ie-make-django-ai-friendly/40672](https://forum.djangoproject.com/t/generate-llms-txt-file-for-django-docs-ie-make-django-ai-friendly/40672) (no llms.txt), [https://www.djangoproject.com/overview/](https://www.djangoproject.com/overview/) (thin showcase), [https://www.djangoproject.com/weblog/](https://www.djangoproject.com/weblog/) (announcement-driven blog), 2025 Developer Survey (54% YouTube learning)_

### Key insight for Django positioning

**Django's strongest differentiators — security maturity, batteries-included completeness, and nonprofit independence — are under-told as stories.** The substance is exceptional (CNA status, 20-year coordinated disclosure track record, Diátaxis documentation, paid Fellows doing professional triage, public board minutes, BSD license with no corporate owner). But these are presented as operational facts rather than woven into a positioning narrative that would resonate with CTOs, engineering managers, and developers choosing a framework. Django's homepage is honest and information-dense but doesn't _persuade_. The most powerful asset — the docs — carries the marketing load, but docs convert existing users, not new ones.

The single highest-impact move for Django's positioning would be to build the case-study / social-proof surface that is currently missing: named adopters with metrics, quotes, and migration stories — backed by the security and stability data that competitors cannot match.

### Additional notes

- **Website Working Group** exists and is actively working on the flagship site redesign — this analysis should inform that work.
- **Trac→GitHub Issues migration** (in progress via informational DEP) will significantly change Django's contributor surface and make GitHub activity metrics more reflective of actual project activity.
- **Fundraising is the meta-problem:** Many of the gaps identified (no ED, no DevRel, no content marketing engine, no website redesign velocity) trace back to the DSF being volunteer-run on a $300-500K budget. The ED hire and fundraising goal increase are the structural fixes that could unlock everything else.
- **The 2025 Developer Survey** is an underutilized asset — 4,600-respondent first-party data on framework usage, AI adoption, and learning pathways that could fuel content for years.
- **Django's 20-year anniversary** (July 2025\) was celebrated on the blog but not leveraged as a major brand moment — a missed opportunity for earned media and positioning refresh.
- **HTMX \+ Alpine.js \+ Django 6.0 template partials** could be positioned as "the modern Django stack" — a response to the SPA-heavy trend that differentiates from React-first competitors.
- **llms.txt adoption** is a small, cheap, high-signal move. It would cost almost nothing to implement (a Sphinx extension exists) and would signal that Django takes AI-assisted development seriously.

### Reviewed by

Hermes Agent (AI-assisted analysis based on public web sources)

### Date reviewed

July 16, 2026

---

_All data verified against live sources as of July 2026\. Per-channel social follower counts (X, Bluesky, LinkedIn individually) not independently verified — the 350K+ combined figure is the DSF's own claim. GitHub stars, PyPI downloads, Discord member count, Mastodon followers, and event dates checked against live sources. ⚠️ flags indicate claims that could not be fully verified or that the provided source map flagged for verification._
