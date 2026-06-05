# Gate 3 Prompt: The Moat Test

Use this prompt after replacing `{COMPANY_TICKER}` with the company name or ticker.

```text
[Use the Core Principles for Every Gate]

Company: {COMPANY_TICKER}
Date: {DATE}

Apply the Chinese reverse-engineering test:

If a well-funded Chinese company threw 20 engineers at every one of this company's engineers and tried to reverse engineer the business, could they do it in one year?

Grade the company's moat using six categories. Score each category from 0 to 10 and provide evidence. Use operating margin and gross margin as financial fingerprints, but do not let high margins alone prove a moat.

Rules:
- Use only reputable sources: SEC filings, earnings call transcripts, Bloomberg, Reuters, Morningstar, FactSet, official investor relations pages, or verified analyst reports. Cite the source name and date for every claim.
- Do not invent missing data, competitor evidence, margin figures, market share figures, customer metrics, or citations. If evidence cannot be found or verified, write `Data not found` or `Unverified` and lower confidence accordingly.

Moat categories:
1. Brand: trusted identity that commands pricing power.
2. Network effects: value increases as more users join.
3. Data moat: proprietary data competitors cannot easily replicate.
4. Switching costs: painful or expensive for customers to leave.
5. Cost advantages: structural ability to produce cheaper than rivals.
6. Regulatory moat: patents, licenses, approvals, or legal barriers.

Stress-test moat durability against technology change, open-source alternatives, platform shifts, regulation, customer bargaining power, and competitor capital intensity.

Return this Markdown structure exactly:

# Gate 3: Moat Analysis — {COMPANY_TICKER}

## Reverse-Engineering Test
Answer: YES or NO — could a well-funded competitor replicate this in one year?
Rationale:

## Moat Breakdown
| Moat Type | Strength 0–10 | Evidence | Source | Durability Risk |
|---|---:|---|---|---|
| Brand | | | | |
| Network Effects | | | | |
| Data Moat | | | | |
| Switching Costs | | | | |
| Cost Advantages | | | | |
| Regulatory Moat | | | | |

Total Moat Score: X/60
Moat Category: Wide / Narrow / None

## Financial Fingerprints
| Metric | Latest Year | 3-Year Trend | Peer Average | Assessment |
|---|---:|---|---|---|
| Gross Margin | | | | |
| Operating Margin | | | | |
| Revenue per Employee ($K) | | | | |
| Churn / Retention (if available) | | | | |

## Analysis
Narrative interpretation of moat quality, durability, and key threats.

## Rating
Rating: X/100
Gate Result: PASS or FAIL
Gate Verdict: One sentence investment-committee-style conclusion.

## Risks, Conservatism, and Edge
- Moat erosion risk:
- Operating margin evidence:
- Technological disruption risk:
- Market misunderstanding:
- Possible edge:

## Final Report Input
Gate: 3
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
