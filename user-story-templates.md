# User Story Templates with Acceptance Criteria
## Product Artifacts Library · Deepshikha Dash

Well-written user stories are the contract between product and engineering. These templates demonstrate story writing across four product scenarios common in public-sector and compliance technology contexts.

---

## Template Structure

```
STORY TITLE
As a [specific user role],
I want to [specific action],
So that [concrete outcome / value].

Acceptance Criteria:
- [ ] [Testable pass/fail condition]
- [ ] [Testable pass/fail condition]
- [ ] ...

Definition of Done:
- [ ] Coded and code-reviewed
- [ ] Unit tested by engineering
- [ ] QA tested against all ACs
- [ ] Error states and edge cases verified
- [ ] Release notes / documentation updated
- [ ] Stakeholder demo completed (if major feature)
```

**The AC discipline rule:** Every acceptance criterion must be verifiable by a QA engineer without asking the PM a clarifying question. If it can't be tested with a clear pass/fail, rewrite it.

---

## Scenario 1: Agency Admin Onboarding (Public Sector SaaS)

### Story: First-Time Admin Account Setup

**As a** newly assigned agency administrator,  
**I want to** complete account setup and configure my program settings in a single guided flow,  
**So that** I can begin disbursing funds to recipients without requiring support team assistance.

**Acceptance Criteria:**
- [ ] Admin receives an invitation email within 5 minutes of being provisioned by a super-admin
- [ ] Invitation link expires after 72 hours; expired link shows a clear error with instructions to request a new one
- [ ] Onboarding flow has 4 steps max: account creation → program configuration → recipient list upload → confirmation
- [ ] Progress is auto-saved at each step — if admin closes the browser and returns, they resume where they left off
- [ ] Admin can skip optional steps and return to them from the settings dashboard
- [ ] Onboarding completion triggers a welcome email with a getting-started checklist
- [ ] Setup flow is fully functional on Chrome, Firefox, Safari, and Edge (latest two versions each)
- [ ] Mobile-responsive — all steps completable on a tablet

**Definition of Done:** ✅ Coded · ✅ QA tested · ✅ Cross-browser verified · ✅ Mobile tested · ✅ Invitation email tested end-to-end · ✅ Release notes updated

---

## Scenario 2: Compliance Flag & Review (Fintech / GovTech)

### Story: Admin Reviews Flagged Transaction

**As an** agency administrator,  
**I want to** review a flagged transaction and mark it as approved or rejected with a reason,  
**So that** I have a documented compliance decision trail and can resolve recipient disputes quickly.

**Acceptance Criteria:**
- [ ] Flagged transactions appear in a dedicated "Requires Review" queue, sorted by flag date (most recent first)
- [ ] Each flagged transaction shows: recipient name/ID, merchant, amount, date, flag reason code, and transaction ID
- [ ] Admin can click into a transaction to see full detail: itemized purchase if available, eligibility rule that triggered the flag, and recipient's remaining balance
- [ ] Admin selects "Approve" or "Reject" with a required reason code and optional free-text note
- [ ] Decision is saved immediately and triggers a recipient notification within 5 minutes
- [ ] Approved transaction updates recipient's transaction history as "Reviewed — Approved"
- [ ] Rejected transaction updates recipient's history as "Reviewed — Rejected" and shows the reason code to the recipient
- [ ] Decision is logged in the audit trail: admin ID, timestamp, decision, reason code, note
- [ ] Admin cannot make a decision on their own transactions (conflict of interest — requires second admin)
- [ ] Queue shows count of pending reviews in the navigation badge

**Definition of Done:** ✅ Coded · ✅ QA tested · ✅ Notification delivery tested · ✅ Audit log verified · ✅ Conflict-of-interest logic verified · ✅ DoS

---

## Scenario 3: Recipient Self-Service (Consumer-Facing)

### Story: Recipient Checks Balance and Recent Transactions

**As a** program recipient,  
**I want to** view my current wallet balance and last 30 days of transactions on my phone,  
**So that** I can track my spending and make sure my balance is accurate without calling support.

**Acceptance Criteria:**
- [ ] Balance displays on the home screen immediately after login — no additional navigation required
- [ ] Balance reflects all completed transactions within 15 minutes of purchase
- [ ] Transaction list shows last 30 days by default; recipient can scroll back further
- [ ] Each transaction shows: date, merchant name, amount, category, and status (completed / pending / declined)
- [ ] Pending transactions are visually distinguished from completed ones
- [ ] Recipient can tap any transaction to see full detail
- [ ] Page loads in ≤ 3 seconds on 4G mobile connection
- [ ] Balance and transaction list are accessible without internet if cached within last 4 hours (offline mode)
- [ ] Language: displays in recipient's preferred language (English default; Spanish, French available in v1)

**Definition of Done:** ✅ Coded · ✅ QA tested · ✅ Performance tested at 3-second threshold · ✅ Offline mode tested · ✅ Localization tested (EN/ES/FR) · ✅ Release notes updated

---

## Scenario 4: Data Export & Reporting (Compliance / Audit)

### Story: Admin Exports Monthly Spend Report

**As an** agency administrator,  
**I want to** export a formatted monthly spend report for my program,  
**So that** I can submit it to my state oversight agency without spending hours reformatting data.

**Acceptance Criteria:**
- [ ] Admin selects: report type = "Monthly Spend Summary," month/year, and program name
- [ ] Report generates in ≤ 3 minutes for programs with up to 5,000 recipients
- [ ] Report includes: total allocated, total spent, total remaining, spend by category, and recipient-level summary
- [ ] PDF output matches the state agency's required formatting template (configurable per program)
- [ ] CSV output includes all raw transaction data with standardized column headers
- [ ] Both formats are downloadable from the report preview screen
- [ ] Generated report is saved to the admin's report history with filename, timestamp, and admin ID
- [ ] Report history is searchable and filterable by date and report type
- [ ] Report data is accurate to within 15 minutes of the export timestamp (data freshness indicator shown)

**Definition of Done:** ✅ Coded · ✅ QA tested · ✅ PDF formatting verified against template · ✅ CSV column structure verified · ✅ Performance tested (3-min threshold) · ✅ Report history persistence verified · ✅ Release notes updated

---

## Story Writing Anti-Patterns to Avoid

| Anti-Pattern | Problem | Fix |
|---|---|---|
| "As a user, I want the system to be fast" | Not actionable, not testable | Specify who, what, and a measurable threshold |
| AC: "The page should look good" | Subjective, untestable | "Page renders without layout breaks on Chrome/Firefox/Safari at 1280px and 375px viewports" |
| AC: "Data should be accurate" | Too vague | "Balance reflects all completed transactions within 15 minutes of purchase" |
| Story with 15+ ACs | Too large — can't fit in one sprint | Split into two stories; each should be shippable independently |
| Missing error states | QA will find them anyway, mid-sprint | Always include: empty state, error state, loading state, and edge case in ACs |

---

*Deepshikha Dash · Product Manager · Austin, TX*
