# Metrics Framework
## Success Measurement for a Public-Sector Compliance SaaS Product
### Product Artifacts Library · Deepshikha Dash

Good metrics design happens before a feature ships, not after. This framework demonstrates how to define, layer, and track product success for a compliance-heavy, public-sector SaaS product — the context I work in most.

---

## The Three-Layer Model

```
LAYER 1: BUSINESS METRICS        ← Are we growing and retaining?
         (lagging, quarterly)

LAYER 2: PRODUCT METRICS         ← Are users getting value?
         (lagging, monthly)

LAYER 3: LEADING INDICATORS      ← Are we on track? (catch issues early)
         (leading, weekly/daily)
```

Never report only business metrics — by the time they move, it's too late to course-correct. Leading indicators are your early warning system.

---

## Applied Framework: GrantFlow Compliance Platform

### Layer 1 — Business Metrics (Quarterly Review)

| Metric | Definition | Target | Data Source |
|---|---|---|---|
| Agency renewal rate | % of agencies that renew contract at end of term | ≥ 90% | CRM / Finance |
| Net new agencies | New agency contracts signed per quarter | +15% QoQ | CRM |
| Revenue per agency | ARR ÷ active agencies | Trending up | Finance |
| NPS — Agency Admins | Net Promoter Score from admin survey | ≥ 45 | Quarterly survey |
| NPS — Recipients | Net Promoter Score from recipient survey | ≥ 40 | Quarterly survey |

---

### Layer 2 — Product Metrics (Monthly Review)

#### Acquisition & Activation
| Metric | Definition | Target |
|---|---|---|
| New agency activation time | Days from contract sign to first fund disbursement | ≤ 5 days |
| Recipient wallet activation rate | % of allocated recipients who activate within 7 days | ≥ 75% |
| Onboarding completion rate | % of new admins who complete setup flow without support ticket | ≥ 85% |

#### Engagement
| Metric | Definition | Target |
|---|---|---|
| Admin MAU | Unique admin logins per month | Trending up |
| Dashboard session length | Average time spent in compliance dashboard per session | ≥ 8 min (signals active use) |
| Feature adoption rate | % of admins who used each major feature in last 30 days | Track per feature |
| Recipient transaction frequency | Avg. transactions per active recipient per month | Trending up |

#### Compliance & Quality
| Metric | Definition | Target |
|---|---|---|
| Eligibility enforcement accuracy | % of transactions correctly approved/blocked | ≥ 99.5% |
| Manual review rate | % of transactions flagged for human review | ≤ 2% (high = rules need tuning) |
| False positive rate | % of eligible transactions incorrectly blocked | ≤ 0.1% |
| Compliance report generation time | Time from admin request to downloadable report | ≤ 5 minutes |

#### Support & Reliability
| Metric | Definition | Target |
|---|---|---|
| Support ticket volume | Tickets per 1,000 active recipients per month | ↓ 20% YoY |
| Ticket category breakdown | % by type: balance, eligibility, technical, onboarding | Track for product prioritization |
| System uptime | % uptime for eligibility enforcement service | ≥ 99.9% |
| Transaction latency | P95 response time for eligibility check | ≤ 2 seconds |

---

### Layer 3 — Leading Indicators (Weekly / Daily)

These are the metrics you check every sprint to catch problems before they compound.

| Indicator | Why It Matters | Alert Threshold |
|---|---|---|
| Day-1 wallet activation rate | Predicts 7-day activation; catches onboarding friction early | < 40% = investigate |
| Transaction error rate (daily) | Compliance failures catch early before they become audit issues | > 0.5% = immediate review |
| New admin support ticket rate | High rate = onboarding broken | > 1 ticket per 5 new admins |
| Dashboard load time (P95) | Performance degradation shows up here first | > 4 seconds = engineering alert |
| Report generation failures | Failed reports = admin can't meet reporting obligations | Any failure = P1 bug |
| Declined transaction spike | Sudden increase may signal rule misconfiguration | +50% WoW = investigate rules engine |

---

## Metrics Design Principles

### 1. Define metrics before the sprint, not after
If you don't know what success looks like before you build it, you can't measure it. Every epic should have a success metric defined in the planning meeting.

### 2. Avoid vanity metrics
Page views, total sign-ups, and raw transaction volume are vanity metrics for a compliance product. What matters: are funds getting to the right people, being spent correctly, and generating clean audit trails?

### 3. The counter-metric rule
Every primary metric needs a counter-metric to prevent gaming. Examples:
- Activation rate ↑ → counter: don't inflate by auto-activating wallets without recipient intent
- Transaction approval rate ↑ → counter: compliance accuracy must not fall below 99.5%
- Report generation speed ↑ → counter: data completeness must not be sacrificed for speed

### 4. Compliance metrics are non-negotiable floors
For public-sector products, compliance accuracy is not a KPI to optimize — it's a floor to maintain. Any feature that risks dropping eligibility enforcement accuracy below 99.5% does not ship, regardless of other metrics.

### 5. Segment by user type
Aggregate metrics hide problems. Always break down by:
- Agency size (small district vs. large state agency)
- Program type (education savings vs. emergency assistance)
- Recipient cohort (newly activated vs. 6+ months active)

---

## Metrics Review Cadence

| Cadence | Audience | Focus |
|---|---|---|
| Daily | PM + Engineering lead | Leading indicators, error rates, system health |
| Weekly | Product team | Sprint progress, feature adoption, support ticket trends |
| Monthly | Cross-functional (CSM, Sales, Product) | Product metrics, NPS, activation and retention |
| Quarterly | Leadership | Business metrics, OKR progress, roadmap reprioritization |

---

*This framework reflects my MEL (Monitoring, Evaluation & Learning) background applied to product measurement — defining what success looks like before execution, tracking leading indicators to catch drift early, and using data to drive roadmap decisions.*

*Deepshikha Dash · Product Manager · Austin, TX*
