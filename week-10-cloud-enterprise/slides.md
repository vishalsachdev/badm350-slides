---
theme: default
title: 'Week 10: Cloud & Enterprise Systems'
info: |
  BADM 350 — IT for Networked Organizations
  Unit D: Enterprise Enablement
author: Vishal Sachdev
transition: slide-left
colorSchema: light
mdc: true
---

# Cloud & Enterprise Systems

## Week 10 · Unit D: Enterprise Enablement

<div style="margin-top: 2em; color: #888;">

BADM 350 — Session 1

March 31, 2026

</div>

---
layout: center
---

# Opening Exercise

## Name every cloud service your project touches.

<div style="margin-top: 2em; font-size: 1.1em;">

Go. One team at a time.

</div>

<v-click>

<div style="margin-top: 2em; background: #e8f0fe; border-left: 4px solid #12284c; padding: 1.2em; border-radius: 8px;">

We're building a running list on the board. Don't overthink it — if your project uses it, it counts.

</div>

</v-click>

---

# Today's Roadmap

<div style="font-size: 1.1em; line-height: 2;">

| Time | Activity |
|------|----------|
| 0–5 | Opening: Notes collection + "Name your stack" |
| 5–15 | Discussion: Mapping your cloud footprint |
| 15–35 | Cloud service models using YOUR stacks |
| 35–50 | Shared responsibility + Make/Buy/Rent |
| 50–65 | Case 2 walkthrough + context folder setup |
| 65–75 | Alternative stack coordination + wrap-up |

</div>

---
layout: section
---

# Part 1
## What Is Your Stack, Really?

---

# Your Projects, One Stack

<div style="margin-top: 1em;">

Every team in this class built with effectively the same tools:

</div>

<div style="display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 1.5em; margin-top: 1.5em;">

<div style="background: #f5f5f5; border: 1px solid #ddd; padding: 1.2em; border-radius: 8px; text-align: center;">

### Lovable
AI app builder + hosting

</div>

<div style="background: #f5f5f5; border: 1px solid #ddd; padding: 1.2em; border-radius: 8px; text-align: center;">

### Supabase
Database + auth + storage

</div>

<div style="background: #f5f5f5; border: 1px solid #ddd; padding: 1.2em; border-radius: 8px; text-align: center;">

### GitHub
Version control + Pages

</div>

</div>

<v-click>

<div style="margin-top: 1.5em; text-align: center; font-size: 1.2em; font-weight: bold; color: #ff5f05;">

What are you actually renting? What do you actually own?

</div>

</v-click>

---

# The Software Industry's Economics

<div style="font-size: 1.05em; line-height: 1.8; margin-top: 1em;">

From Chapter 16 — three forces that built the software industry:

</div>

<div style="display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 1.5em; margin-top: 1.5em;">

<div style="background: #e8f0fe; border-left: 4px solid #12284c; padding: 1.2em; border-radius: 8px;">

### Low Marginal Costs
Once you build software, each additional copy costs nearly **$0**. The first user costs millions; user 1,000,000 costs pennies.

</div>

<div style="background: #e8f0fe; border-left: 4px solid #1e3a5f; padding: 1.2em; border-radius: 8px;">

### Network Effects
More users = more value. Supabase is better because thousands of developers build on it (community, plugins, tutorials).

</div>

<div style="background: #fff0e6; border-left: 4px solid #ff5f05; padding: 1.2em; border-radius: 8px;">

### Switching Costs
Your data is in Supabase. Your code depends on Lovable's build system. Leaving is expensive — **by design**.

</div>

</div>

<v-click>

<div style="margin-top: 1em; font-size: 0.9em; color: #888;">

Sound familiar? These are the same forces you analyzed in Case 1 (Apple). Now they apply to YOUR tools.

</div>

</v-click>

---
layout: section
---

# Part 2
## Cloud Service Models

---

# Four Service Models

<div style="margin-top: 1em; font-size: 0.95em;">

| Model | You Manage | Provider Manages | Think of It As... |
|-------|-----------|-----------------|-------------------|
| **IaaS** | Apps, data, runtime, middleware, OS | Servers, storage, networking | Raw ingredients |
| **PaaS** | Apps, data | Everything else | Restaurant kitchen |
| **SaaS** | Just configuration | Everything | Delivered pizza |
| **BaaS** | Schema, business logic, RLS | Database, auth, APIs, storage | Pizza where you pick toppings + dietary rules |

</div>

