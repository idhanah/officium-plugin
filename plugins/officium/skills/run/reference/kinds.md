# What each kind of report covers

The job's `skill` says which kind the person picked. These are English condensations of the ai-berkshire skills of the same name (github.com/xbtlin/ai-berkshire, MIT licence).

## `/investment-research`: Full company deep dive (also when no kind was picked)
The four-masters report: business (Duan Yongping), moat (Buffett), inversion and risks (Munger), management, industry and the long view (Li Lu), valuation with three scenarios and a buy-below price, verdict. Chapters as in [report.md](report.md). Card `kind`: `"Company"`.

## `/investment-checklist`: Buffett checklist, quicker
Six gates, each **Pass** or **Fail** with a short reason: (1) can I understand the business; (2) is it a good business: return on equity, margins, free cash flow, debt; (3) is the moat deep enough; (4) can management be trusted; (5) is the price low enough, with a rough value range per share; (6) position and discipline: would I hold it if the market closed for ten years?
Then the **quick veto list**, marking any that apply: cannot say how it makes money; free cash flow negative three years running with no improvement; management integrity problems; the advantage is being worn away for good; it only works if someone later pays more; could not bear it going to zero; the reason to buy is "everyone is buying" or "it went up lately"; the case cannot be written in 200 words.
Several companies: end with a comparison table. Card `kind`: `"Company"` (one) or `"Comparison"` (several).

## `/quality-screen`: Quick quality screen of a few companies
Seven tests, with numbers and sources for each company. Exclude a company that fails one:
1. 10-year average return on equity below 8%
2. Free cash flow added up over 5 years is negative
3. Interest cover (operating profit ÷ interest) below 2
4. Long-run gross margin below 15%
5. Operating cash flow ÷ net profit, 5-year average, below 0.7
6. Long-run net margin below 5%
7. Shares outstanding up more than 20% in 5 years, not from acquisitions
Exemptions: (A) test 1 waived if listed under 10 years, gross margin above 30% and operating cash flow positive for 2 years; (B) test 6 waived if gross margin above 30% and net margin back above 5% or clearly rising; (C) tests 4 and 6 waived if return on equity above 20%, operating cash flow ÷ net profit above 1.0, and a membership, platform or high-volume thin-margin model.
A table (company × test) and **Keep** or **Exclude** for each. Card `kind`: `"Quality screen"`; `ticker` lists the tickers, e.g. `"PNR · XYL"`.

## `/earnings-review`: Latest earnings results
From first-hand sources (results release, quarterly or annual report, call transcript): headline numbers against last year and against expectations; segments; guidance changes, with management's words quoted and sourced; red flags (one-offs, accounting changes, receivables or inventory rising faster than sales); did the long-term case change; verdict. Card `kind`: `"Earnings review"`, `title` like `"ASML: Q3 2026 Results"`.

## `/industry-research`: Map of a whole industry
The investment case as a chain of cause and effect, each link checked, with events that already prove or disprove it; the value chain from raw materials to customers and where profits pool; main companies per segment with share, growth and margins; drivers and what could break it; the 3 to 5 companies most worth a deeper look. Card `kind`: `"Industry"`, no `bands`.

## `/industry-funnel`: Best 3 companies in an industry
All listed companies in the industry across the big markets → five hard tests (5-year average return on equity above 15%; free cash flow positive in most of the last 5 years; net debt below 3 years of operating profit; gross margin above the industry median; shares not up more than 20% in 5 years) → 10 or fewer, showing who failed what → moat, management and growth → the final 3, each with bear, base and bull value per share and a verdict. Card `kind`: `"Industry"`; the card's verdict names the three.

## `/news-pulse`: Why a share moved today
The move (size, days) against its index and sector over the same days; everything that could explain it (company news and filings, results, analyst changes, sector and competitor news, economic news, rumours), each dated and sourced; explanations ranked by the strength of evidence; whether the move fits the long-term value or looks like an overreaction; what to watch. Card `kind`: `"Company"`.
