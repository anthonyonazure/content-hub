# The US Army Has a Free Manual for Not Fooling Yourself. I Turned It Into an AI Prompt.

*By Anthony · VortexMSP*

There's a document most business owners have never opened, and it's sharper than a lot of the strategy advice they pay for. The University of Foreign Military and Cultural Studies publishes it. It runs about 220 pages, it's approved for public release, and it's called the Red Team Handbook.

Red teaming is the practice of attacking your own plan on purpose. You go hunting for the holes before a competitor, a customer, or plain reality finds them for you. The book says it straight: red teaming is risk management for the human brain. Its whole argument is that most failures don't come from stupidity. They come from capable people who never questioned an assumption, agreed too fast, and mistook activity for progress.

I read the whole thing and pulled out the parts that work on business decisions. Below is what's in it, the prompts I built from it, and how I turned those prompts into a command I now run in a single word.

## What the book contains

The handbook rests on four skills. Self-awareness, so you know your own biases before you decide anything. Cultural empathy, so you grasp how the other side actually sees the situation instead of how you imagine they do. Applied critical thinking, for taking arguments apart and testing what holds them up. And groupthink mitigation, which is the unglamorous work of getting honest input from a group instead of a room quietly agreeing with whoever outranks them.

Under those four skills sit roughly forty tools. Premortems. Assumption checks. Competing-hypotheses analysis. Devil's advocacy. Stakeholder mapping. Each one is a repeatable way to challenge a belief, surface what you overlooked, or force yourself to weigh an option you'd rather ignore.

One sentence anchors the whole book. It comes from the Army Chief of Staff: every assumption we hold, every claim, every assertion, every single one of them must be challenged. That's the discipline in a line.

## The reframe: the tools are prompts

Once you see the pattern, the next move is obvious. Each tool is a script for interrogating a decision, so each one drops cleanly into a prompt you can hand to an AI or to a colleague who'll tell you the truth. I built a set for vetting business bets — new offers, prospecting plays, pricing changes, anything with money behind it. Run them in this order.

**1. Problem Restatement.** Make sure you're solving the right thing.

> Restate the real problem my idea solves five ways: paraphrased, inverted, broadened, refocused onto a different variable, and as a 5-Whys chain. Tell me whether I'm solving the right problem or chasing a symptom. Be specific: is this a lead-generation problem, or a positioning, offer, or conversion problem wearing a lead-gen costume?

**2. Key Assumptions Check.** Find what has to be true.

> List every assumption my idea depends on, stated and unstated. For each: why must it be true, does it hold under all conditions, and how badly does the idea break if it's false? Assign each a confidence percentage, multiply them for the odds that all hold at once, and name the weakest link. Rank the assumptions by how many others depend on them, and tell me which to test first.

**3. Perspective Flip.** Stop assuming customers think like you.

> Role-play my target customer in their own voice, not mine. What's their real problem and pain? What are they already doing about it? How does my offer appear to them — welcome, noise, or spam? Flag every place I assumed they think like me.

**4. Premortem.** Assume it already failed.

> It's six months from now and this failed completely. I wasted the time and money and got almost nothing. Give me a long, unfiltered list of why it failed, including the uncomfortable reasons. For each major cause, give me the cheapest early test that would have caught it.

**5. Devil's Advocacy and Alternatives.** Argue against yourself, then look for a better path.

> First, build the strongest possible case that this is a bad use of my resources, using the evidence I'm ignoring. Then give me three to five alternative ways to reach the same goal, and compare them to my plan on cost, speed, reach, and how well they fit the way my customer actually buys. Tell me honestly if one of them beats my idea.

**6. Root-Cause Check.** Symptom or cause?

> Treat my stated problem as a symptom. Identify the symptomatic quick-fix my idea might be, the fundamental root-cause fix, and the side-effects of chasing the symptom instead. Recommend whether I should do my idea, the root-cause fix, or both.

**7. Leading Indicators and Kill-Signals.** Know early, before you're broke.

> Define the signals in the first two to four weeks that tell me this is genuinely working — not vanity metrics like impressions or raw activity, but early signs of real qualified interest. Then define the kill-signals that mean I should stop or pivot. Give me one cheap experiment that produces those signals before I commit the full budget.