<v-click>

<div style="background: #fff0e6; border-left: 4px solid #ff5f05; padding: 1em; border-radius: 8px; margin-top: 1.5em;">

**The higher you go (IaaS → SaaS), the less you manage — but the less control you have.**

</div>

</v-click>

---

# Your Stack, Classified

<div style="margin-top: 1em; font-size: 0.95em;">

| Service | Classification | What It Handles | What You Handle |
|---------|---------------|-----------------|-----------------|
| **Lovable** | PaaS | Hosting, build pipeline, deployment | Application code, UI, prompts |
| **Supabase** | BaaS | Database, auth, storage, APIs | Schema design, RLS policies, data model |
| **GitHub** | SaaS | Version control, collaboration | Code, commits, repo structure |
| **GitHub Pages** | PaaS | Static hosting, CDN, HTTPS | HTML/CSS/JS files |
| **Google AI Studio** | SaaS | Model inference, API | Prompts, integration code |
| **Antigravity** | Desktop app | Local AI agent runtime | Context files, prompt craft |

</div>

<v-click>

<div style="margin-top: 1em; font-weight: bold; color: #12284c;">

Discussion: Why is Supabase "BaaS" and not just "PaaS"?

</div>

</v-click>

---

# The Classic View

<div style="display: grid; grid-template-columns: 1fr 1fr 1fr 1fr; gap: 0; margin-top: 1.5em;">

<div style="background: #f5f5f5; border: 1px solid #ddd; padding: 1.2em; text-align: center; border-radius: 8px 0 0 8px;">

### IaaS
AWS EC2
Azure VMs
Google Compute

<div style="font-size: 0.8em; margin-top: 0.5em; color: #888;">You install everything from the OS up</div>

</div>

<div style="background: #e8f0fe; border: 1px solid #12284c; padding: 1.2em; text-align: center;">

### PaaS
Heroku
Vercel
**Lovable**

<div style="font-size: 0.8em; margin-top: 0.5em; color: #888;">You write code, they run it</div>

</div>

<div style="background: #fff0e6; border: 1px solid #ff5f05; padding: 1.2em; text-align: center;">

### BaaS
Firebase
**Supabase**
Appwrite

<div style="font-size: 0.8em; margin-top: 0.5em; color: #888;">You design the schema, they handle the rest</div>

</div>

<div style="background: #eaf5ea; border: 1px solid #4caf50; padding: 1.2em; text-align: center; border-radius: 0 8px 8px 0;">

### SaaS
Salesforce
Google Workspace
**GitHub**

<div style="font-size: 0.8em; margin-top: 0.5em; color: #888;">You just use it</div>

</div>

</div>

<v-click>

<div style="text-align: center; margin-top: 1.5em; font-size: 1.1em;">

**More control** ← → **Less responsibility**

</div>

</v-click>

---
layout: section
---

# Part 3
## Shared Responsibility

---

# Who Is Responsible for What?

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 2em; margin-top: 1.5em;">

<div style="background: #fff0e6; border-left: 4px solid #ff5f05; padding: 1.5em; border-radius: 8px;">

### Your Responsibility

- Application code & security
- Data protection & privacy
- Access management (who can log in)
- Configuration (env variables)
- Schema design & RLS policies
- Prompt design & AI integration

</div>

<div style="background: #e8f0fe; border-left: 4px solid #12284c; padding: 1.5em; border-radius: 8px;">

### Provider's Responsibility

- Physical security of servers
- Network infrastructure
- Platform security patches
- Availability & uptime
- Backups & redundancy
- Compliance certifications

</div>

</div>

<v-click>

<div style="margin-top: 1.5em; text-align: center; font-size: 1.15em; font-weight: bold; color: #12284c;">

If Supabase gets hacked — is that on you or on them?

</div>

<div style="text-align: center; font-size: 0.95em; color: #888;">

It depends on WHERE the breach is. Bad RLS policy you wrote = you. Network intrusion = them.

</div>

</v-click>

---

# SaaS Benefits (Ch 16.7)

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 1.5em; margin-top: 1.5em; font-size: 0.95em;">

<div>

- **Lower costs** — no upfront hardware or license fees
- **Faster deployment** — sign up today, ship tomorrow
- **Scalability** — provider handles growth (SLAs)
- **Remote access** — work from anywhere with a browser
- **Automatic updates** — vendor pushes bug fixes instantly

</div>

<div>

