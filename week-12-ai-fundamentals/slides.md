---
theme: default
title: 'Week 12: Directing AI'
info: |
  BADM 350 — IT for Networked Organizations
  Unit E: AI Strategy
author: Vishal Sachdev
transition: slide-left
colorSchema: light
mdc: true
navigator: false
drawings:
  enabled: false
---

<style>
div[class*="fixed"][class*="right-5"],
div[class*="fixed"][class*="right-4"][class*="z-modal"] {
  display: none !important;
}
h2 { color: #12284c; border-bottom: 3px solid #c84113; padding-bottom: 6px; }
strong { color: #c84113; }
blockquote { border-left: 4px solid #c84113; color: #555; font-style: italic; padding-left: 1em; }
</style>

# Directing AI

## Week 12 · AI Fundamentals + Codex Live Demo

<div style="margin-top: 2em; color: #888;">

BADM 350 — Unit E: AI Strategy · Session 1

Tue Apr 14, 2026

[Canvas: Week 12 Overview](https://canvas.illinois.edu/courses/68238/pages/week-12-overview-ai-fundamentals)

</div>

---

## Where we've been

- **Unit A — Foundations:** What IS is, how it creates advantage
- **Unit B — Digital Economics:** Scale, platforms, network effects
- **Unit C — Data:** SQL, analytics, storytelling
- **Unit D — Enterprise:** Cloud, security, controls

<div style="margin-top: 2em;">

**You built a thing. You secured it. You know how it works.**

</div>

---
layout: center
---

# Now the question shifts

## *How does AI actually work —*
## *and how do you direct it like a business tool?*

---

## Unit E roadmap (4 weeks)

| Week | Focus | What you'll do |
|------|-------|---------------|
| **12** | AI Fundamentals | Learn Codex on a fake startup (NovaBrew) |
| **13** | Agentic Workflows | Point Codex at **your** project |
| **14** | AI Operating Model | Case 3: Capital One |
| **15** | Final Presentation | Board memo + live demo |

<div style="margin-top: 1.5em;">

> The skills you build this week become exhibits in your final pitch.

</div>

---
layout: center
---

## You're not learning to code.

## You're learning to **direct a coding agent in plain English.**

<div style="margin-top: 2em; text-align: center;">

**No prior coding experience required. Seriously.**

</div>

---

## Why this matters (strategically)

<div style="font-size: 1.3em; color: #c84113; margin-bottom: 0.8em;">

**Execution is cheap.** *Deciding what to execute* is the job.

</div>

- **The old bottleneck:** *"Can we build it?"* — engineers, time, budget
- **The new bottleneck:** *"Should we build it? For whom? Why now?"*
- **Step 1 — Decide.** Which problem, which customer, which tradeoff. An agent can't pick the right fight for you.
- **Step 2 — Describe.** Decompose that decision into things an agent can actually do.
- **This is a manager's job, not a developer's job** — and it's exactly what you'll be asked to do in 2 years.

<div style="margin-top: 1.5em;">

> *"The person who can brief an AI well is the person who gets the leverage."*

</div>

---

## Where AI agents shine

- **File operations** — read, parse, reorganize, summarize
- **Parallel research** — run 3 agents on 3 sources at once
- **Bounded analysis** — "find the top 3 themes in these reviews"
- **Repeatable workflows** — once it works, it works every time
- **Drafting** — first passes of emails, specs, code, memos

<div style="margin-top: 1.5em;">

**Pattern:** clear inputs → clear success signal → bounded scope

</div>

---

## Where AI agents fail

- **Judgment calls** with no clear right answer
- **Novel strategy** — anything that requires taste
- **Unbounded tasks** — *"make my business better"*
- **Anything without a verifiable success signal**
- **High-stakes decisions** with no human check

<div style="margin-top: 1.5em;">

**Pattern:** fuzzy goal → fuzzy output → you waste tokens and time

</div>

---
layout: center
---

## The core skill you're building

# Decomposing a business problem into **things an agent can actually do**

<div style="margin-top: 2em; text-align: center;">

This is the same discipline as writing a PRD (Week 7).
**Vague ask → vague output.** Whether you're briefing a human or a machine.

</div>

---

## Meet your instructor this week

<div style="text-align: center; font-size: 4em; margin: 0.2em 0;">🤖</div>

# Codex

- Free desktop app from OpenAI
- **The course runs inside the app itself** — Codex teaches you Codex
- You talk to it in plain English
- It reads files, writes files, runs commands, builds apps

<div style="margin-top: 1em;">

**Your job today:** install it, sign in, say *"Let's start"*

</div>

---

## The NovaBrew scenario

You're consulting for a fictional coffee startup. Over Modules 0–2 you'll:

1. **Read** messy customer feedback files
2. **Run parallel agents** to analyze reviews, sales, and competitors at once
3. **Build custom advisors** — a CEO, a Product Lead, a Customer Success voice
4. **Vibe code** and deploy a working Coffee Quiz web app to a live URL

<div style="margin-top: 1.5em;">

**By Thursday EOD:** you have a deployed app. No code written by hand.

</div>

---
layout: center
---

# Live demo time

## Watch how I talk to Codex.

## Not the features — **the prompts.**

<div style="margin-top: 2em;">

> *"What would you have asked differently?"*

</div>

---
layout: center
---

# 💰 Before you forget

## $100 in free Codex credits for UIUC students

<div style="margin-top: 1.5em;">

**chatgpt.com/codex/students**

Sign in → verify with @illinois.edu → done in 2 min

</div>

---

## Now: work session (~35 min)

### Your goal before we wrap

- ✅ Codex app installed
- ✅ Signed into ChatGPT
- ✅ NovaBrew course folder open in Codex
- ✅ **Module 0 complete** (Getting Started)
- ✅ **Module 1 started** (Fundamentals)

<div style="margin-top: 1em;">

**I'll circulate. Flag me down the second you get stuck.**

</div>

---

## Common pitfalls I'll be watching for

- Windows install friction → fall back to **web Codex** if needed
- No GitHub account → just download the **ZIP** from the repo
- ChatGPT asking for phone verification → Illinois email works, be patient
- Skipping Module 0 → **don't.** Directory setup matters.
- "I don't know what to type" → grab me, we'll model a prompt together

---

## Setup checklist (if you're starting fresh)

1. Download Codex: **chatgpt.com/codex**
2. Sign in to ChatGPT (personal account is fine)
3. Get the course repo: **github.com/vishalsachdev/codex-for-badm350**
   - Click green **Code** button → **Download ZIP** → unzip
4. Open the course folder in the Codex app
5. Type: **`Let's start`**
6. Follow the agent's lead

---

## Project note: no new checkpoint this week

- **No separate project deliverable** in Week 12
- Use any extra time to **refine your app based on Checkpoint 4 feedback**
- The Codex skills you learn this week feed **directly** into Week 13's lab (Module 3: Pre-Launch Toolkit)
- Next week you'll point Codex at **your** project and automate two real business processes

---

## Before Thursday

- **Aim for Module 2** (Vibe Coding) by end of class Thursday
- **Jot down 3 manual processes** in your project's business domain
  - Customer support? Content drafting? Competitor research? Data cleanup?
  - You'll use this list in Week 13 — don't skip it
- **Claim the $100 credits** if you haven't

---

## Due dates this week

| Deliverable | Points | Due |
|---|---|---|
| Session 1 participation | 3 | *Today* |
| Session 2 participation | 3 | Thu Apr 16 |
| **AI Fundamentals Lab** (Modules 0–2 + deployed app + reflection) | **5** | Mon Apr 20, 11:59 PM |
| **GenAI Module 3 Quiz** (Designing Interaction for Consistency) | **9** | Mon Apr 20, 11:59 PM |
| Yellowdig | — | Sun Apr 19, 11:59 PM |

---
layout: center
---

# Laptops open.
# Codex open.
# *"Let's start"*

<div style="margin-top: 1.5em; color: #888;">

I'll be walking the room.

</div>
