---
theme: default
title: 'Week 11: Security & Controls'
info: |
  BADM 350 — IT for Networked Organizations
  Unit D: Enterprise Enablement
author: Vishal Sachdev
transition: slide-left
colorSchema: light
mdc: true
navigator: false
---

# Security & Controls

## Week 11 · Unit D: Enterprise Enablement

<div style="margin-top: 2em; color: #888;">

BADM 350 — Session 1

April 7, 2026

[Canvas: Week 11 Overview](https://canvas.illinois.edu/courses/68238/pages/week-11-overview-security-and-controls)

</div>

---
layout: center
---

# Opening: Have You Been Pwned?

<div style="font-size: 1.2em; margin-top: 1em;">

Go to **haveibeenpwned.com** right now.

Type in your email address.

</div>

<v-click>

<div style="margin-top: 2em; background: #fef0f0; border-left: 4px solid #e57373; padding: 1.2em; border-radius: 8px;">

How many breaches? What data was exposed? Names? Passwords? Phone numbers?

**Raise your hand if you had more than 5 breaches.**

</div>

</v-click>

<v-click>

<div style="margin-top: 1em; font-size: 0.9em; color: #888;">

The NYT used to run an interactive quiz like this — it's gone now, but the breaches aren't. This is your data, on someone else's server, exposed because someone didn't do what we're learning today.

</div>

</v-click>

---

# Today's Roadmap

<div style="font-size: 1.1em; line-height: 2;">

| Time | Activity |
|------|----------|
| 0–5 | Notes collection (two-pass) |
| 5–15 | Opening: Have I Been Pwned? |
| 15–35 | The CIA Triad — the security framework |
| 35–50 | Breach cases: Target & Equifax |
| 50–70 | Audit Your App — teams use CIA checklist |
| 70–75 | Checkpoint 4 preview + Thursday setup |

</div>

---
layout: section
---

# Part 1
## The CIA Triad

---

# The Framework Every Security Pro Uses

<div style="display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 1.5em; margin-top: 1.5em;">

<div style="background: #e8f0fe; border-left: 4px solid #12284c; padding: 1.5em; border-radius: 8px;">

### Confidentiality

**Who can see it?**

Only authorized people should access sensitive data.

<div style="font-size: 0.85em; color: #888; margin-top: 0.5em;">Breach example: Equifax — 147M people's SSNs exposed</div>

</div>

<div style="background: #fff0e6; border-left: 4px solid #ff5f05; padding: 1.5em; border-radius: 8px;">

### Integrity

**Can it be tampered with?**

Data should be accurate and unmodified by unauthorized users.

<div style="font-size: 0.85em; color: #888; margin-top: 0.5em;">Breach example: SolarWinds — attackers modified software updates</div>

</div>

<div style="background: #eaf5ea; border-left: 4px solid #4caf50; padding: 1.5em; border-radius: 8px;">

### Availability

**Can you access it when you need it?**

Systems should be accessible and functional when needed.

<div style="font-size: 0.85em; color: #888; margin-top: 0.5em;">Breach example: Colonial Pipeline — ransomware shut down fuel supply for days</div>

</div>

</div>

---

# CIA Is a Tradeoff

<div style="margin-top: 1em; font-size: 1.05em; line-height: 1.8;">

You can't maximize all three at once. Security is about **proportionate trade-offs**.

</div>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 2em; margin-top: 1.5em;">

<div style="background: #f5f5f5; border: 1px solid #ddd; padding: 1.5em; border-radius: 8px;">

### More Confidentiality = Less Availability

Lock everything down → harder for real users to access.

*MFA on every action? Secure, but users abandon your app.*

</div>

<div style="background: #f5f5f5; border: 1px solid #ddd; padding: 1.5em; border-radius: 8px;">

### More Availability = Less Confidentiality

Make everything easy to access → easier for attackers too.

*No login required? Available, but anyone sees everything.*

</div>

</div>

<v-click>

<div style="text-align: center; margin-top: 1.5em; font-size: 1.15em; font-weight: bold; color: #ff5f05;">

The goal isn't perfect security. It's proportionate security for your risk level.

</div>

</v-click>

---

# Think-Pair-Share: Your Project's CIA

<div style="margin-top: 1em; font-size: 1.1em;">

**1 minute alone, then discuss with your team:**

</div>

<div style="display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 1.5em; margin-top: 1.5em;">

<div style="background: #e8f0fe; border-left: 4px solid #12284c; padding: 1.2em; border-radius: 8px;">

### Confidentiality

What's the most sensitive data in your app? Who should NOT see it?

</div>

<div style="background: #fff0e6; border-left: 4px solid #ff5f05; padding: 1.2em; border-radius: 8px;">

### Integrity

Could someone modify data they shouldn't? What would break?

</div>

<div style="background: #eaf5ea; border-left: 4px solid #4caf50; padding: 1.2em; border-radius: 8px;">

### Availability

What's your single point of failure? What if Supabase goes down?

</div>

</div>

<v-click>

<div style="margin-top: 1.5em; text-align: center; font-size: 1.1em; color: #888;">

We'll hear 3-4 teams share. Which CIA dimension is your biggest risk?

</div>

</v-click>

---
layout: section
---

# Part 2
## When It Goes Wrong

---

# The Target Breach (2013)

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 2em; margin-top: 1.5em;">

<div>

### What Happened

- **40 million** credit/debit card numbers stolen
- **70 million** customer records exposed (names, addresses, emails, phone numbers)
- Attackers got in through an **HVAC vendor** — Fazio Mechanical Services
- Vendor had network access for billing and contract submissions
- Malware installed on point-of-sale terminals

</div>

<div style="background: #fef0f0; border-left: 4px solid #e57373; padding: 1.5em; border-radius: 8px;">

### CIA Analysis

**Confidentiality** — Card data exposed to unauthorized actors

**Integrity** — Malware on POS systems modified how data was processed

**Availability** — Systems stayed up (attackers wanted to stay hidden)

<div style="margin-top: 1em; font-weight: bold; color: #e57373;">

Cost: $162 million. CEO and CIO both fired.

</div>

</div>

</div>

<v-click>

<div style="background: #fff0e6; border-left: 4px solid #ff5f05; padding: 1em; border-radius: 8px; margin-top: 1em;">

**Key lesson:** Your weakest link isn't your code — it's who has access to your network. An HVAC company took down the 8th largest retailer in the US.

</div>

</v-click>

---

# The Equifax Breach (2017)

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 2em; margin-top: 1.5em;">

<div>

### What Happened

- **147 million** Americans' personal data exposed
- SSNs, birth dates, addresses, driver's license numbers
- Root cause: **unpatched Apache Struts vulnerability** (CVE-2017-5638)
- Patch was available **2 months** before the breach
- Equifax knew about the vulnerability and failed to act

</div>

<div style="background: #fef0f0; border-left: 4px solid #e57373; padding: 1.5em; border-radius: 8px;">

### CIA Analysis

**Confidentiality** — The most sensitive PII possible: SSNs

**Integrity** — Attackers had access for **76 days** — could they have modified records?

**Availability** — The credit reporting system was compromised at its core

<div style="margin-top: 1em; font-weight: bold; color: #e57373;">

Cost: $700 million settlement. CEO resigned.

</div>

</div>

</div>

<v-click>

<div style="background: #fff0e6; border-left: 4px solid #ff5f05; padding: 1em; border-radius: 8px; margin-top: 1em;">

**Key lesson:** The patch existed. They didn't apply it. Most breaches aren't sophisticated zero-days — they're known vulnerabilities that nobody fixed.

</div>

</v-click>

---

# Discussion: What Would You Have Done?

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 2em; margin-top: 1.5em;">

<div style="background: #e8f0fe; border-left: 4px solid #12284c; padding: 1.5em; border-radius: 8px;">

### Target

1. Should an HVAC vendor have network access to payment systems?
2. What's the business case for network segmentation?
3. Target's security system **flagged the intrusion** but nobody acted. Why?

</div>

<div style="background: #fff0e6; border-left: 4px solid #ff5f05; padding: 1.5em; border-radius: 8px;">

### Equifax

1. Who is responsible when a patch exists but isn't applied?
2. Equifax's CEO blamed **one IT employee** for not patching. Fair?
3. Should a company that stores 800M people's data have different security standards?

</div>

</div>

<v-click>

<div style="margin-top: 1.5em; text-align: center; font-size: 1.15em; font-weight: bold; color: #12284c;">

Both breaches were preventable. Both cost hundreds of millions. Both ended careers.

</div>

</v-click>

---

# Common Attack Vectors (Ch 21)

<div style="margin-top: 1em; font-size: 0.95em;">

| Attack | How It Works | Real Example | Your Project? |
|--------|-------------|--------------|---------------|
| **Phishing** | Fake email tricks user into revealing credentials | Google/Facebook scammed for $100M via fake invoices | Could someone fake a password reset email? |
| **Ransomware** | Encrypt data, demand payment | Colonial Pipeline (2021) — $4.4M ransom, fuel shortage | What if your database gets encrypted? |
| **SQL Injection** | Malicious input manipulates database queries | Heartland Payment — 130M cards via SQL injection | Do you validate user input? |
| **DDoS** | Overwhelm servers with traffic | GitHub hit with 1.3 Tbps DDoS (2018) | What if your hosting goes down? |
| **Credential Stuffing** | Reuse leaked passwords from other breaches | Disney+ hacked hours after launch (reused passwords) | Do your users reuse passwords? |

</div>

<v-click>

<div style="background: #e8f0fe; border-left: 4px solid #12284c; padding: 1em; border-radius: 8px; margin-top: 1em;">

**Thursday preview:** We'll add **prompt injection** to this list — what happens when attackers target the AI in your app.

</div>

</v-click>

---

# Shared Responsibility — From Last Week

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 2em; margin-top: 1.5em;">

<div style="background: #fff0e6; border-left: 4px solid #ff5f05; padding: 1.5em; border-radius: 8px;">

### Your Responsibility

- **RLS policies** (who sees what data)
- **Input validation** (reject bad data)
- **Auth configuration** (login, protected routes)
- **API key management** (don't expose secrets)
- **Application logic** (business rules)

</div>

<div style="background: #e8f0fe; border-left: 4px solid #12284c; padding: 1.5em; border-radius: 8px;">

### Supabase's Responsibility

- Physical server security
- Network infrastructure
- Database engine patches
- Encryption at rest
- Backup infrastructure
- Uptime guarantees

</div>

</div>

<v-click>

<div style="margin-top: 1.5em; text-align: center; font-size: 1.15em; font-weight: bold; color: #ff5f05;">

If Supabase has a network breach = their fault.

If you forgot to enable RLS and anyone can read your data = YOUR fault.

</div>

</v-click>

---
layout: section
---

# Part 3
## Audit Your App

---

# The CIA Checklist

<div style="margin-top: 0.5em; font-size: 0.95em;">

Open the **CIA Triad Audit Checklist** on Canvas. Work through it with your team.

</div>

<div style="display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 1.5em; margin-top: 1em; font-size: 0.85em;">

<div style="background: #e8f0fe; border-left: 4px solid #12284c; padding: 1.2em; border-radius: 8px;">

### Confidentiality

- RLS policies on every table?
- Can logged-out users see data?
- API keys visible in client code?
- Can User A see User B's data?
- Sensitive data encrypted?

</div>

<div style="background: #fff0e6; border-left: 4px solid #ff5f05; padding: 1.2em; border-radius: 8px;">

### Integrity

- Can someone submit malicious input?
- Can users modify others' data?
- Forms validated before database write?
- Trusting client-side data that should be server-validated?

</div>

<div style="background: #eaf5ea; border-left: 4px solid #4caf50; padding: 1.2em; border-radius: 8px;">

### Availability

- What happens if Supabase goes down?
- Error handling for failed API calls?
- Rate limiting on login attempts?
- Backup strategy for user data?

</div>

</div>

<v-click>

<div style="background: #fef0f0; border: 2px solid #e57373; padding: 1em; border-radius: 8px; margin-top: 1em; text-align: center;">

**Goal: Find 3 real vulnerabilities. You'll fix them for Checkpoint 4.**

</div>

</v-click>

---

# Live Demo: How to Check RLS

<div style="margin-top: 1em; font-size: 1.05em;">

**The #1 vulnerability in this class: RLS is disabled.**

</div>

<div style="margin-top: 1.5em; font-size: 0.95em; line-height: 1.8;">

1. Open **Supabase Dashboard** → Authentication → Policies
2. Every table should have at least one policy
3. If RLS is **DISABLED** → anyone with your anon key can read/write everything

</div>

<v-click>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 2em; margin-top: 1.5em;">

<div style="background: #fef0f0; border-left: 4px solid #e57373; padding: 1.2em; border-radius: 8px;">

### Before (Vulnerable)

RLS disabled. Any user with the anon key (visible in your client code) can query any row in any table.

This is your **Equifax moment** — the vulnerability is known, the fix is available.

</div>

<div style="background: #eaf5ea; border-left: 4px solid #4caf50; padding: 1.2em; border-radius: 8px;">

### After (Hardened)

RLS enabled. Policy: `auth.uid() = user_id`

Now users can only read/write their own rows. The anon key is still public, but it doesn't matter.

</div>

</div>

</v-click>

---

# Team Activity: 20 Minutes

<div style="margin-top: 1em; font-size: 1.1em;">

**Open your app. Open the CIA checklist. Work through it together.**

</div>

<div style="margin-top: 1.5em; font-size: 1em; line-height: 1.8;">

1. **Check Supabase** → Authentication → Policies (Confidentiality)
2. **Open DevTools** → Network tab → use your app → look at API calls (Integrity)
3. **Test error states** → turn off WiFi, submit empty forms (Availability)
4. **Write down 3 vulnerabilities** you find — CIA classification for each

</div>

<v-click>

<div style="background: #e8f0fe; border-left: 4px solid #12284c; padding: 1em; border-radius: 8px; margin-top: 1.5em;">

**I'll walk around. Flag me if you're stuck or if you found something interesting.**

If you don't find any vulnerabilities, you're not looking hard enough. Every app in this room has them.

</div>

</v-click>

---
layout: section
---

# Checkpoint 4 + Thursday

---

# Checkpoint 4: Make It Real + Make It Secure

<div style="display: grid; grid-template-columns: 3fr 2fr; gap: 2em; margin-top: 1.5em;">

<div style="font-size: 0.9em;">

| Component | Points |
|-----------|--------|
| Working core user flow | 15 |
| Functioning database (3+ tables, real CRUD) | 15 |
| Authentication (login, protected routes) | 10 |
| User testing (3 people, documented) | 10 |
| **Security hardening (Find 3, Fix 3)** | **10** |
| **Total** | **55** (+5 EC migration) |

</div>

<div style="background: #fef0f0; border-left: 4px solid #e57373; padding: 1.5em; border-radius: 8px;">

### Due Thursday, April 9

**12:30 PM — before class**

Live URL + PDF report (3-5 pages)

One submission per team.

**The 3 vulnerabilities you find today become your security hardening section.**

</div>

</div>

<v-click>

<div style="background: #fff0e6; border-left: 4px solid #ff5f05; padding: 1em; border-radius: 8px; margin-top: 1em;">

**Peer review (5 pts)** is a separate discussion — due Sunday, April 12.

</div>

</v-click>

---

# Thursday Preview: Prompt Injection + Live Reviews

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 2em; margin-top: 1.5em;">

<div style="background: #f5f5f5; border: 1px solid #ddd; padding: 1.5em; border-radius: 8px;">

### First 15 Minutes

Live **prompt injection demo** — what happens when someone attacks the AI in your app.

- Direct injection: overriding system prompts
- Indirect injection: hidden instructions in content
- Why this matters for YOUR apps

</div>

<div style="background: #fff0e6; border-left: 4px solid #ff5f05; padding: 1.5em; border-radius: 8px;">

### Then: Live App Reviews

I'll pick teams at random, open your app on the projector, and test it:

- Does the core flow work?
- Can I break auth?
- Is RLS on?
- What happens with bad input?

**Class watches and learns from each review.**

</div>

</div>

<v-click>

<div style="margin-top: 1.5em; text-align: center; font-size: 1.15em; font-weight: bold; color: #12284c;">

Submit Checkpoint 4 before class starts Thursday. Every team should be ready.

</div>

</v-click>

---
layout: center
---

# The Big Question

<div style="font-size: 1.3em; margin-top: 1em;">

Every app in this room stores user data on someone else's servers.

</div>

<v-click>

<div style="font-size: 1.2em; margin-top: 1em;">

If a user asks you: *"Is my data safe in your app?"*

</div>

</v-click>

<v-click>

<div style="font-size: 1.5em; font-weight: bold; color: #ff5f05; margin-top: 1em;">

What's your answer?

</div>

<div style="font-size: 1.1em; margin-top: 1em; color: #888;">

After today, you should know where you're vulnerable — and after Thursday, you'll have fixed it.

</div>

</v-click>