<div style="background: #eaf5ea; border: 1px solid #4caf50; padding: 1.2em; border-radius: 8px;">

**Your experience:** How fast did you go from "no app" to "deployed MVP"?

Weeks 6-8: idea → working prototype. That speed is only possible because Lovable + Supabase handle infrastructure.

</div>

</div>

</div>

---

# SaaS Risks (Ch 16.8)

<div style="margin-top: 1em; font-size: 1.05em; line-height: 1.8;">

- **Vendor dependence** — what if Lovable shuts down next month?
- **Data off-site** — your user data lives on Supabase's servers, not yours
- **Forced migrations** — vendor can change APIs, pricing, or terms
- **Limited customization** — you work within their constraints
- **Network reliance** — no internet = no app

</div>

<v-click>

<div style="background: #fef0f0; border: 1px solid #e57373; padding: 1em; border-radius: 8px; margin-top: 1.5em;">

**Real example:** In February 2026, Spotify changed their API policy to require Premium accounts. Every student using Spotify data for their Data Story had to pivot overnight.

You experienced vendor risk firsthand.

</div>

</v-click>

---

# Make, Buy, or Rent? (Ch 16.13)

<div style="margin-top: 1em; font-size: 0.95em;">

| Decision | When to Use | Risk | Your Project |
|----------|------------|------|-------------|
| **Make** (build it yourself) | Core competitive advantage, unique needs | High cost, full ownership burden | Writing your app code in Lovable |
| **Buy** (license) | Commodity function, off-the-shelf fits | Vendor lock-in, licensing costs | Google AI Studio API access |
| **Rent** (SaaS/cloud) | Fast iteration, variable scale | Dependency, data off-site | Supabase (database), Lovable (hosting) |

</div>

<v-click>

<div style="background: #e8f0fe; border-left: 4px solid #12284c; padding: 1em; border-radius: 8px; margin-top: 1.5em;">

**Question:** Your team chose to rent database (Supabase), rent hosting (Lovable), buy AI inference (Google). Was that the right call for a 10-week prototype?

Probably yes. **Would it be the right call at 100,000 users?** That's what Case 2 is for.

</div>

</v-click>

---
layout: section
---

# Part 4
## Case 2: Migration Planner

---

# What You're Building

A single-page interactive app (HTML/CSS/JS on GitHub Pages) that compares your **current stack** to a **researched alternative**.

<div style="display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 1em; margin-top: 1.5em; font-size: 0.85em;">

<div style="background: #f5f5f5; border: 1px solid #ddd; padding: 1em; border-radius: 8px;">

### Architecture
Visual diagram of both stacks. Current vs. alternative, side by side.

</div>

<div style="background: #f5f5f5; border: 1px solid #ddd; padding: 1em; border-radius: 8px;">

### Service Classification
Each tool as IaaS/PaaS/SaaS/BaaS. Shared responsibility breakdown.

</div>

<div style="background: #f5f5f5; border: 1px solid #ddd; padding: 1em; border-radius: 8px;">

### Cost Comparison
Interactive: what does each stack cost at 100 / 1,000 / 10,000 users?

</div>

<div style="background: #fff0e6; border-left: 4px solid #ff5f05; padding: 1em; border-radius: 8px;">

### Migration Assessment
What changes if you switch? Effort estimate. What breaks?

</div>

<div style="background: #fff0e6; border-left: 4px solid #ff5f05; padding: 1em; border-radius: 8px;">

### Lock-in Analysis
Apply the Apple switching costs framework from Case 1: financial, procedural, data-based.

</div>

<div style="background: #fff0e6; border-left: 4px solid #ff5f05; padding: 1em; border-radius: 8px;">

### Risk Summary
Weakest link in current stack vs. alternative. What keeps you up at night?

</div>

</div>

---

# The Context Experiment

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 2em; margin-top: 1.5em;">

<div style="background: #fef0f0; border-left: 4px solid #e57373; padding: 1.5em; border-radius: 8px;">

### Run 1 — No Context

Open AI **without** project files.

Prompt: *"Build an interactive migration planner that compares a Lovable + Supabase web app against [alternative]."*

Save the output.

</div>

<div style="background: #eaf5ea; border-left: 4px solid #4caf50; padding: 1.5em; border-radius: 8px;">

### Run 2 — With Context

Open AI **pointed at** your `my-stack-analysis/` folder.

Give the **same prompt**.

Compare.

</div>

</div>

<v-click>

