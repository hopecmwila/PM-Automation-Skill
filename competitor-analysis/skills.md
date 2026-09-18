# Competitor Analysis Skill

## Purpose
Map a product, feature, or company against the real competitive landscape - combining whatever the user already knows with fresh web research - so no relevant competitor, gap, or claim goes unchecked. Produces one of several standard outputs (full report, battlecard, messaging comparison, content gap analysis, positioning map) depending on what the user needs.

## Required Inputs
1. **Subject**: the product/feature/company being analyzed - what it does, target users, goals
2. **Capability list**: what the subject actually does (features, positioning claims). Only use what's provided or verifiably sourced - never invent capabilities.
3. **Known competitors**, if any
4. **Scope constraints**: market, region, segment, and which output is wanted (full report / battlecard / messaging matrix / content gap / positioning map), if any

If the subject or capability list is missing or ambiguous, ask clarifying questions before researching. Known competitors and scope are helpful but not blocking - proceed with sensible defaults (broad market scope, full report) and state the assumption if the user doesn't specify.

## Core Rules
- **Never limit research to competitors the user names.** Always web-search for additional direct, indirect, and emerging competitors - job postings, funding news, and alternatives to X searches are good signals for players the user may not know about.
- **Every competitor claim must trace to a source (URL).** Mark anything you can't verify as *unverified* rather than stating it as fact.
- **Don't invent subject-side features.** Only describe the user's product/company using what was actually provided or what you verified independently - flag anything inferred.
- **No unsupported superlatives** (best, leading, only) without a citation backing the claim.
- **Keep table stakes and differentiators separate.** Table stakes = capabilities most/all competitors share. Differentiators = what the subject has beyond table stakes. Don't let one leak into the other.
- **Date-stamp everything.** Competitive intelligence has a short shelf life - note the research date and flag anything time-sensitive (pricing, recent announcements).
- **Be honest about competitor strengths.** A battlecard or SWOT that only lists weaknesses of competitors isn't credible and will backfire with sales/product teams.

## Research Sources
Pull from primary and secondary sources as relevant to the scope; web-search across these categories rather than relying on a single site.

**Primary (direct from competitor)**: website (homepage, product/pricing/about/careers pages), blog and resource center, social media profiles, product demos/free trials, webinars and events, press releases/newsroom, job postings (hiring signals reveal strategic priorities - e.g., hiring for a new product line or market).

**Secondary (third-party)**: review sites (G2, Capterra, TrustRadius, Product Hunt) for customer sentiment; analyst reports (Gartner, Forrester, IDC) for category placement; news coverage (TechCrunch, industry press) for funding/partnerships/narrative; SEO tools or search for keyword and content gaps; financial filings for public companies; community forums (Reddit, Discourse, industry Slack/Discord) for unfiltered user sentiment.

## Workflow

1. **Scope**: confirm subject, users, goals, known competitors, and which output format is wanted (see Output Formats below).
2. **Research**: web-search for existing solutions - direct, indirect, and emerging/adjacent. For each competitor, capture: offering, target customer, pricing model, strengths, weaknesses/gaps, and source URLs. Don't stop at the user's named list - actively search for others (for example, category alternatives, competitor vs, and category market map).
3. **Table Stakes**: list capabilities common across most/all competitors.
4. **Differentiators**: list what sets the subject apart from table stakes, and why each matters to the customer.
5. **Feature Matrix**: table mapping core features across the subject and each competitor (Yes/No/Partial), to pinpoint what actually matters.
6. **Positioning & Messaging** (when relevant to the requested output): reverse-engineer each competitor's positioning statement, narrative (villain/hero/transformation/stakes), and messaging strengths/vulnerabilities (clarity, differentiation, proof, consistency, resonance). Plot on a positioning map if a 2x2 comparison would clarify the landscape.
7. **SWOT**: Strengths/Weaknesses/Opportunities/Threats for the subject given the landscape just mapped.
8. **Compile** into the requested Output Format, with a full source list and research date.

## Output Formats

Default to the **Full Report** unless the user asks for something narrower (a battlecard for sales enablement, a messaging comparison, a content gap analysis, or just a positioning map). All formats share the same sourcing and table-stakes/differentiator rules above.

### Full Report (default)
```
# Competitor Analysis: [Subject]
_Research date: [date]_

## Subject
[Full capability list, as provided/verified]

## Existing Solutions
### [Competitor] - [source]
- Offering:
- Target customer / pricing model:
- Strengths:
- Limitations/Gaps:
(repeat per competitor, known + researched)

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

## What to Avoid
- Skipping web research and relying only on user-named competitors.
- Presenting unverified claims as fact - flag them instead.
- Missing a source for any competitor data point.
- Mixing table stakes into differentiators, or vice versa.
- Listing subject-side features that weren't actually provided or verified.
- One-sided battlecards that omit genuine competitor strengths.
- Omitting the research date - competitive intel goes stale fast.

## Maintenance Note (for recurring/ongoing use)
If the user wants this tracked over time rather than as a one-off: deep analysis quarterly, lighter monitoring (new announcements, content, messaging changes) monthly, and battlecards updated immediately after major competitor announcements or new win/loss feedback.

## Example Trigger
User: shares product brief plus a couple of known competitors and asks for a competitive analysis.
You: Confirm scope if needed → research known + newly discovered competitors with sources → produce the Full Report (or the specific format requested) with table stakes, differentiators, feature matrix, SWOT, and a full source list, flagging anything unverified.