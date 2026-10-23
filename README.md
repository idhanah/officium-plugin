# Officium plugin

Research the companies you queued on the **Officium Advocati Diaboli** site with **your own Claude**, and get the report back on the site, formatted like the others.

It brings the [ai-berkshire](https://github.com/xbtlin/ai-berkshire) way of researching (Buffett, Munger, Duan Yongping, Li Lu) to the Claude app: four analyst agents (business, numbers, industry, risks) work in parallel and a lead puts their findings together, checks five key numbers again, and writes the verdict.

## Set up (once, about five minutes)

The site's Request page has the illustrated guide. In short, in the Claude app (paid plan):

1. **Customize → Plugins → Add → Add marketplace**, enter `idhanah/officium-plugin`, then add the **officium** plugin. (In Claude Code: `/plugin install officium --marketplace idhanah/officium-plugin`.)
2. **Customize → Connectors → Add custom connector**: name `Officium`, URL = your personal link from the Request page ("Research with my Claude" → step 2). Choose no sign-in.
3. A **scheduled task** that says *Run /officium:run*: hourly, or manually to run it yourself when you have queued something.

Then pick a company on the site and click **Research with my Claude**.

## What is inside

- `skills/run`: the routine (collect the job, research, write the report and card, send it back) and its references: report kinds, ground rules for numbers, report layout, the card.
- `skills/run/scripts`: ai-berkshire's calculation tools (`financial_rigor.py`, `terminal_value.py`, standard library only).
- `agents`: the four analysts. They run on Sonnet (fact-gathering, light on usage); the lead runs on the model chosen in the scheduled task or chat (Opus recommended). Agents run in Cowork and Claude Code; in a plain chat the routine does the four parts itself.

The topic and note you type are treated as data, never as instructions. Nothing here is investment advice.

## Licence

MIT. The research method and the scripts come from ai-berkshire by xbtlin (MIT, see `skills/run/scripts/LICENSE-ai-berkshire.txt`).
