# Why `battlecard-linear-vs-asana-bad.md` Fails

Line-by-line against the rules in `SKILL.md`. Compare against
`examples/good/battlecard-linear-vs-asana.md`, which covers the *same real companies* correctly -
every fact in the good version is independently checkable; nothing in the bad version is.

| # | What the bad example does | Rule it breaks | What it should do instead |
|---|---|---|---|
| 1 | "probably priced around $10-25 a user depending on the plan" | **Language Discipline** - "probably" used in place of a citation, when the real prices (Starter $10.99, Advanced $24.99, both annual) are public and were found in under a minute of search | Cite the actual tiers, or if genuinely uncertain, tag the number `[Estimated]` with a source for the estimate - see the good example's Quick Overview. |
| 2 | "the leading work management platform and has the best feature set in the category" | **Core Rules** - unsupported superlative ("leading," "best") with no citation | Either cite a specific ranking (e.g. G2's category leaderboard) or drop the superlative and state the specific, sourced claim - the good example does this with "13,000+ G2 reviews at 4.4/5." |
| 3 | "that's mostly marketing fluff - most teams probably just use it as a glorified to-do list anyway" | **Core Rules** - speculation presented as analysis, not sourced fact; also breaks "be honest about competitor strengths" by editorializing instead of assessing | State what's confirmed about how the product is positioned and used, tagged accordingly, and note honestly if usage-pattern data wasn't found - don't guess at how customers actually use it. |
| 4 | Entire "Weaknesses" list ("Clunky and overcomplicated," "Users are always complaining," "Will probably lose ground") | **Core Rules** - every competitor claim must trace to a source; **Common Mistakes #5** - one-sided battlecard with zero honest strengths | Every weakness needs a source (e.g. a specific, cited review-aggregation theme, as the good example does with the free-tier cap and the Starter-to-Advanced price jump). Include at least one genuine, sourced strength. |
| 5 | Feature Comparison table - no source column, no confidence tags, and "User rating 3.5/5" for Asana directly contradicts the real, sourced figure (4.4-4.5/5 on G2, per the good example) | **Core Rules** - unsourced claims; **Common Mistakes #3** - unsourced comparison table | Every cell with a figure needs `(Source: URL, accessed date)`. This row shows exactly why that matters: an invented number here isn't just unsourced, it's wrong. |
| 6 | No research date anywhere, no dated filename | **Core Rules** - "Date-stamp everything"; **Common Mistakes #7** | Add `_Last updated: [date]_` and save as `[subject]-competitor-analysis-[YYYY-MM-DD].md`, as the good example does. |
| 7 | "Linear is just better for basically any team... not really a good reason to pick Asana" | **Core Rules** - "be honest about competitor strengths"; **Common Mistakes #5** | State win/loss themes honestly, including where the competitor is genuinely the better fit - see the good example's "Loss risk" line about cross-functional programs. |
| 8 | No `[Confirmed]/[Estimated]/[Inferred]` tags anywhere | **Core Rules** - confidence-tag requirement | Tag every data point so the reader knows how much weight to put on it. |
| 9 | No "Data Confidence Notes" section, and nothing flags that both products' pricing changes often | **Output Formats** template requirement; also a real risk here - the good example notes Linear's top tier alone dropped from $50 to $16/user/mo across three restructures | Close with a note on what's solid vs. estimated, and flag anything that's likely to go stale fast. |

## The pattern
Every failure here traces back to the same root cause as in any other bad example: **treating
plausible-sounding language as a substitute for a citation.** The difference this time is that the
correct information was genuinely easy to find - so this version isn't just unsourced, several of
its specific claims (the user rating, "leading... best feature set") are actually wrong once
checked against the real data in the good example. That's the real cost of skipping sourcing: not
just less rigor, but confidently wrong numbers in a document a salesperson might actually use in a
deal.