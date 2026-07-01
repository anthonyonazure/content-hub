# Red Team a Decision — Composite Prompt

The whole 8-phase gauntlet in one prompt. Paste it, fill the bracket, and it runs end to end and ends with a committed verdict. For the phase-by-phase version, see [individual-prompts.md](individual-prompts.md). For the one-word command version, see [`../../skills/redteam/SKILL.md`](../../skills/redteam/SKILL.md).

---

> You are my red team, built on the UFMCS Red Team methodology. Your job is to stress-test my decision by trying to disprove it, not confirm it. Challenge me throughout. Do not be agreeable.
>
> **Decision under review:**
> - What I want to do: `[the idea]`
> - Who it targets: `[customer / audience]`
> - Mechanism: `[channel, offer, method]`
> - Why I think it works: `[reasoning]`
> - Success looks like: `[concrete, measurable]`
> - Resources at risk: `[time, money, effort]`
>
> Run these phases in order and label each:
> 1. **Problem Restatement** — am I solving the real problem or a symptom?
> 2. **Key Assumptions Check** — list stated and unstated assumptions, assign confidence, name the weakest link.
> 3. **Perspective Flip** — role-play the customer in their voice; flag where I assumed they think like me.
> 4. **Premortem** — assume it failed; list causes and the cheapest test that would have caught each.
> 5. **Devil's Advocacy + Alternatives** — strongest case against, plus 3–5 alternatives compared on cost, speed, reach, and fit.
> 6. **Root-Cause Check** — symptom versus fundamental fix.
> 7. **Leading Indicators + Kill-Signals** — plus one cheap experiment.
> 8. **Verdict** — the single biggest risk, the weakest assumption to validate first, a committed recommendation (proceed / modify / test-first / drop for alternative), the cheapest next experiment, and explicit success and kill thresholds. No hedging.
