# AI board of advisors for Claude Code

Five advisors answer your question **as separate agents that never see each other's answers**, then a chair finds where they disagree and gives one recommendation. Every advisor has to finish one extra line: **"What will the others miss?"** That line is where the useful, non-obvious answers come from.

## Use it in Claude Code
1. Copy the [`.claude/agents/`](.claude/agents/) folder into your project (or into `~/.claude/agents/` to use it everywhere).
2. Tell Claude Code:
   > Run the senior-developer, recruiter, entrepreneur, ai-engineer and skeptic agents in parallel on this question: *your question*. Then give all five answers to the board-chair agent.

| File | Advisor |
|---|---|
| `senior-developer.md` | 15 years in software, knows what breaks when people ship code they don't understand |
| `recruiter.md` | hires for marketing and tech roles, cares about what gets people hired or promoted |
| `entrepreneur.md` | started a business at 38 with no technical background |
| `ai-engineer.md` | builds agents and automations every day, knows where AI fails |
| `skeptic.md` | looks for the flaw in whatever the others will say |
| `board-chair.md` | reads all five answers, names the biggest disagreement and gives the final recommendation |

Change the roles to fit your question (a lawyer, a customer, a CFO…). Keep the "What will the others miss" line.

## No Claude Code? Use one prompt
Paste [`one-prompt.txt`](one-prompt.txt) into any chat. In my test the advisors agreed more in one chat (4–1) than as separate agents (2–2–1).

## My test (16 Oct 2026, Claude Opus 5.5)
Question: *"I'm 35. I work in marketing and I've never written code. I can spare about one hour a day. Should I learn to code, or just learn AI?"*
- **One normal prompt:** learn AI first, skip a traditional coding course. Good advice, and what you'd expect.
- **Five separate agents:** learn AI 2 · both 2 · neither yet 1. The developer and the AI engineer independently warned that AI rarely crashes when it's wrong: it gives you a confident wrong answer, so you need to be able to read the code. The founder: do it on work time, so your company pays for your learning.
- **Chair:** learn AI, and learn to read code through it. This week, have AI write a script for your most boring task and explain every line.

Full answers in [`example/`](example/). One test with the same model in every role, not a benchmark.

Made for the reel on [Instagram @aipractically](https://www.instagram.com/aipractically/) and [YouTube @aipracticallykris](https://www.youtube.com/@aipracticallykris).