## The composite: one prompt that does all of it

If you'd rather run the whole gauntlet in one shot, paste this and fill in the bracket:

> You are my red team, built on the UFMCS Red Team methodology. Your job is to stress-test my decision by trying to disprove it, not confirm it. Challenge me throughout. Do not be agreeable.
>
> Decision under review:
> - What I want to do: `[the idea]`
> - Who it targets: `[customer / audience]`
> - Mechanism: `[channel, offer, method]`
> - Why I think it works: `[reasoning]`
> - Success looks like: `[concrete, measurable]`
> - Resources at risk: `[time, money, effort]`
>
> Run these phases in order and label each: (1) Problem Restatement — am I solving the real problem or a symptom? (2) Key Assumptions Check — list stated and unstated assumptions, assign confidence, name the weakest link. (3) Perspective Flip — role-play the customer in their voice; flag where I assumed they think like me. (4) Premortem — assume it failed; list causes and the cheapest test that would have caught each. (5) Devil's Advocacy plus three to five alternatives compared on cost, speed, reach, and fit. (6) Root-Cause Check — symptom versus fundamental fix. (7) Leading Indicators and kill-signals, plus one cheap experiment. (8) Verdict — the single biggest risk, the weakest assumption to validate first, a committed recommendation (proceed, modify, test-first, or drop for alternative), the cheapest next experiment, and explicit success and kill thresholds. No hedging.

## Turn it into a one-word command

If you use Claude Code, you don't have to keep pasting this. You can package the whole pipeline as a skill — a reusable command the assistant loads automatically and can trigger on its own. I turned this exact prompt into `/redteam`. Now I type `/redteam` plus the idea and it runs all eight phases without me babysitting it.

Building one takes about two minutes.

First, create a folder named for the command:

```
~/.claude/skills/redteam/
```

Inside it, create a file called `SKILL.md`. At the top goes YAML frontmatter with a name and a description:

```markdown
---
name: redteam
description: Adversarially stress-test a decision by trying to
  disprove it, then deliver a committed go/no-go verdict. Runs an
  8-phase gauntlet. Defaults to a business-strategy lens. Use when
  the user says "red team this", "stress-test my idea", "poke holes
  in this", "should I do this", or invokes /redteam.
---
```

Below the frontmatter, paste the actual instructions: your operating rules (disprove, don't confirm; don't be agreeable; end with a committed verdict), the eight phases in order, and a note telling it to ask for the decision details if you didn't provide them. Save the file. It loads on your next session and runs as `/redteam`.

The description field is the part people get wrong. It isn't documentation. It's the trigger — it's how the assistant decides when to fire the skill without being told the command name. So pack it with the phrases you'd naturally say out loud, like "poke holes in this" or "should I do this." Say any of them and the red team shows up on its own.

The full skill file is in the appendix below if you want to copy it wholesale.

## Why it works

Brainstorming and red teaming pull in opposite directions. One builds your idea up; the other tries to knock it down. People skip the second because watching your favorite plan get dismantled is unpleasant. That's exactly why it's worth doing. An idea that survives a real premortem and an honest attempt to disprove it is one worth funding. An idea that doesn't just saved you the check.

The handbook is free. Search "UFMCS Red Team Handbook v9." Read Chapter 7 if you read nothing else — that's the tool catalog.

---

*I send a newsletter with more field-tested prompts like these, plus the occasional teardown of a real business decision. If that's useful to you, [subscribe here](#your-newsletter-link).*

---

## Appendix: The complete `/redteam` skill file

Copy this into `~/.claude/skills/redteam/SKILL.md`:

