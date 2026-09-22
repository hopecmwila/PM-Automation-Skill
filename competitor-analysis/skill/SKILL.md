---
name: competitor-analysis
description: Map a product, feature, or company against its real competitive landscape by combining what the user already knows with fresh web research, then produce a full report, battlecard, messaging comparison, content gap analysis, or positioning map. Use whenever the user asks to research competitors, benchmark against rivals, build a sales battlecard, compare positioning/messaging, find content or feature gaps, or wants a "competitive analysis" or "market landscape" - even if they only name one or two competitors, since this skill is what finds the rest.
---

# Competitor Analysis Skill

## Purpose
Map a product, feature, or company against the real competitive landscape - combining whatever the user already knows with fresh web research - so no relevant competitor, gap, or claim goes unchecked. Produces one of several standard outputs (full report, battlecard, messaging comparison, content gap analysis, positioning map) depending on what the user needs.

## Credits — Concepts Borrowed From Other Skills
This skill was benchmarked against three publicly available competitor-analysis skills, and the following concepts were deliberately borrowed from them. Everything else in this document is original to this skill.

- **[competitor-analysis-claude](https://github.com/0-shiv/secondstep-claude-skills/blob/main/skills/competitor-analysis-claude/SKILL.md)** by Shivendra Rawat (0-shiv) — borrowed the **`[Confirmed] / [Estimated] / [Inferred]` confidence-tag system** for data points (this skill previously only had a binary verified/unverified flag), the explicit **Ethical Boundaries** rule (public sources only, never social engineering or unauthorized access), and the **Context Awareness** checklist (company stage, geographic scope, market dynamics, decision the analysis informs).
- **[Competitors Analysis](https://mcpmarket.com/tools/skills/competitor-analysis)** by daymade ([source repo](https://github.com/daymade/claude-code-skills)) — borrowed the **Forbidden / Required language patterns table** (banning words like "presumably," "likely," "undisclosed" in favor of cited, falsifiable statements) and the **paired Wrong / Right "Common Mistakes" format**, which is more instructive than a plain bullet list of things to avoid. Also reinforced the inline **`claim (Source: URL, accessed date)`** citation style used throughout this skill's outputs.
- **[Competitive Intelligence - The Claude Way](https://chrislema.com/competitive-intelligence-the-claude-way)** by Chris Lema — borrowed the **dated-snapshot filename convention** (`[subject-slug]-competitor-analysis-[YYYY-MM-DD].md`, since a competitive analysis is a point-in-time snapshot, not a permanent truth), the **"Not found" discipline** (write "Not found" for a missing data point instead of silently dropping the section or inventing a value), and the idea of a **companion trend-tracking mode** for diffing multiple dated snapshots of the same subject over time (see Maintenance Note).

## Required Inputs
1. **Subject**: the product/feature/company being analyzed - what it does, target users, goals
2. **Capability list**: what the subject actually does (features, positioning claims). Only use what's provided or verifiably sourced - never invent capabilities.
3. **Known competitors**, if any
4. **Scope constraints**: market, region, segment, and which output is wanted (full report / battlecard / messaging matrix / content gap / positioning map), if any

If the subject or capability list is missing or ambiguous, ask clarifying questions before researching. Known competitors and scope are helpful but not blocking - proceed with sensible defaults (broad market scope, full report) and state the assumption if the user doesn't specify.

## Core Rules
- **Never limit research to competitors the user names.** Always web-search for additional direct, indirect, and emerging competitors - job postings, funding news, and alternatives to X searches are good signals for players the user may not know about.
- **Every competitor claim must trace to a source (URL), cited inline as `claim (Source: URL, accessed [date])`.** Mark anything you can't verify as *unverified* rather than stating it as fact.
- **Tag every data point with a confidence level: `[Confirmed]`, `[Estimated]`, or `[Inferred]`.** *(Borrowed from [competitor-analysis-claude](https://github.com/0-shiv/secondstep-claude-skills/blob/main/skills/competitor-analysis-claude/SKILL.md).)* `[Confirmed]` = stated directly by a primary source. `[Estimated]` = a reasonable numeric/qualitative approximation from secondary sources (e.g. review-site sentiment, analyst commentary). `[Inferred]` = a judgment call you made from indirect evidence (e.g. a job posting implies a new product line). Never present an `[Estimated]` or `[Inferred]` point with the confidence of a `[Confirmed]` one.
- **If a dimension has no data, write "Not found" rather than omitting the section or inventing a value.** *(Borrowed from [Chris Lema's evaluate-company skill](https://chrislema.com/competitive-intelligence-the-claude-way).)* A missing section reads as an oversight; "Not found" reads as a checked box.
- **Don't invent subject-side features.** Only describe the user's product/company using what was actually provided or what you verified independently - flag anything inferred.
- **No unsupported superlatives** (best, leading, only) without a citation backing the claim.
- **Keep table stakes and differentiators separate.** Table stakes = capabilities most/all competitors share. Differentiators = what the subject has beyond table stakes. Don't let one leak into the other.
- **Date-stamp everything.** Competitive intelligence has a short shelf life - note the research date and flag anything time-sensitive (pricing, recent announcements).
- **Be honest about competitor strengths.** A battlecard or SWOT that only lists weaknesses of competitors isn't credible and will backfire with sales/product teams.
- **Ethical boundaries.** *(Borrowed from [competitor-analysis-claude](https://github.com/0-shiv/secondstep-claude-skills/blob/main/skills/competitor-analysis-claude/SKILL.md).)* Use only publicly available information. Never suggest or perform social engineering, credential stuffing, scraping behind a login wall, or any other form of unauthorized access to get competitor data.

## Context Awareness
*(Borrowed and merged from [competitor-analysis-claude](https://github.com/0-shiv/secondstep-claude-skills/blob/main/skills/competitor-analysis-claude/SKILL.md)'s Context Awareness checklist.)* Before researching, and while writing up findings, keep these in view - they change what "good" looks like:
- **Company/subject stage**: startup vs. growth vs. enterprise changes which competitors and which metrics matter.
- **Geographic scope**: local, national, or international competition.
- **Market dynamics**: growing, mature, or declining market changes how much weight to put on new entrants vs. incumbents.
- **The decision this analysis informs**: pricing change, sales enablement, product roadmap, messaging refresh, fundraising - tailor emphasis accordingly.
- **Data freshness**: how old is each source, and does it still apply?

## Research Sources
Pull from primary and secondary sources as relevant to the scope; web-search across these categories rather than relying on a single site.

**Primary (direct from competitor)**: website (homepage, product/pricing/about/careers pages), blog and resource center, social media profiles, product demos/free trials, webinars and events, press releases/newsroom, job postings (hiring signals reveal strategic priorities - e.g., hiring for a new product line or market).

**Secondary (third-party)**: review sites (G2, Capterra, TrustRadius, Product Hunt) for customer sentiment; analyst reports (Gartner, Forrester, IDC) for category placement; news coverage (TechCrunch, industry press) for funding/partnerships/narrative; SEO tools or search for keyword and content gaps; financial filings for public companies; community forums (Reddit, Discourse, industry Slack/Discord) for unfiltered user sentiment.

## Language Discipline
*(Borrowed from [daymade's Competitors Analysis skill](https://mcpmarket.com/tools/skills/competitor-analysis), adapted from a code-citation table to a source-citation table.)* Every sentence in the output should be either a cited fact, a clearly-tagged estimate/inference, or an explicit gap. Use this table to self-check before finalizing:

| Forbidden | Why |
|---|---|
| "presumably," "likely," "probably," "should have" | No evidence behind it - either find the source or tag it `[Estimated]`/`[Inferred]` and say why |
| "undisclosed," "not publicly available" used to justify a guess | If you don't know, write "Not found" - don't fill the gap with a guess |
| An unsourced number in a comparison table | Every cell with a figure needs a citation, even if the subject's own number is well known to the user |
| "best," "leading," "only" with no citation | Unsupported superlative - see Core Rules |

| Required | Example |
|---|---|
| Claim + inline source | "Raised a $40M Series B in March 2026 (Source: techcrunch.com/..., accessed 2026-09-22)" |
| Confidence tag on estimates | "Roughly 200-300 employees `[Estimated]` (Source: linkedin.com/company/..., accessed 2026-09-22)" |
| "Not found" for real gaps | "Enterprise pricing: Not found (not listed publicly; requires sales contact)" |

## Workflow

1. **Scope**: confirm subject, users, goals, known competitors, and which output format is wanted (see Output Formats below). Apply the Context Awareness checklist above.
2. **Research**: web-search for existing solutions - direct, indirect, and emerging/adjacent. For each competitor, capture: offering, target customer, pricing model, strengths, weaknesses/gaps, and source URLs with confidence tags. Don't stop at the user's named list - actively search for others (for example, category alternatives, competitor vs, and category market map).
3. **Table Stakes**: list capabilities common across most/all competitors.
4. **Differentiators**: list what sets the subject apart from table stakes, and why each matters to the customer.
5. **Feature Matrix**: table mapping core features across the subject and each competitor (Yes/No/Partial), to pinpoint what actually matters.
6. **Positioning & Messaging** (when relevant to the requested output): reverse-engineer each competitor's positioning statement, narrative (villain/hero/transformation/stakes), and messaging strengths/vulnerabilities (clarity, differentiation, proof, consistency, resonance). Plot on a positioning map if a 2x2 comparison would clarify the landscape.
7. **SWOT**: Strengths/Weaknesses/Opportunities/Threats for the subject given the landscape just mapped.
8. **Compile** into the requested Output Format, with a full source list and research date. Save/name the output using the dated-snapshot convention: `[subject-slug]-competitor-analysis-[YYYY-MM-DD].md` — this is a point-in-time snapshot, not a permanent truth, and the date in the filename makes future trend-tracking possible (see Maintenance Note).

## Output Formats

Default to the **Full Report** unless the user asks for something narrower (a battlecard for sales enablement, a messaging comparison, a content gap analysis, or just a positioning map). All formats share the same sourcing, confidence-tagging, and table-stakes/differentiator rules above.

### Full Report (default)
```
# Competitor Analysis: [Subject]
_Research date: [date]_

## Subject
[Full capability list, as provided/verified]

## Existing Solutions
### [Competitor] - [source]
- Offering: [claim] `[Confirmed/Estimated/Inferred]`
- Target customer / pricing model:
- Strengths:
- Limitations/Gaps:
(repeat per competitor, known + researched; use "Not found" for missing data points)

## Table Stakes
- [feature]

## Differentiators
- [feature]: why it matters (+ proof/source if applicable)

## Feature Matrix
| Feature | Subject | Competitor A | Competitor B |
|---|---|---|---|

## SWOT
- Strengths:
- Weaknesses:
- Opportunities:
- Threats:

## Data Confidence Notes
[Short summary of what's Confirmed vs. Estimated vs. Inferred, and what's stale or time-sensitive]

## Sources
[All URLs used, with access date]
```

### Battlecard (per competitor - for sales/marketing enablement)
```
# Battlecard: [Competitor]
_Last updated: [date] | Win rate: [if tracked]_

## Quick Overview
- What they do (one sentence):
- Target customer:
- Pricing model:
- Recent developments:

## Their Pitch
- Self-description / tagline:
- Top claimed differentiators:

## Strengths (be honest)
- [from reviews/market presence]

## Weaknesses
- [from reviews - recurring complaints, gaps, limitations]

## Our Differentiators
- [differentiator]: why it matters + proof

## Objection Handling
| If the prospect says... | Respond with... |
|---|---|

## Landmines to Set
- Questions that surface areas where they're weak

## Win/Loss Themes
- Why we typically win / lose against them
```

### Messaging Comparison
Use the Messaging Matrix (tagline, core value prop, primary audience, key differentiator claim, tone/voice, proof points, category framing, primary CTA - subject vs. each competitor) plus a short Narrative Analysis (villain/hero/transformation/stakes) and a Strengths/Vulnerabilities assessment (clarity, differentiation, proof, consistency, resonance) per competitor.

### Content Gap Analysis
Use a Content Audit Comparison table (topic/theme x subject/competitors, noting gaps) and a Content Type Coverage table (format x subject/competitors). Close with numbered opportunities: topics competitors cover that the subject doesn't, topics the subject covers that they don't, format gaps, underserved audience segments, and SEO/search-term gaps.

### Positioning Map
Reverse-engineer a positioning statement per player, then plot on a 2x2 using the axis pair most relevant to the market (for example, Price vs. Capability, Ease of Use vs. Power, SMB vs. Enterprise Focus, Point Solution vs. Platform, Innovative vs. Established). Call out which quadrant is underserved.

## Positioning Pitfalls to Flag
When advising on the subject's own positioning (not just describing competitors), watch for and call out: positioning against a competitor rather than for a customer need, claiming too many differentiators (more than 1-2 that matter most), category jargon the customer doesn't use, positioning on features rather than outcomes, and positioning that has changed too frequently to build market recognition.

## Common Mistakes to Avoid
*(Format borrowed from [daymade's Competitors Analysis skill](https://mcpmarket.com/tools/skills/competitor-analysis).)*

**1. Presenting an estimate as a fact**
- Wrong: "Acme has 500 employees."
- Right: "Roughly 400-500 employees `[Estimated]` (Source: linkedin.com/company/acme, accessed 2026-09-22)."

**2. Dropping a section because you found nothing**
- Wrong: [Pricing section simply missing from the report]
- Right: "Pricing: Not found (no public pricing page as of 2026-09-22; product is enterprise sales-led)."

**3. An unsourced comparison table**
- Wrong: `| Languages supported | 25 | 58 |`
- Right: `| Languages supported | 25 (Source: acme.com/features, accessed 2026-09-22) | 58 (internal roadmap doc) |`

**4. Mixing table stakes into differentiators**
- Wrong: listing "has a mobile app" as a differentiator when every competitor also has one.
- Right: mobile app goes in Table Stakes; the differentiator is the specific capability the mobile app has that others don't.

**5. A one-sided battlecard**
- Wrong: a battlecard that lists ten competitor weaknesses and zero strengths.
- Right: at least one honest, sourced strength per competitor, even if it's just "faster onboarding, per G2 reviews."

**6. Skipping web research and relying only on user-named competitors.**
**7. Omitting the research date or the dated-snapshot filename** - competitive intel goes stale fast, and without a date, no future trend comparison is possible.

## Maintenance Note (for recurring/ongoing use)
If the user wants this tracked over time rather than as a one-off: deep analysis quarterly, lighter monitoring (new announcements, content, messaging changes) monthly, and battlecards updated immediately after major competitor announcements or new win/loss feedback.

**Trend tracking.** *(Concept borrowed from the companion "trend-company" skill described in [Competitive Intelligence - The Claude Way](https://chrislema.com/competitive-intelligence-the-claude-way).)* Because each report is saved with a dated filename (`[subject-slug]-competitor-analysis-[YYYY-MM-DD].md`), a later request like "how has Acme changed since our last analysis" can be answered by diffing the current findings against the most recent prior snapshot for the same subject - call out what's new, what's changed, and what's now stale, rather than re-researching from zero.

## Example Trigger
User: shares product brief plus a couple of known competitors and asks for a competitive analysis.
You: Confirm scope if needed → research known + newly discovered competitors with sources → produce the Full Report (or the specific format requested) with table stakes, differentiators, feature matrix, SWOT, data confidence notes, and a full source list, flagging anything unverified or "Not found."