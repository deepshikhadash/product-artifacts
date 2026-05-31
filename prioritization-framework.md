# Prioritization Framework
## RICE + MoSCoW Applied to a Compliance Product Backlog
### Product Artifacts Library · Deepshikha Dash

Prioritization is where PM judgment shows up most clearly. This document demonstrates two complementary frameworks — RICE for quantitative scoring, MoSCoW for stakeholder communication — applied to a realistic compliance-technology product backlog.

---

## Framework 1: RICE Scoring

**Formula:** `(Reach × Impact × Confidence) ÷ Effort = RICE Score`

| Variable | Definition | Scale |
|---|---|---|
| **Reach** | How many users affected per quarter? | 1–10 (10 = all users) |
| **Impact** | How much does it move a key metric? | 1 = minimal · 3 = moderate · 7 = high · 10 = massive |
| **Confidence** | How certain are we in the estimates? | 1–10 (10 = very high, backed by data) |
| **Effort** | Person-weeks of engineering + design work | Raw number (higher = more costly) |

---

## Applied Example: GrantFlow Compliance Platform Backlog

**Context:** Q3 planning session. 8 features in backlog. Engineering capacity = 40 person-weeks. Goal: maximize compliance accuracy and admin efficiency.

| Feature | Reach | Impact | Confidence | Effort (wks) | RICE Score | Priority |
|---|---|---|---|---|---|---|
| Real-time transaction eligibility enforcement | 10 | 10 | 9 | 6 | **150** | 🔴 P0 |
| Bulk fund allocation via CSV upload | 10 | 9 | 9 | 4 | **202** | 🔴 P0 |
| Automated monthly compliance report | 8 | 10 | 8 | 5 | **128** | 🔴 P0 |
| Recipient balance & transaction history | 10 | 8 | 9 | 4 | **180** | 🔴 P0 |
| Flagged transaction review queue | 7 | 9 | 8 | 4 | **126** | 🟡 P1 |
| Audit trail export (CSV) | 5 | 9 | 9 | 3 | **135** | 🟡 P1 |
| Individual fund adjustment (with 2nd approval) | 6 | 7 | 8 | 3 | **112** | 🟡 P1 |
| Partial eligibility cart handling | 6 | 7 | 7 | 5 | **59** | 🟢 P2 |

**Q3 Recommendation:**  
Ship P0 features (est. 19 weeks total effort) + Audit trail export (3 weeks) = **22 weeks**.  
Reserve 18 weeks for P1 sprint work + bug buffer.  
Partial eligibility handling deferred to Q4 — high complexity, lower urgency.

---

## Framework 2: MoSCoW

RICE gives you a score. MoSCoW gives you a conversation. Use it to align stakeholders on what "launch" actually means.

| Category | Definition | When to Use |
|---|---|---|
| **Must Have** | Launch-blocking. Without this, the product doesn't work or creates compliance/legal risk | Core eligibility enforcement, fund disbursement, audit trail |
| **Should Have** | High value, expected by users, but product ships without it | Compliance report automation, admin dashboard |
| **Could Have** | Nice to have — improves experience but low urgency | Mobile push notifications, bulk export scheduling |
| **Won't Have (this release)** | Explicitly out of scope — important to name to prevent scope creep | ML fraud detection, multi-language UI, ERP integrations |

### GrantFlow v1 MoSCoW Map

**Must Have (v1):**
- Transaction eligibility enforcement at point of purchase
- Bulk fund allocation
- Recipient wallet with balance visibility
- Basic audit trail logging
- Admin compliance dashboard (read-only)

**Should Have (v1):**
- Automated monthly report generation
- Flagged transaction review queue
- Individual fund adjustment with approval workflow

**Could Have (v1):**
- Audit trail export in CSV
- Email notifications for declined transactions
- Mobile-responsive recipient interface

**Won't Have (v1 — explicitly deferred):**
- Spanish/French localization
- Recipient dispute workflow
- State ERP API integrations
- ML-based anomaly detection

---

## When to Use Each Framework

| Scenario | Use |
|---|---|
| Internal engineering capacity planning | RICE — quantitative, helps compare apples to oranges |
| Stakeholder alignment meeting (exec, CSM, sales) | MoSCoW — communicates priorities in plain language |
| Deciding between two similarly-scored features | Add a tiebreaker: strategic alignment score (does it serve our Q3 OKR directly?) |
| Mid-sprint descope decision | MoSCoW — quick call: is this a Must or Should? If Should, it can move |
| Annual roadmap planning | RICE first, then MoSCoW to communicate output |

---

## PM Principles Behind This Framework

1. **Prioritization is a decision, not a consensus.** Frameworks give you structure; you make the call.
2. **Effort is the most-underestimated variable.** Always sanity-check effort scores with the engineering lead before finalizing.
3. **Confidence scores keep you honest.** A feature with a RICE score of 200 but confidence of 3 is a guess, not a priority.
4. **Name the Won't Haves explicitly.** Unstated deferrals become scope creep. Put them in writing.
5. **Re-score every quarter.** Priorities shift. A P2 from Q2 can be a P0 by Q4 if customer feedback changes.

---

*Deepshikha Dash · Product Manager · Austin, TX*
