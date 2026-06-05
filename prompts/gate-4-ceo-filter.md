# Gate 4 Prompt: The CEO Filter

Use this prompt after replacing `{COMPANY_TICKER}`.

```text
[Use the Core Principles for Every Gate]

Company: {COMPANY_TICKER}
Date: {DATE}

Identify the current CEO of {COMPANY_TICKER} using verifiable recent sources. State the CEO name found, cite the source and date, and mark it `Unverified` if you cannot confirm who the current CEO is.

Evaluate whether the CEO is strong enough for a long-term high-conviction investment. Assess leadership quality, capital allocation discipline, and governance integrity.

Rules:
- Use only reputable sources: SEC filings (DEF 14A proxy statements, 10-K), Bloomberg, Reuters, company investor relations, verified news, official earnings call transcripts. Cite the source name and date for every claim.
- Do not invent missing data, ownership figures, insider purchases, biography details, governance claims, quotes, or citations. If evidence cannot be found or verified, write `Data not found` or `Unverified` and lower confidence accordingly.

Analyze:
1. Track record: what have they built, fixed, scaled, or destroyed? Reference specific outcomes with dates.
2. Skin in the game: real share ownership (not options), open-market purchases, founder ownership, and incentive structure. Use the most recent DEF 14A proxy.
3. Tenure and commitment: founder, operator-owner, or hired manager. Founder or 10+ years preferred.
4. Delivery vs. promises: compare stated investor-day targets, guidance, capital allocation, and product roadmaps against actual outcomes over the last 3 years.
5. Team quality: whether the CEO attracts, retains, and promotes exceptional operators. Look at key management tenure.
6. Capital allocation: buyback discipline, M&A record, R&D efficiency, and dividend policy.

Stress-test succession risk, key-person risk, promotional behavior, governance, compensation alignment, related-party issues, culture decay, and execution under pressure.

Return this Markdown structure exactly:

# Gate 4: CEO Filter — {COMPANY_TICKER}

## CEO Identification
CEO Name: [Name]
Source: [Source] — [Date]
Tenure: [Start Date]
Founder?: YES / NO

## Leadership Assessment
| Area | Evidence | Source | Assessment |
|---|---|---|---|
| Track Record | | | |
| Skin in the Game | | | |
| Tenure and Commitment | | | |
| Delivery vs. Promises | | | |
| Team Quality | | | |
| Capital Allocation | | | |

## Ownership and Compensation
| Metric | Value | Source / Date |
|---|---:|---|
| CEO Share Ownership (%) | | |
| CEO Open-Market Purchases (last 3Y) | | |
| CEO Total Compensation ($M) | | |
| Pay vs. Peers | | |

## Analysis
Narrative assessment of leadership quality, alignment with shareholders, and key governance concerns.

## Rating
Rating: X/100
Gate Result: PASS or FAIL
Gate Verdict: One sentence investment-committee-style conclusion.

## Risks, Conservatism, and Edge
- Succession risk:
- Governance or alignment risk:
- Compensation concerns:
- Market misunderstanding:
- Possible edge:

## Final Report Input
Gate: 4
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
