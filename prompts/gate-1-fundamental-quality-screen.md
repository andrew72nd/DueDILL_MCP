# Gate 1 Prompt: Fundamental Quality Screen

Use this prompt after replacing `{COMPANY_TICKER}` with the company name or ticker.

```text
[Use the Core Principles for Every Gate]

Company: {COMPANY_TICKER}
Date: {DATE}

Perform a fundamental quality screen on the last 3 fiscal years. The goal is to decide whether this company deserves to continue to Gate 2.

Analyze:
1. Revenue growth: calculate 3-year CAGR and year-over-year growth. Is revenue actually growing?
2. Free cash flow: use free cash flow, not EBITDA. Has FCF been consistently positive?
3. Net cash: calculate cash and equivalents minus total debt. Does the company have more cash than debt?

Rules:
- Use only reputable sources: SEC filings (10-K, 10-Q), Bloomberg, Reuters, Morningstar, FactSet, or official investor relations pages. Cite the source name and date for every key number.
- Do not invent missing data. If a data point cannot be found or verified, write `Data not found` or `Unverified` and explain what source is needed.
- The company needs at least 2 out of 3 checks to pass.
- Be skeptical of accounting quirks, one-time items, acquisitions, cyclicality, stock-based compensation, customer concentration, and weak cash conversion.
- Include current market regime context and identify what the market may be misunderstanding.

Return this Markdown structure exactly:

# Gate 1: Fundamental Quality Screen — {COMPANY_TICKER}

## Key Metrics
| Metric | FY−2 | FY−1 | FY Latest | 3-Year Trend | Assessment |
|---|---:|---:|---:|---|---|
| Revenue ($M) | | | | | |
| Revenue Growth YoY | | | | | |
| Free Cash Flow ($M) | | | | | |
| FCF Margin | | | | | |
| Net Cash / (Debt) ($M) | | | | | |

## Gate Checks
| Check | Pass/Fail | Evidence | Source |
|---|---|---|---|
| Revenue Actually Growing | | | |
| Free Cash Flow Positive | | | |
| More Cash Than Debt | | | |

## Analysis
Narrative interpretation of the metrics, accounting quality concerns, cyclicality, and regime context.

## Rating
Rating: X/100
Gate Result: PASS or FAIL
Gate Verdict: One sentence investment-committee-style conclusion.

## Risks, Conservatism, and Edge
- Bear case:
- Accounting quality concerns:
- Data quality concerns:
- Market misunderstanding:
- Possible edge:

## Final Report Input
Gate: 1
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
