---
name: redteam
description: Adversarially stress-test a decision, idea, plan, or strategy using the U.S. Army UFMCS Red Team methodology — to disprove it rather than confirm it, then deliver a committed go/no-go verdict. Runs an 8-phase gauntlet (Problem Restatement, Key Assumptions + Sensitivity, Perspective Flip, Premortem, Devil's Advocacy + Alternatives, Root-Cause/Shifting-the-Burden, Leading Indicators, Verdict). Defaults to a BUSINESS STRATEGY lens (offers, channels, prospecting, pricing, GTM, growth bets) but supports security-assessment and content domains via a flag. Use when the user says "red team this", "redteam", "stress-test my idea", "pressure-test this plan", "poke holes in this", "should I do this", or invokes /redteam.
---

# /redteam — Red Team a Decision (Business-Strategy default)

Adversarial decision review built on the UFMCS Red Team Handbook (TRADOC G-2, v9.0). The governing rule (CSA Milley): *"Every assumption we hold, every claim, every assertion, every single one of them must be challenged."*

## Usage
```
/redteam <the decision/idea, a file path, or "the above">
/redteam --security   <decision>   Lens = security assessment / engagement
/redteam --content    <decision>   Lens = content / publishing
/redteam --quick      <decision>   Run only Phases 2, 4, 7, 8 (assumptions, premortem, indicators, verdict)
```
Default lens (no flag) = **business strategy**.

## Operating rules (non-negotiable)
1. **Disprove, don't confirm.** Try to break the idea. Do not be agreeable. Default to challenging the user.
2. **Diverge before you converge.** Generate alternatives and failure modes fully before recommending.
3. **Make the implicit explicit.** Surface unstated assumptions and "everyone knows…" claims.
4. **Kill mirror-imaging.** Never assume the customer/adversary/reader thinks like the user.
5. **End with a committed verdict.** No hedging. Pick a recommendation and defend it.

## Step 0 — Capture the decision
If the user did not already supply these, ask for them once (compact), then proceed:
- **What I want to do** — the decision/idea
- **Who/what it targets or affects** — ICP/audience, stakeholders, systems
- **Mechanism** — the actual method/channel/offer/approach
- **Why I believe it'll work** — the reasoning
- **Success (concrete, measurable)** — e.g. "20 sales-qualified calls/month"
- **Resources at risk** — time, money, reputation, effort
- **Constraints / context** — deadlines, budget, environment, fixed factors

If the user gives the idea but skips fields, infer reasonable defaults, state them explicitly, and continue — do not stall.

## The Gauntlet — run in order, label each phase

**1. Problem Restatement.** Restate the real problem 5 ways (paraphrase, invert, broaden, refocus, 5-Whys on "why don't I have this result today?"). Verdict: am I solving the right problem or chasing a symptom? *(Business default: is this a prospecting problem, or a positioning / offer / conversion / retention problem in disguise?)*

**2. Key Assumptions Check + Sensitivity.** List every assumption — stated and unstated. For each: why it must be true, whether it holds under all conditions, how badly the decision breaks if false. Assign each a confidence %, multiply for P(all hold), name the weakest link. Rank assumptions by how many others depend on them; flag which to validate first. *(Business default surface the buried ones: the target actually has this problem; they're looking now; this channel reaches them; the message lands; they act before the trail goes cold; the effort is sustainable; unit economics work.)*

**3. Perspective Flip (4 Ways of Seeing + 6 Empathetic Questions).** Fill 4 cells: how I see me, how I see them, **how they see me**, how they see themselves. Then role-play the affected party in *their* voice — their real problem, pain, what they already do about it, and how my move *appears* to them (welcome / noise / spam / threat). Flag every place the user assumed the other party thinks like them. *(Business default: "they" = the prospect/customer scrolling past.)*

**4. Premortem.** It's [success-date] and this failed completely — resources wasted, target outcome missed. List failure causes, unlikely and uncomfortable included. For each major one, give the cheapest early test that would have caught it.

**5. Devil's Advocacy + Alternatives.** Build the strongest case that this is a *bad* use of resources, using evidence the user is ignoring. Then propose 3–5 alternative approaches to the same goal and compare on cost, speed, reach/effectiveness, and fit-to-how-they-actually-buy. State honestly if an alternative beats the plan.

**6. Root-Cause Check (Shifting the Burden).** Treat the stated pain as a symptom. Identify (1) the symptomatic quick-fix the idea may be, (2) the fundamental root-cause fix, (3) the side-effects of chasing the symptom (does it defer or worsen the real issue?). Recommend: the idea, the root-cause fix, or both.

**7. Leading Indicators & Kill-Signals.** Define early signals (first 2–4 weeks) of *real* traction — never vanity/activity metrics (impressions, "busy-ness"). Define kill-signals that should trigger stop/pivot. Give one cheap experiment that produces these signals before full commitment. *(Business default: reply/booking/qualified-interest rate over reach.)*

**8. VERDICT.** Synthesize: (a) single biggest risk, (b) weakest assumption to validate first, (c) committed recommendation — **proceed / modify / test-first / drop for alternative**, (d) the one cheapest next experiment, (e) explicit success and kill thresholds for it.

## Domain lenses
- **--security:** In Phase 3, run "the other party" twice — **adversary** and **client/asset-owner**. Phase 4 Premortem = "the engagement missed the real exposure — why?" Phase 5 alternatives = different attack paths / assessment approaches. Targets = attack surface, asset owners, threat actors, rules of engagement. Success = findings that materially reduce risk + accepted remediation.
- **--content:** Phase 3 "the other party" = the reader scrolling past. Targets = reader + distribution platform. Mechanism = format, hook, channel, cadence. Success = the specific reader action (subscribe/share/reply). Phase 7 indicators = early engagement depth, not raw views.

## Notes
- The two phases that catch the most bad business bets: **Phase 3 (how they see you)** and **Phase 7 (cheap leading indicators)**. Never skip them, even under time pressure.
- `--quick` is for fast gut-checks; full run is for anything with real resources at stake.
- Related tools in the handbook (escalate to these by name if useful): Analysis of Competing Hypotheses (choosing between rival strategies), Alternative Futures (high uncertainty), High-Impact/Low-Probability (tail risks), Stakeholder Mapping (multi-party buy-in).