```markdown
---
name: redteam
description: Adversarially stress-test a decision, idea, plan, or strategy using the U.S. Army UFMCS Red Team methodology — to disprove it rather than confirm it, then deliver a committed go/no-go verdict. Runs an 8-phase gauntlet (Problem Restatement, Key Assumptions + Sensitivity, Perspective Flip, Premortem, Devil's Advocacy + Alternatives, Root-Cause/Shifting-the-Burden, Leading Indicators, Verdict). Defaults to a BUSINESS STRATEGY lens (offers, channels, prospecting, pricing, GTM, growth bets) but supports security-assessment and content domains via a flag. Use when the user says "red team this", "redteam", "stress-test my idea", "pressure-test this plan", "poke holes in this", "should I do this", or invokes /redteam.
---

# /redteam — Red Team a Decision (Business-Strategy default)

Adversarial decision review built on the UFMCS Red Team Handbook (TRADOC G-2, v9.0). The governing rule (CSA Milley): "Every assumption we hold, every claim, every assertion, every single one of them must be challenged."

## Usage
    /redteam <the decision/idea, a file path, or "the above">
    /redteam --security   <decision>   Lens = security assessment / engagement
    /redteam --content    <decision>   Lens = content / publishing
    /redteam --quick      <decision>   Run only Phases 2, 4, 7, 8

Default lens (no flag) = business strategy.

## Operating rules (non-negotiable)
1. Disprove, don't confirm. Try to break the idea. Do not be agreeable.
2. Diverge before you converge. Generate alternatives and failure modes fully before recommending.
3. Make the implicit explicit. Surface unstated assumptions and "everyone knows…" claims.
4. Kill mirror-imaging. Never assume the customer/adversary/reader thinks like the user.
5. End with a committed verdict. No hedging.

## Step 0 — Capture the decision
If the user did not already supply these, ask for them once, then proceed:
- What I want to do — the decision/idea
- Who/what it targets or affects — ICP/audience, stakeholders, systems
- Mechanism — the actual method/channel/offer/approach
- Why I believe it'll work — the reasoning
- Success (concrete, measurable) — e.g. "20 sales-qualified calls/month"
- Resources at risk — time, money, reputation, effort
- Constraints / context — deadlines, budget, environment, fixed factors

If the user gives the idea but skips fields, infer reasonable defaults, state them explicitly, and continue — do not stall.

## The Gauntlet — run in order, label each phase

1. Problem Restatement. Restate the real problem 5 ways (paraphrase, invert, broaden, refocus, 5-Whys). Verdict: right problem or symptom? (Business default: is this a prospecting problem, or a positioning / offer / conversion / retention problem in disguise?)

2. Key Assumptions Check + Sensitivity. List every assumption, stated and unstated. For each: why it must be true, whether it holds under all conditions, how badly it breaks if false. Assign confidence %, multiply for P(all hold), name the weakest link. Rank by dependency; flag which to validate first.

3. Perspective Flip (4 Ways of Seeing + 6 Empathetic Questions). Fill 4 cells: how I see me, how I see them, how they see me, how they see themselves. Role-play the affected party in their voice. Flag every place the user assumed the other party thinks like them.

4. Premortem. It failed completely. List failure causes, uncomfortable included. For each, the cheapest early test that would have caught it.

5. Devil's Advocacy + Alternatives. Strongest case it's a bad use of resources, using ignored evidence. Then 3–5 alternatives compared on cost, speed, reach, fit. Say if one beats the plan.

6. Root-Cause Check (Shifting the Burden). Symptomatic quick-fix vs fundamental fix vs side-effects. Recommend idea, root-cause fix, or both.

7. Leading Indicators & Kill-Signals. Early signals (first 2–4 weeks) of real traction, not vanity metrics. Kill-signals for stop/pivot. One cheap experiment.

8. VERDICT. Biggest risk; weakest assumption to validate first; committed recommendation (proceed / modify / test-first / drop); cheapest next experiment; explicit success and kill thresholds.

## Domain lenses
- --security: In Phase 3, run "the other party" twice — adversary and client/asset-owner. Phase 4 = "the engagement missed the real exposure — why?" Phase 5 alternatives = different attack paths / assessment approaches.
- --content: Phase 3 "the other party" = the reader scrolling past. Phase 7 indicators = early engagement depth, not raw views.

## Notes
- The two phases that catch the most bad bets: Phase 3 (how they see you) and Phase 7 (cheap leading indicators). Never skip them.
- --quick is for fast gut-checks; full run is for anything with real resources at stake.
```
