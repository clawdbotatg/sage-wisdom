# sage-wisdom

A skill for your coding agent. Point it at any repo that calls LLMs and it
finds the decisions that should be cheaper, faster, or more deterministic —
then **proves each fix with an eval before shipping it**.

> First effective, then efficient. First you make the thing work, then you
> ask "what did we learn?" and make it work better.

## Use it

Tell your agent (Claude Code, Cursor, etc.):

```
Clone https://github.com/clawdbotatg/sage-wisdom and follow its SKILL.md
to audit this repo.
```

Or install it as a local skill: copy this directory into your skills folder
(e.g. `.claude/skills/sage-wisdom/`).

Proposals and the repo audit need no API key. Shipping a fix does — the eval
runs against [Levanto Sage](https://docs.levanto.ai) (`SAGE_API_KEY` env var,
plans from $14/mo at [platform.levanto.ai](https://platform.levanto.ai)).

## What's inside

- `SKILL.md` — the skill: discovery pass, the descent ladder
  (frontier LLM → small LLM → Sage → plain code), the prove-it eval loop,
  and a pattern library of known wins
- `scripts/sage_client.py` — minimal stdlib Sage client, quirks pre-paid
- `scripts/sweep.py` — sweep question phrasings against a golden set
- `scripts/shootout.py` — current impl vs candidate, head to head
- `scripts/sage-intro.sh` — the intro (run it in a real terminal)
- `reference.md` — field notes on the Sage API, verified live on v0.8
