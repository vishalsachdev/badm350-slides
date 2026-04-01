---
theme: default
title: 'Week 10: Cloud & Enterprise — Session 2'
info: |
  BADM 350 — IT for Networked Organizations
  Unit D: Enterprise Enablement
author: Vishal Sachdev
transition: slide-left
colorSchema: light
mdc: true
---

# Cloud & Enterprise Systems

## Week 10 · Session 2: Team Presentations

<div style="margin-top: 2em; color: #888;">

BADM 350 — Session 2

April 2, 2026

[Canvas: Week 10 Overview](https://canvas.illinois.edu/courses/68238/pages/week-10-overview-cloud-and-enterprise-systems)

</div>

---

# Today's Plan

<div style="font-size: 1.1em; line-height: 2;">

| Time | Activity |
|------|----------|
| 0–5 | Notes collection + framing |
| 5–40 | 7 team presentations (5 min each, strict) |
| 40–48 | Think-Pair-Share: Patterns you noticed |
| 48–60 | Full-class discussion: Lock-in, cost, migration |
| 60–70 | Checkpoint 4 preview + TPS: Security thinking |
| 70–75 | Wrap-up + notes collection |

</div>

---
layout: section
---

# Team Presentations
## 5 minutes each — 3 min walkthrough, 2 min Q&A

---

# Presentation Format

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 2em; margin-top: 1.5em;">

<div style="background: #e8f0fe; border-left: 4px solid #12284c; padding: 1.5em; border-radius: 8px;">

### Your 3 Minutes

1. What alternative did you research?
2. Walk through your migration planner — show the **cost comparison**
3. Would you actually switch? **One sentence.**

</div>

<div style="background: #fff0e6; border-left: 4px solid #ff5f05; padding: 1.5em; border-radius: 8px;">

### Then 2 Minutes Q&A

Your classmates and I will ask questions like:

- What surprised you about pricing?
- What would break first if you migrated?
- What did Run 2 give you that Run 1 didn't?

</div>

</div>

<div style="margin-top: 1.5em; text-align: center; font-weight: bold; color: #ff5f05; font-size: 1.2em;">

Timer is running. 5 minutes means 5 minutes.

</div>

---

# Comparison Board

<div style="margin-top: 1em; font-size: 0.9em;">

*We'll fill this in as teams present.*

| Team | Project | Alternative | Key Finding | Would You Switch? |
|------|---------|-------------|------------|-------------------|
| 1 | | | | |
| 2 | | | | |
| 3 | | | | |
| 4 | | | | |
| 5 | | | | |
| 6 | | | | |
| 7 | | | | |

</div>

<div style="margin-top: 1em; font-size: 0.9em; color: #888;">

By the end of presentations, this board gives us a class-wide view of the cloud landscape.

</div>

---
layout: section
---

# Discussion
## What Patterns Did You Notice?

---
layout: center
---

# Think-Pair-Share

<div style="background: #e8f0fe; border-left: 4px solid #12284c; padding: 1.5em; border-radius: 8px; margin-top: 1em; font-size: 1.1em;">

**Question:** Across all 7 presentations, where is our class **most locked in**? Is it the database (Supabase), the builder (Lovable), or something else?

</div>

<div style="display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 1.5em; margin-top: 2em; text-align: center;">

<div style="background: #f5f5f5; border: 1px solid #ddd; padding: 1.2em; border-radius: 8px;">

### Think
1 minute — jot down your answer

</div>

<div style="background: #f5f5f5; border: 1px solid #ddd; padding: 1.2em; border-radius: 8px;">

### Pair
2 minutes — compare with your neighbor

</div>

<div style="background: #fff0e6; border-left: 4px solid #ff5f05; padding: 1.2em; border-radius: 8px;">

### Share
Volunteers — what did your pair conclude?

</div>

</div>

---

# Class Discussion

<div style="margin-top: 1em; font-size: 1.05em; line-height: 1.8;">

Now that we've seen all 7 alternatives:

1. **Cost surprises** — What's actually expensive at scale? What's cheaper than expected?

2. **Migration reality** — Which alternatives are realistic to actually migrate to? Which are fantasy?

3. **Context experiment** — Who found the biggest difference between Run 1 and Run 2? What did AI get wrong even WITH context?

4. **Case 1 callback** — Are cloud services more or less sticky than consumer software (Apple)? Why?

</div>

---

# From the Early Submissions

<div style="background: #f0f0f5; border-left: 4px solid #12284c; padding: 1.5em; border-radius: 8px; margin-top: 1.5em;">

> "Run 1 was extremely generic. It just treated it like a basic web app... Run 2 picked up things about our app and mentioned components like apartments, reviews, profiles, and favorites."

> "It still got a lot of things wrong though. It assumed Supabase was already fully set up on our live app when it's not even close."

<div style="text-align: right; font-size: 0.85em; color: #888; margin-top: 0.5em;">— Apartment Reviews team, Firebase alternative</div>

</div>

<v-click>

<div style="margin-top: 1.5em; font-size: 1.15em; font-weight: bold; color: #ff5f05;">

The AI knows Supabase generically. It doesn't know YOUR Supabase until you show it — and even then, it overestimates.

</div>

</v-click>

---
layout: section
---

# Checkpoint 4 Preview
## Week 11: Security & Controls (60 pts)

---

# What Checkpoint 4 Adds to Your Work

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 2em; margin-top: 1.5em;">

<div>

### You Already Have (from Case 2)

- Architecture diagram of your stack
- Service classification (IaaS/PaaS/SaaS/BaaS)
- Cost analysis at different scales
- Lock-in and migration assessment

</div>

<div style="background: #fff0e6; border-left: 4px solid #ff5f05; padding: 1.5em; border-radius: 8px;">

### Week 11 Adds

- **CIA Triad** — Confidentiality, Integrity, Availability applied to YOUR data
- **Data integration depth** — how data flows between services
- **Controls assessment** — what governance applies
- **Capital One breach** — what happens when shared responsibility fails

</div>

</div>

<div style="margin-top: 1.5em; font-weight: bold; color: #12284c;">

Keep your context folder and migration planner. You'll build directly on them.

</div>

---
layout: center
---

# Think-Pair-Share: Security Preview

<div style="background: #fef0f0; border: 1px solid #e57373; padding: 1.5em; border-radius: 8px; margin-top: 1em; font-size: 1.1em;">

**Question:** What is the single biggest security risk in your project right now? Think about your data, your users, and your cloud services.

</div>

<div style="display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 1.5em; margin-top: 2em; text-align: center;">

<div style="background: #f5f5f5; border: 1px solid #ddd; padding: 1.2em; border-radius: 8px;">

### Think
1 minute

</div>

<div style="background: #f5f5f5; border: 1px solid #ddd; padding: 1.2em; border-radius: 8px;">

### Pair
2 minutes

</div>

<div style="background: #fff0e6; border-left: 4px solid #ff5f05; padding: 1.2em; border-radius: 8px;">

### Share
2-3 pairs share out

</div>

</div>

<v-click>

<div style="margin-top: 1.5em; text-align: center; font-size: 1em; color: #888;">

Hold that thought. Week 11 gives you the framework to answer this rigorously.

</div>

</v-click>

---

# What's Next

<div style="margin-top: 1.5em; font-size: 1.05em; line-height: 1.8;">

- **No new lab this week** — Case 2 was the lab
- **Week 11 (next Tue/Thu):** Security & Controls
  - Reading: Chapter 21 (Information Security) — assignment TBD
  - Capital One breach case study
  - AI security lab
  - **Checkpoint 4: Integration + Review (60 pts)**
- **Keep your context folder** — it becomes the foundation for Checkpoint 4

</div>

<div style="background: #e8f0fe; border-left: 4px solid #12284c; padding: 1em; border-radius: 8px; margin-top: 1.5em;">

**Bridge:** You now understand your stack like an investor would. Next week we ask: *is it secure?* What happens when things go wrong?

</div>
