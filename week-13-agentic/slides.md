---
theme: default
title: 'Week 13: Agentic Workflows'
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

# Agentic Workflows

## Week 13 · Pre-Launch Toolkit

<div style="margin-top: 2em; color: #888;">

BADM 350 · Unit E: AI Strategy · Tue Apr 21, 2026

</div>

<div style="margin-top: 3em; padding: 1em; background-color: #f5f5f5; border-left: 4px solid #c84113;">
  <strong>Goal for today:</strong> defend where your product sits on the Workflow↔Agent spectrum — out loud, in one sentence.
</div>

---

## What we're doing today

- **0–13 min** · Think-Pair-Share: where's the inner loop / outer loop in your team's product?
- **13–43 min** · Gallery walk: post your two automation picks; other tables critique
- **43–68 min** · Lecture synthesis: spectrum + 5 patterns, grounded in the picks in this room
- **68–75 min** · Thursday preview + notes

<br>

> This is a **discussion-first** class. The lecture comes *after* you've argued with each other.

---
layout: section
---

# Part 1

## The Workflow↔Agent Spectrum

*Not a binary. Degrees of autonomy.*

---

## It's a dial, not a switch

```
Workflow ←————————————————————————————————→ Agent
```

<br>

| Pure workflow | Middle | Pure agent |
|---|---|---|
| Deterministic steps | LLM picks route | LLM plans + executes + iterates |
| Same input → same output | Some paths branch | Different runs → different paths |
| Cron job, `if/else`, SQL | RAG + routing, prompt chain | Codex, AutoGPT-style loops |

<br>

**Where does Codex sit?**
*It depends on how you direct it.* Tight instructions → workflow-ish. "Build me a landing page" → agent-ish.

---

## Common misconception

<div style="text-align: center; font-size: 1.4em; margin: 2em 0; color: #888;">

"Agent = autonomy = better"

</div>

<div style="text-align: center; font-size: 2em; color: #c84113; margin: 1em 0;">No.</div>

<br>

Cheaper, deterministic, debuggable **workflows** often beat agents. The skill is knowing when an agent is actually warranted.

<br>

<div class="grid grid-cols-2 gap-6">
<div>

**Good agent candidates**
- Open-ended goals
- Many valid paths
- Need tool use + iteration

</div>
<div>

**Bad agent candidates**
- Deterministic transforms
- Tight SLAs
- Anything a 10-line script does reliably

</div>
</div>

---
layout: section
---

# Part 2

## Inner Loop / Outer Loop

*Who owns which decision?*

---

## Two loops are always running

- **Inner loop** — the AI's execution turn
  - reads files, calls tools, writes output, iterates
  - starts when you say "go" · ends when it hands back

- **Outer loop** — your turn
  - accept, reject, redirect, give a new goal
  - the model has **no opinion** on whether the work was worth doing

- *Innermost loop* — the model's own reasoning (chain-of-thought, tool calls)
  - opaque · don't micromanage it

---

## Analogy — head chef / sous-chef

<div class="grid grid-cols-2 gap-8 pt-4">

<div>

### Sous-chef — inner loop
Prep, cook, taste-as-you-go, plate.

### Head chef — outer loop
Taste the final plate.
Decide if it goes out.
Plan tomorrow's menu.

</div>

<div>

### Bad head chef
Rubber-stamps the plate without tasting.
= Abdicating the outer loop.

### Micromanaging chef
"Stir now, stir now, stir now."
= Trying to control the innermost loop.

</div>

</div>

---

## You already did this last week

| Week 12 — what you did | Inner loop | Outer loop |
|---|---|---|
| Codex Module 0–2 (NovaBrew) | Codex reading files, writing components, running dev server | You: "CTA is ugly, redo pricing" |
| Module 1 parallel agents | 10 Codex runs, in parallel | You picking the best output |
| Week 11 prompt injection | LLM executing whatever it reads | *Missing* — that's why injection works |
| Week 8 SQL | Database running the query | You rewriting after seeing results |
| Week 6 Netflix recommenders | Model scoring titles | Users watching / skipping |

<br>

> **Last week you ran an inner loop for the first time — you just called it "letting Codex cook."**
> Today we name it so you can design the boundary on your own product.

---
layout: section
---

# Part 3

## Anthropic's 5 Patterns

*Each one is a different inner-loop shape.*

---

## Pattern 1 · Prompt chaining

<div style="background: #f5f5f5; padding: 1em; text-align: center; font-family: monospace; margin: 1em 0;">
[input] → LLM A → LLM B → LLM C → [output]
</div>

Linear. Each step's output feeds the next. Outer loop sits **at the end**.

<br>

