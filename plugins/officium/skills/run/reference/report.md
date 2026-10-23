# How the report is written

Match the site's own reports: plain English, short paragraphs, tables where they help, every number with its source. The site shows the Markdown in its reader: `#` is the title, each `##` becomes a chapter in the contents list (number them: `## 1. The business`), `###` are sub-sections.

## Top of the report

```markdown
# Nintendo (TSE: 7974): Four-Masters Investment Research
> Research date: 2026-10-23 · Price at research: **¥8,950** (close 22 Oct 2026, Yahoo Finance and Nikkei) · Currency: JPY
> Framework: ai-berkshire `/investment-research` (Buffett · Munger · Duan Yongping · Li Lu), researched with the Officium plugin by four analyst agents and a lead.
> Requested by a friend of the Officium for: *their note, if any, in a few words*
> **Educational research only. Not investment advice.**
```

## Chapters for a company report

0. **Information rating and AI limitations**: the A/B/C rating and why, what could not be checked, any contradictions between the analysts and how they were settled, the five spot-checked numbers.
1. **Key facts and checks**: a table of the key figures with both sources, the arithmetic checks (market value = price × shares, and so on), and a five-year record (revenue, margins, profit, free cash flow, cash, debt).
2. **The business** (Duan Yongping): the one-sentence business, where the money comes from, is it a good business. End with a quoted box: `> **Duan Yongping's question: what is good about this business, in one sentence?**`
3. **The moat** (Buffett): each kind of moat checked, the trend, and `> **Buffett's question: will the moat still be there in ten years, and what could destroy it?**`
4. **Inversion and risks** (Munger): how it could fail (a table: path, likelihood, impact), a historical analogy, the bear case, and `> **Munger's question: where am I most likely to be wrong, and why would smart people not buy?**`
5. **Management**: key decisions and how they turned out, capital allocation, ownership and pay, and `> **Duan Yongping's question: if the CEO retired, would the company stay as strong?**`
6. **Industry and the long view** (Li Lu): structure, competitors, where the profits pool, and `> **Li Lu's question: looking back from twenty years on, is this a lasting franchise or a passing one?**`
7. **Valuation and margin of safety**: today's multiples against history and peers, what growth the price already assumes, three scenarios three years out (growth × P/E → value per share, from the script or written out), and the buy-below price.
8. **Verdict**: Avoid, Wait or hold, or Favour; the three reasons; what would change the verdict; what to do if you own it and if you do not.
9. **Sources**: a numbered list of the links used.

Other kinds of report use the chapters their kind describes in [kinds.md](kinds.md), keeping chapter 0 (rating and limitations) first and **Sources** last.
