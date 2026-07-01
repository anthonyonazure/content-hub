# Twitter/X Thread — Red Team Your Decisions

*Byline: Anthony · VortexMSP · CTA: newsletter*

---

**1/**
The US Army has a ~220-page manual on making better decisions. Declassified, free, and sharper than most "critical thinking" courses you'd pay for.

I turned its tools into prompts you can run on any business idea before you spend a dollar.

Thread 🧵

**2/**
It's the Red Team Handbook (UFMCS, TRADOC G-2).

"Red teaming" = professionally attacking your own plan before reality does it for you.

The book's own words: it's "risk management for the human brain."

**3/**
What's inside: ~40 structured thinking tools built on four skills — self-awareness, cultural empathy, applied critical thinking, and groupthink mitigation.

Every tool does three things: challenge assumptions, expose what you missed, force alternatives.

**4/**
The governing line, from the Army Chief of Staff:

"Every assumption we hold, every claim, every assertion, every single one of them must be challenged."

Most bad calls aren't stupid. They're smart people never testing what they took for granted.

**5/**
The reframe: every one of those tools is basically a prompt.

Feed them to an AI (or an honest colleague) to gut-check a decision before you commit money. I built a set for vetting business ideas. Steal them.

**6/**
PROMPT — Key Assumptions Check:

"List every assumption my idea depends on, stated and unstated. For each: why must it be true, and how badly does the idea break if it's false? Rank them by how many other assumptions depend on them, and tell me which to test first."

**7/**
PROMPT — Perspective Flip (kills the #1 marketing mistake: assuming customers think like you):

"Role-play my target customer in their own voice. What's their real problem? How does my offer appear to them — welcome, or noise? Flag every place I assumed they think like me."

**8/**
PROMPT — Premortem:

"It's 6 months out and this failed completely. I wasted the money and got nothing. List every reason it failed, uncomfortable ones included. For each, give the cheapest test that would've caught it early."

**9/**
PROMPT — Leading Indicators:

"Define signals in the first 2–4 weeks that tell me this is actually working — not vanity metrics like impressions. Then define the kill-signals that mean stop. Give me one cheap test to produce them before I go all in."

**10/**
Chain them into one. The composite "red team a decision" prompt, compressed:

"Stress-test my idea by trying to DISPROVE it, not confirm it. Run: 1) am I solving the real problem? 2) weakest assumption 3) how the customer sees it 4) premortem 5) 3 better alternatives 6) root cause vs symptom 7) cheap early signals 8) verdict. Don't be agreeable."

**11/**
Last upgrade: I stopped copy-pasting these.

In Claude Code you can package prompts as "skills" — reusable commands. So I built one. Now I type `/redteam <idea>` and it runs the whole 8-phase gauntlet on its own.

**12/**
Building it takes ~2 minutes:

• make a folder: `~/.claude/skills/redteam/`
• add a file: `SKILL.md`
• put your 8-phase instructions in the body
• add frontmatter with a `name` + a `description` full of trigger phrases

That `description` is how it auto-fires.

**13/**
Why this beats brainstorming:

Brainstorming tries to confirm your idea. Red teaming tries to kill it.

The ideas that survive a real premortem are the ones actually worth funding.

**14/**
The whole loop: a free Army manual → a set of prompts → one composite → a command you run in a single word.

Book's free (search "UFMCS Red Team Handbook v9").

Full prompts + composite + the skill file are in my newsletter 👇
[your-newsletter-link]
