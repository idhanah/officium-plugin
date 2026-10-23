# Ground rules for every number

These come from the ai-berkshire framework (`skills/financial-data.md` and the research skills) and apply to the lead and to every analyst.

1. **Look everything up.** Never answer from memory. Use web search and read the sources. Write the date you looked.
2. **Two independent sources for each key figure**: share price, shares outstanding, market value, revenue, net profit, free cash flow, cash, debt, and management's shareholding.
   - US shares: macrotrends.net and stockanalysis.com, plus the company's 10-K/10-Q.
   - Europe, Japan, India and elsewhere: the company's annual report or investor site, plus stockanalysis.com, marketscreener.com or Yahoo Finance.
   - Hong Kong and China: the exchange filing or annual report, plus aastocks.com or Yahoo Finance.
   If two sources differ by more than 1%, say so, prefer the company's own filing, and explain the difference (different period, currency, consolidated vs parent, share classes).
3. **Do the arithmetic with a tool, not in your head.** If you can run Python, use the scripts in this skill's `scripts/` folder (standard library only; their help text is partly in Chinese):
   - `python scripts/financial_rigor.py verify-market-cap --price P --shares S --reported M --currency USD`
   - `python scripts/financial_rigor.py cross-validate --field revenue --values '{"source A": 1.0, "source B": 1.01}' --unit USD`
   - `python scripts/financial_rigor.py verify-valuation --price P --eps E --bvps B --fcf-per-share F --dividend D`
   - `python scripts/financial_rigor.py three-scenario --price P --eps E --shares S_in_hundreds_of_millions --growth BULL BASE BEAR --pe BULL BASE BEAR --years 3 --currency USD`
   - `python scripts/terminal_value.py --help` for the ten-year view (perpetual-growth exit multiple; r of 9 to 11.5% for USD, keep g at or below 4%).
   If you cannot run code, write each calculation out step by step.
4. **Watch units and currencies**: millions vs billions, share classes (economic interest vs votes), ADR ratios, and which currency each figure is in.
5. **Rate the information** at the start: **A** plenty (long listed, many analysts: beware just repeating the consensus), **B** some (estimates needed: label each one with how sure you are), **C** little (ask first-principles questions: who pays and why, what drives repeat buying, could a rich competitor copy it, what key decisions has management made).
6. **Facts and estimates stay apart.** Each fact gets its source; each estimate says what it rests on. If something cannot be found, write "not found". Never fill a gap with a plausible number.
7. Not investment advice: the report is research to learn from.