**Use when:** task decomposes cleanly into sub-steps.
**Don't use when:** one well-prompted call is enough. Don't chain for chain's sake.

---

## Pattern 2 · Routing

<div style="background: #f5f5f5; padding: 1em; font-family: monospace; margin: 1em 0;">
<pre style="margin:0;">          ┌→ [Customer-service LLM]
[input] → [Router]
          └→ [Billing LLM]
</pre>
</div>

One LLM classifies; another handles. Outer loop picks the **routing rules**.

<br>

**Use when:** input categories need different prompts or tools.
*Examples: support triage, doc Q&A.*

---

## Pattern 3 · Parallelization

<div style="background: #f5f5f5; padding: 1em; font-family: monospace; margin: 1em 0;">
<pre style="margin:0;">          ┌→ [LLM] ┐
[input] ──┼→ [LLM] ┼→ [merge] → [output]
          └→ [LLM] ┘
</pre>
</div>

N inner loops fan out. Outer loop **merges**.

<br>

<div style="background: #fff8e6; border-left: 4px solid #c84113; padding: 1em;">
<strong>This is what Module 1 did</strong> — 10 Codex instances analyzing NovaBrew campaigns in parallel. You picked the best. That merge was your outer loop.
</div>

---

## Pattern 4 · Orchestrator-worker

<div style="background: #f5f5f5; padding: 1em; font-family: monospace; margin: 1em 0;">
<pre style="margin:0;">[Orchestrator LLM] → decides sub-tasks
         ↓ ↓ ↓
   [Worker] [Worker] [Worker]
         ↓ ↓ ↓
[Orchestrator LLM] → synthesizes
</pre>
</div>

Orchestrator plays a **mini outer loop** over workers. Human outer loop still sits above.

<br>

**Use when:** you can't predict the sub-tasks in advance.
*Examples: research agents, multi-file code edits.*

---

## Pattern 5 · Evaluator-optimizer

<div style="background: #f5f5f5; padding: 1em; font-family: monospace; margin: 1em 0;">
<pre style="margin:0;">[Generator] → output → [Evaluator] → feedback ↩
                              ↓ accept
                           [final]
</pre>
</div>

Model tries to **internalize part of the outer loop** via self-critique.

<br>

**The interesting question:** does self-critique reduce how much human outer loop you still need?

*Usually: less than you'd hope.* Self-critique catches obvious errors; humans still catch misaligned goals.

---

## When NOT to use an agent

<div class="grid grid-cols-2 gap-8 pt-4">

<div>

### Cheaper alternatives usually win
- Deterministic workflow solves it → use the workflow
- One well-prompted call solves it → skip the chain
- Rules-based script solves it → don't call an LLM at all

</div>

<div>

### Agents are expensive
- Longer latency
- Harder to debug
- Non-deterministic outputs
- Token costs compound per iteration

</div>

</div>

<br>

<div style="text-align: center; font-size: 1.2em; color: #12284c; margin-top: 1em;">
The skill isn't building the most autonomous system.<br>
<strong>It's knowing where autonomy earns its cost.</strong>
</div>

---
layout: section
---

# Live Synthesis

*Grounding in what your room just did.*

---

## Gallery-walk callouts

*(filled in live — pull from room)*

<br>

- **Team ____ picked Option ____** → pattern = ____
  - Inner loop: ____
  - Outer loop: ____

<br>

- **Team ____ picked Option ____** → pattern = ____
  - Inner loop: ____
  - Outer loop: ____

<br>

> **The question I'll ask you Thursday:** point at the inner-loop boundary.
> If you can't point at it, you haven't designed it — you pushed "go."

---

## Thursday's lab

- **Build** your automation (Module 3.2)
- **Demo** it to another team · pair-swap feedback form
- **Submit a PR** to the public class repo
- **Phase 2 (optional EC):** standout PRs invited into `codex-for-badm350`

<br>

### Due before Thursday 12:30

Individual proof screenshot + 1-paragraph reflection.

### Due in class Thursday

Capstone PR merged (or ready to merge).

---

## Wrap

- **End-of-class:** handwritten notes — add 2 gallery observations
- **Between now and Thursday:** Module 3.2 as a team; individual proof by 12:30
- **Looking ahead (Week 14):** AI governance (Capital One case). Same inner/outer framing — *what controls live in the outer loop?*

<br>

### Links
- Anthropic · [Building effective agents](https://www.anthropic.com/research/building-effective-agents)
- Class repo · [github.com/vishalsachdev/badm350-spring-2026-case-studies](https://github.com/vishalsachdev/badm350-spring-2026-case-studies)
- Codex course · [github.com/vishalsachdev/codex-for-badm350](https://github.com/vishalsachdev/codex-for-badm350)
