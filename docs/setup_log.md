---
title: "Andromeda Life Insurance Pilot — Setup Checklist"
description: "Step-by-step setup process to build the Andromeda-aligned pilot environment before launching campaigns."
author: "Dan Elkins"
date: "2025-10-16"
---

# 🧰 Andromeda Life Insurance Pilot — Setup Checklist

A practical, ground-up list of everything required to build and verify the system before first launch.

---

## 🧱 1. Clean Environment Setup

- [ ] Create a **dedicated Meta Business Portfolio** for the pilot  
- [ ] Create a **new Ad Account** (assign payment method)  
- [ ] Add yourself as **Admin** — no shared access from other portfolios  
- [ ] Enable **Special Ad Category: Credit / Employment / Housing / Social Issues** (Insurance applies here)  
- [ ] Verify your **business domain** (for Aggregated Events Measurement)  
- [ ] Confirm **time zone + currency** settings in Ad Account  
- [ ] Note all IDs (Business, Ad Account, Pixel, Dataset) inside `/logs/setup_log.md`

**DoD:** Isolated ad account + verified domain + correct permissions.

---

## 📊 2. Pixel & Dataset Configuration

- [ ] Create a **fresh Pixel** (unique to this pilot)  
- [ ] Create a **Dataset** (under Events Manager → Data Sources → Datasets)  
- [ ] Link Pixel + Dataset to the Ad Account  
- [ ] Define three events:
  - `ViewContent` → user starts or engages with quiz  
  - `Lead` → form or quiz completion  
  - `Schedule` → appointment booked  
- [ ] Rank events under **Aggregated Event Measurement (AEM):**
  1. Schedule  
  2. Lead  
  3. ViewContent  

**DoD:** Pixel and Dataset appear active with correct AEM order.

---

## 🧩 3. Funnel + CRM + Automations

- [ ] Build the **Quiz Funnel** (or VSL variant)
  - Quiz Page / Lead Capture Page / TY + Booking Page  
- [ ] Install Pixel on all pages (use Meta Pixel Helper to confirm)  
- [ ] Pass UTMs and `fbclid` through hidden fields into CRM  
- [ ] Connect **Booking App** (Calendly / GHL / ScheduleOnce)  
- [ ] Create **CRM Pipeline:**  
  New Lead → Qualified → Booked → Showed → Closed  
- [ ] Build **Automations:**  
  - Immediate SMS + Email confirmation  
  - Calendar reminders + no-show recovery  
  - Post-call follow-up  

**DoD:** Submitting a test lead fires automations and creates a booked test appointment.

---

## 🔌 4. Conversion API (CAPI) Integration

Choose the method that fits your workflow:
- [ ] Zapier App (simplest)
- [ ] Meta’s CAPI Gateway (managed)
- [ ] Manual POST/webhook via server (advanced control)

**Send these events server-side:**
- `ViewContent` — quiz engagement  
- `Lead` — completed form  
- `Schedule` — appointment booked  

**Implementation Details**
- [ ] Use the same **Event ID** for browser + server events  
- [ ] Include **match keys**: email, phone, IP, user agent (SHA256 hashed)  
- [ ] Set `action_source` to `website` or `system_generated`  
- [ ] Validate events using **Test Events Tool**  
- [ ] Target **Event Match Quality (EMQ)** score: 6–8+  
- [ ] Document test results + EMQ scores in `/logs/setup_log.md`

**DoD:** Each event visible twice (browser + server) with green “deduped” check.

---

## 🧪 5. Data Path QA

- [ ] Pixel Helper shows `ViewContent` firing correctly  
- [ ] Submitting a test lead triggers `Lead` (pixel + server)  
- [ ] Booking a test appointment triggers `Schedule` (pixel + server)  
- [ ] Events appear in **Test Events** tab with matching IDs  
- [ ] AEM diagnostics show “Active” — no config errors  
- [ ] Take screenshots of each verified event flow for logs  

**DoD:** All three events firing cleanly and deduped with verified lineage.

---

## 🗂 Repo Documentation (as you go)

- [ ] `/docs/scope.md` — pilot purpose + success metrics  
- [ ] `/docs/setup_checklist.md` — (this file)  
- [ ] `/docs/launch_checklist.md` — pre-launch + post-launch flow  
- [ ] `/logs/setup_log.md` — screenshots, event IDs, notes  
- [ ] `/tracking/event_specs.md` — payload + CAPI structure  
- [ ] `/creative_tests/v1_*` — creative sets  

**DoD:** everything documented; reproducible by any team member.

---

## ✅ Final Readiness Review

Confirm the following before campaign launch:
- [ ] Clean Pixel + Dataset (no shared assets)
- [ ] CRM + booking flow tested end-to-end
- [ ] CAPI events firing + deduped
- [ ] Domain verified + AEM priority correct
- [ ] Funnel and automations fully functional

Once these are checked off, move into the **Launch Checklist** to deploy your first campaign.