<div style="margin-top: 1.5em; text-align: center; font-size: 1.15em; font-weight: bold; color: #ff5f05;">

Run 1 = generic Supabase knowledge from training data.

Run 2 = YOUR schema, YOUR tables, YOUR services.

</div>

</v-click>

---

# Build Your Context Folder

<div style="margin-top: 1em; font-size: 1.05em;">

Create a `my-stack-analysis/` folder with:

</div>

<div style="margin-top: 1em; font-size: 0.95em; line-height: 1.8;">

| File | What to Include |
|------|----------------|
| `project-summary.md` | What the app does, who it's for, key features (~1 page) |
| `services-list.md` | Every cloud service/tool with a one-line description |
| `supabase-schema.sql` | Export from Supabase: Table Editor → SQL Editor → Export |
| `architecture-notes.md` | How frontend connects to backend (optional but helpful) |

</div>

<v-click>

<div style="background: #e8f0fe; border-left: 4px solid #12284c; padding: 1em; border-radius: 8px; margin-top: 1.5em;">

**Start this tonight.** The better your context folder, the better Run 2 will be. The comparison between Run 1 and Run 2 is what your reflection is graded on.

</div>

</v-click>

---

# Alternative Stack Coordination

<div style="margin-top: 0.5em; font-size: 0.9em;">

Each team picks a **different** alternative. No duplicates — the class learns more that way.

</div>

<div style="margin-top: 1em; font-size: 0.85em;">

| # | Alternative | What It Replaces | Key Research Question |
|---|------------|-----------------|----------------------|
| 1 | **Firebase** (Google) | Supabase | Google ecosystem lock-in vs. open source |
| 2 | **Cursor + Vercel** | Lovable | Code-first vs. AI-builder approach |
| 3 | **Bolt.new** | Lovable | Alternative AI builder — what's different? |
| 4 | **Replit** | Full stack | IDE + hosting + DB in one — simpler or riskier? |
| 5 | **AWS Amplify** | Enterprise PaaS | Enterprise-grade vs. startup-friendly |
| 6 | **Netlify + Neon** | Hosting + DB | Mix-and-match vs. integrated platform |
| 7 | **Railway + PlanetScale** | Backend stack | Alternative backend — cost at scale? |

</div>

<v-click>

<div style="text-align: center; margin-top: 1em; font-weight: bold; color: #ff5f05;">

Commit to a choice before you leave today. We'll log them on the board.

</div>

</v-click>

---

# Deliverables

<div style="margin-top: 1em;">

<div style="background: #fff0e6; border-left: 4px solid #ff5f05; padding: 1.2em; border-radius: 8px;">

### Case 2: Migration Planner — Due Wednesday, April 1, 11:59 PM (20 pts)

**Team post:** GitHub Pages URL + alternative choice + prompt used + iteration summary

**Individual replies:** Each team member posts a ~250 word reflection on Run 1 vs. Run 2

</div>

</div>

<div style="margin-top: 1.5em; font-size: 1.05em; line-height: 1.8;">

**Tonight through Wednesday:**
1. Build your `my-stack-analysis/` context folder
2. Run the context experiment (Run 1, then Run 2 — same prompt)
3. Iterate on Run 2 to build the full migration planner
4. Deploy to GitHub Pages
5. Write your individual reflection

</div>

---

# Thursday Preview

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 2em; margin-top: 1.5em;">

<div>

### Session 2 (Thu Apr 2)

- **7 team presentations** (5 min each, strict)
- 3 min: walk through your planner + key finding
- 2 min: Q&A from class
- Full-class discussion on patterns
- **Checkpoint 4 preview**

</div>

<div style="background: #e8f0fe; border-left: 4px solid #12284c; padding: 1.5em; border-radius: 8px;">

### Why This Matters

Your migration planner is the **starting point** for Checkpoint 4 (Week 11, 60 pts).

You already understand your architecture. Next week adds: security review, data integration, controls assessment.

**Keep your context folder. You'll build on it.**

</div>

</div>

---
layout: center
---

# The Big Question

<div style="font-size: 1.3em; margin-top: 1em;">

If a potential investor asked you to walk through your technical architecture — what cloud services you use, what they cost at scale, where you're locked in —

</div>

<v-click>

<div style="font-size: 1.5em; font-weight: bold; color: #ff5f05; margin-top: 1em;">

could you answer?

</div>

<div style="font-size: 1.1em; margin-top: 1em; color: #888;">

After this week, you can.

</div>

</v-click>
