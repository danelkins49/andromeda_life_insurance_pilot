---
title: "Andromeda Life Insurance Pilot — Scope"
description: "Defining the scope and objectives for the Meta Andromeda-aligned life insurance advertising pilot."
author: "Dan Elkins"
date: "2025-10-16"
---

# 🚀 Andromeda Life Insurance Pilot — Scope

## 🎯 Objective

Prove a repeatable **advertising and data system** aligned with Meta’s **Andromeda retrieval engine** that stabilizes performance, increases lead quality, and reduces daily media buying time.

The goal is to demonstrate that when a clean, self-contained advertising ecosystem is built and optimized correctly, it produces **consistent leads, predictable results, and higher sales conversion** without constant manual intervention..

---

## 🧩 Core Problems to Solve

1. **Excessive daily ad management**
   - Too much firefighting in ad accounts and constant manual resets.

2. **Inconsistent campaign performance**
   - Campaigns fatigue fast; no shared learning between launches.

3. **Inconsistent lead quality**
   - Leads generated are often unqualified or low-intent.

4. **Low appointment show rates**
   - Disconnect between ad message and post-lead experience.

5. **Unstable business model for agents**
   - Reliance on unpredictable lead gen, leading to burnout and distrust in the process.

6. **Lack of clean, individualized data**
   - Shared “super pixels” across portfolios muddy signal quality.  
   - Without dedicated pixels per agent, Meta’s AI can’t accurately learn purchase behavior or audience patterns.  
   - The absence of clear data lineage prevents meaningful optimization and event feedback.

---

## 🧠 Strategic Hypothesis

> If Meta’s Andromeda system is given a clean dataset (via fresh pixel + CAPI) and enough creative diversity to learn, it will optimize towards **higher-quality conversions** and stabilize ad performance with minimal manual intervention.

This pilot tests whether that hypothesis can hold true in the **Special Ad Category (Insurance)** — where traditional targeting is restricted.

---

## ⚙️ Core System Components

### 1. Funnel Layer
- **Meta Ads → Funnel → CRM → Back-End Automations**
- Captures zero-party data for personalization and segmentation.
- Bridges paid traffic from Meta directly into the quiz or VSL funnel.
- Pushes leads into the CRM with tags, triggers, and automated follow-ups.
- Includes back-end automations for appointment scheduling, nurture sequences, and sales tracking.
- Tests multiple awareness-level angles to identify highest-converting entry points.


### 2. Tracking Layer
- **Fresh Pixel + CAPI Integration**
- One pixel per agent for clean data ownership.
- Send `Lead`, `Qualified Lead`, and `Sale` events server-side.
- Maintain isolated data lineage — no shared pixels across portfolios.

### 3. Creative Layer
- **Andromeda-Adaptive Creative Structure**
- Minimum 5 creative concepts per campaign:
  - UGC / Testimonial
  - Demonstrative / Educational
  - Benefit-Focused Static
  - Objection-Overcoming Static
  - Value or Identity Hook
- Built to engage multiple user types and awareness levels.

### 4. Optimization Layer
- Focused on:
  - Event validation (pixel vs. CAPI)
  - Conversion feedback (CRM → Meta)
  - Audience refinement through system learning
  - Reducing human media-buying intervention

### 5. Feedback Layer
- Manual sale validation → CRM → Offline Conversion API postback
- Continuous feedback loop completes the learning cycle.

---

## 📈 Success Metrics

| Metric | Goal | Measurement Method |
|--------|------|--------------------|
| Ad management time | ↓ 50% | Compare weekly time spent vs. baseline |
| CPL consistency | ±15% variance | 14-day rolling average |
| Lead-to-appointment rate | ↑ 20% | CRM + booking data |
| Appointment show rate | ↑ 15% | CRM status tracking |
| Sale rate from self-gen leads | ↑ 10–20% | Manual validation + CAPI event |
| Data cleanliness | 100% isolated per agent | Pixel → Dataset → Event lineage verification |

---

## 🧭 Outcome

Establish a **validated blueprint** for Meta advertising that:
- Leverages Andromeda’s machine learning for predictable performance.  
- Produces clean, ownable data streams for ongoing optimization.  
- Restores agent confidence in organic, self-generated lead systems.  
- Allows each agent’s pixel to learn uniquely, building compounding intelligence over time.

---

## 🗂 Versioning

- **Pilot Version:** v1.0 (2025-10-16)  
- **Next Review:** After first 14-day campaign cycle  
- **Maintained by:** Dan Elkins
