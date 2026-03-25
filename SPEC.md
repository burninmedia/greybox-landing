# Agent Audit Trail — Product Specification

## Product Name & Domain

**Recommendation:** **GreyBox** (greybox.ai or greybox.io)

**Why GreyBox:** Inverts "black box" into something honest and transparent — operators can see inside. Short, memorable, meaningful. Avoids the genericness of "audit" or "trace" while immediately communicating what the product does.

**Alternatives considered:**
- `AgentLens` — clear but less punchy
- `DecideHQ` — decision-focused but less obviously about AI
- `TraceAgent` — descriptive but awkward
- `Auri` (like aurora/light) — too abstract
- `Hedron` — interesting but meaningless

**Domain:** greybox.ai or greybox.io — both likely available.

---

## What It Is

GreyBox is an **audit layer for AI agents** — a service that logs, explains, and visualizes what agents actually did and why. Operators and other agents can query the trail, understand decisions, and verify behavior.

**Tagline:** *See inside the box.*

---

## The Problem

AI agents are increasingly handling high-stakes operations:
- Moving money
- Managing logistics
- Handling customer relationships
- Making medical, legal, financial decisions

Right now, when an agent acts, operators see the outcome — not the reasoning. If something goes wrong (or right), there's no native way to answer: *what did it actually do, and why did it decide that?*

Agents are black boxes. As they handle real stakes, that opacity becomes unacceptable.

---

## The Service

**GreyBox** provides three things:

1. **Decision Logging** — Every agent action is captured with timestamp, inputs, outputs, and context.
2. **Explanation Layer** — Each decision is annotated with why the agent made that choice (chain-of-thought, tool calls, context used).
3. **Visualization Dashboard** — Operators see a timeline of agent behavior, decision trees, and audit trails at a glance.

**Output example (mockup):**
```
[Agent: OrderBot-3] Action: APPROVE_RETURN
  Timestamp: 2026-03-21 03:42:17 ET
  Reasoning: Customer tier=gold, item age=12 days (<30-day policy), 
             no prior returns in 90 days. Threshold met.
  Confidence: 0.94
  Context: order #8821, customer #4419, policy v2.1
  ─────────────────────────────────────────────
  Tool calls: get_customer_tier(), check_return_window(), 
              lookup_policy(order_type=return)
```

---

## Website Structure

**Single page. Sections:**

1. **Hero** — Headline + tagline. "Agents are black boxes. We fix that."
2. **Problem** — The stakes are real. Black boxes are not acceptable.
3. **Solution** — What GreyBox does (logging, explanation, visualization).
4. **Demo** — Mockup of the audit trail output (styled code block / terminal).
5. **How It Works** — 3-step visual: Integrate → Capture → Query.
6. **CTA / Waitlist** — Email signup form for early access.

---

## Tech Stack

- Pure HTML + CSS + vanilla JS
- No backend required (static site)
- Hosted on GitHub Pages (or similar static host)
- Netlify drop as fallback

---

## Cron Monitoring

- `curl -s -o /dev/null -w "%{http_code}" https://[site-url]` daily
- Alert if HTTP ≠ 200
- Report to Stephen via Telegram

---

## Status

- [x] SPEC.md written (this file)
- [x] Stephen approves domain name ✅ (greybox.fyi, Mar 21 2026)
- [x] Website built (index.html)
- [ ] Hosted live (DNS pointing)
- [x] Cron job configured (8AM/12PM/4PM/8PM ET)
