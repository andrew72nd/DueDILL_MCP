# Gate 5 Prompt: Valuation

Use this prompt after replacing `{COMPANY_TICKER}` with the company name or ticker.

```text
[Use the Core Principles for Every Gate]

Company: {COMPANY_TICKER}
Date: {DATE}

Build a conservative valuation. Valuation is a tool, not an answer. The rule that cannot be broken: the bear case must still be attractive. Do not build a valuation to justify a pre-formed conclusion.

Rules:
- Use only reputable sources: SEC filings (10-K, 10-Q), Bloomberg, Reuters, FactSet, Morningstar, S&P Capital IQ, or official investor relations. Cite the source name and date for every key number and multiple used.
- Do not invent missing data, valuation inputs, market prices, peer multiples, DCF assumptions, or citations. If a required input cannot be found or verified, write `Data not found` or `Unverified`. If the valuation cannot be completed honestly, provide the partial analysis and list the missing inputs.

Analyze:
1. Current valuation: market cap, enterprise value, and key multiples (EV/Revenue, EV/FCF, P/E, EV/EBIT).
2. Historical multiple context: how do current multiples compare to this company's own 3-year and 5-year history?
3. Conservative DCF with bear, base, and bull cases using free cash flow.
4. Multiples comparison against direct sector peers and the S&P 500 median.
5. Sensitivity analysis: revenue growth rate, FCF margins, WACC, terminal growth rate, and dilution impact.
6. The story the market is pricing today versus what the company may be becoming.

DCF constraints:
- Terminal growth should usually be below 2%.
- WACC should not be aggressively low. Justify every assumption.
- Bear case must include slower growth, lower margins, dilution, multiple compression, and macro stress.

Return this Markdown structure exactly:

# Gate 5: Valuation — {COMPANY_TICKER}

## Current Valuation Snapshot
| Metric | Value | Historical Average (3Y) | Peer Median | Source / Date |
|---|---:|---:|---:|---|
| Market Cap ($B) | | | | |
| Enterprise Value ($B) | | | | |
| EV / Revenue | | | | |
| EV / FCF | | | | |
| P/E (GAAP) | | | | |
| P/E (Non-GAAP) | | | | |
| EV / EBIT | | | | |
| Free Cash Flow Yield | | | | |

## DCF Scenario Analysis
| Case | Revenue CAGR | FCF Margin | WACC | Terminal Growth | Implied Value / Share | Upside / (Downside) |
|---|---:|---:|---:|---:|---:|---:|
| Bear | | | | | | |
| Base | | | | | | |
| Bull | | | | | | |

## Peer Multiples Comparison
| Company | EV/Revenue | EV/FCF | Rule of 40 | Notes |
|---|---:|---:|---:|---|

## Sensitivity Table (Implied Value / Share)
Revenue CAGR vs. FCF Margin — show a grid of implied values across key assumptions.

## Analysis
Narrative: what story is the market pricing? What is the margin of safety in the bear case? Is the current price attractive, fair, or demanding?

## Rating
Rating: X/100
Gate Result: PASS or FAIL
Gate Verdict: One sentence investment-committee-style conclusion.

## Risks, Conservatism, and Edge
- Margin of safety:
- Sensitivity risks:
- Dilution risk:
- Market story priced today:
- Possible edge:

## Final Report Input
Gate: 5
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
