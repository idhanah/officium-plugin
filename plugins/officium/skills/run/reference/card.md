# The report card

The card is a JSON object the site shows above the report and in its lists. Send it as the `card` argument of `officium_submit_report`. The site checks it and tells you exactly what to fix.

| Field | What goes in it |
|---|---|
| `kind` | `"Company"`, `"Industry"`, `"Earnings review"`, `"Quality screen"` or `"Comparison"` |
| `title` | e.g. `"Nintendo: Investment Research"`, `"ASML: Q3 2026 Results"`, `"European Defence: Industry Map"` |
| `ticker` | e.g. `"7974"`; for an industry a short code such as `"DEFENCE"` |
| `venue` | the exchange, e.g. `"Tokyo Stock Exchange"`; for an industry `"Several"` |
| `date` | research date, `YYYY-MM-DD` |
| `px` | price at research with its currency sign, e.g. `"¥8,950"`, `"$102.71"`, `"€1,396.40"`; for an industry `"n/a"` |
| `blurb` | two sentences: what the company does, and what this report looked at |
| `verdict` | a few words, e.g. `"Hold · buy below ¥7,500"`, `"Avoid"`, `"Favour · up to $120"` |
| `tone` | `"bad"` for Avoid, `"warn"` for Wait or hold, `"good"` for Favour |
| `headline` | one sentence: the conclusion |
| `reasons` | **exactly 3** sentences, the reasons that matter most, each with a number |
| `watch` | 3 to 5 signals that would change the verdict |
| `next` | `{ "text": "Q3 results and the full-year outlook", "until": "2026-11-05" }` (`until` only when the date is known) |
| `bands` | optional, company reports in `$`, `€`, `£` or `₹` only: `{ "cur": "$", "bear": 70, "base": 95, "bull": 130, "price": 102.71, "zone": 85, "zoneLabel": "Clearly attractive below $85", "note": "3-year scenarios discounted to today at 10%" }`. Values are per share, as numbers, with `bear <= base <= bull`. Leave `bands` out for other currencies. |
| `sym` | optional: the Yahoo Finance symbol, e.g. `"7974.T"`, `"ASML.AS"`, `"PNR"` |
| `benchmark` | optional, with `sym`: the sector the share is compared with on the site's scorecard, `{ "sym": "XLK", "name": "US technology", "fund": "Technology Select Sector SPDR" }`: a sector ETF or index with a Yahoo Finance symbol. The site fills in its level on the research day; without it, a broad market index is used. |
| `plan` | optional: `{ "none": "what to do if you do not own it", "holding": "what to do if you do", "add": ["signals to buy more"], "sell": ["signals to sell"] }` |

Example (a made-up company, for the shape only):

```json
{
  "kind": "Company",
  "title": "Example Water Co.: Investment Research",
  "ticker": "EXW",
  "venue": "NYSE",
  "date": "2026-10-11",
  "px": "$52.47",
  "sym": "EXW",
  "blurb": "Pool, water-filtration and pump maker that mostly sells replacements for worn-out equipment. A four-masters review of the business, the moat, the risks and the price.",
  "verdict": "Wait · buy below $45",
  "tone": "warn",
  "headline": "A good replacement business whose moat narrowed in 2026; the price leaves little room for that.",
  "reasons": [
    "Replacement sales are about 80% of revenue at a 25% operating margin, with low capital needs.",
    "Pool dealers moved share to rivals after 2026's price rises, the first real dent in the moat.",
    "At $52.47 the shares trade at 19 times earnings, against a base-case value of $49."
  ],
  "watch": ["Pool share recovering or slipping further", "A new CFO staying put", "Free cash flow above $600m"],
  "next": { "text": "Q4 results and 2027 guidance", "until": "2027-02-03" },
  "bands": { "cur": "$", "bear": 38, "base": 49, "bull": 63, "price": 52.47, "zone": 45, "zoneLabel": "Clearly attractive below $45", "note": "3-year scenarios discounted to today at 10%" }
}
```
