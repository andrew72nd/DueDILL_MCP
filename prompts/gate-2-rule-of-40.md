# Gate 2 Prompt: The Rule of 40

Use this prompt after replacing `{COMPANY_TICKER}` with the company name or ticker.

```text
[Use the Core Principles for Every Gate]

Company: {COMPANY_TICKER}
Date: {DATE}

Calculate the Rule of 40 using conservative inputs:

Rule of 40 = Revenue Growth Rate + Free Cash Flow Margin

Use 3-year revenue CAGR as the primary growth rate unless the most recent year is materially weaker, in which case explain both numbers and use the lower conservative figure for the final score. Use free cash flow margin, not adjusted EBITDA margin.

Rules:
- Use only reputable sources: SEC filings (10-K, 10-Q), Bloomberg, Reuters, Morningstar, FactSet, or official investor relations pages. Cite the source name and date for every key number.
- Do not invent missing data. If a data point cannot be found or verified, write `Data not found` or `Unverified` and explain what source is needed. If the Rule of 40 cannot be calculated honestly, say so instead of forcing a score.

Analyze:
1. Revenue growth rate and trend (3-year CAGR and latest year growth).
2. Free cash flow margin and trend (show each year).
3. Final Rule of 40 score: conservative vs. reported basis.
4. Peer comparison against direct software/sector peers and elite benchmark (>60 is world class).
5. Whether the score is durable or temporarily inflated by one-off items, rate tailwinds, or pricing power that may not persist.

Stress-test for mean reversion, AI-cycle enthusiasm, rates, customer concentration, pricing pressure, regulation, margin normalization, and stock-based compensation dilution.

Return this Markdown structure exactly:

# Gate 2: Rule of 40 — {COMPANY_TICKER}

## Rule of 40 Calculation
| Input | Conservative Value | Reported Basis | Source / Notes |
|---|---:|---:|---|
| Revenue Growth Rate (3Y CAGR) | | | |
| Revenue Growth Rate (Latest YoY) | | | |
| Free Cash Flow Margin | | | |
| Rule of 40 Score (Conservative) | | | |

## Trend Analysis
| Year | Revenue Growth | FCF Margin | Rule of 40 |
|---|---:|---:|---:|

## Peer Context
| Company | Revenue Growth | FCF Margin | Rule of 40 | Notes |
|---|---:|---:|---:|---|

## Analysis
Narrative interpretation: is the score sustainable? What are the main drivers and risks?

## Rating
Rating: X/100
Gate Result: PASS or FAIL
Gate Verdict: One sentence investment-committee-style conclusion.

## Risks, Conservatism, and Edge
- Bear case:
- Mean reversion risk:
- Dilution or SBC risk:
- Market misunderstanding:
- Possible edge:

## Final Report Input
Gate: 2
Rating: X/100
Result: PASS or FAIL
Key evidence:
-
-
Main risks:
-
Market misunderstanding:
-
Possible edge:
-
Unverified or missing data:
-

## References
-
```
