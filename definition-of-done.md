# Definition of Done
## Template for Compliance-Critical Product Teams
### Product Artifacts Library · Deepshikha Dash

The Definition of Done (DoD) is the non-negotiable checklist that every story must pass before it's marked complete. A weak DoD is one of the top causes of technical debt, compliance gaps, and sprint velocity erosion.

This template is designed for teams building compliance-critical products — where "done" has higher stakes than a typical consumer app.

---

## Standard Story DoD

Every story must pass all applicable gates before moving to Done.

### Gate 1: Engineering
- [ ] Code written and self-reviewed by the engineer
- [ ] Pull request submitted with description linking to JIRA story
- [ ] Code reviewed and approved by at least one other engineer
- [ ] Unit tests written and passing (coverage ≥ 80% for new code)
- [ ] No new linting errors or warnings introduced
- [ ] Feature flag configured if applicable (for gradual rollout)

### Gate 2: QA
- [ ] All acceptance criteria verified — each AC has a documented pass result
- [ ] Error states tested: empty state, loading state, network failure, invalid input
- [ ] Edge cases tested (documented in AC or QA notes)
- [ ] Regression tested: no existing functionality broken
- [ ] Cross-browser / cross-device tested where applicable
- [ ] Accessibility checked (WCAG 2.1 AA minimum for user-facing features)

### Gate 3: Compliance & Security (applies to all data-handling features)
- [ ] PII handling reviewed: no unnecessary data collected or exposed
- [ ] Data retention policy applied: fields labeled with retention period
- [ ] Audit log entry confirmed: all relevant actions are logged with timestamp, user ID, and action type
- [ ] Eligibility rule logic reviewed by PM before QA sign-off (for compliance enforcement features)
- [ ] Security review completed if feature touches authentication, permissions, or financial data

### Gate 4: Documentation
- [ ] Release notes written (user-facing language, not technical)
- [ ] Internal product documentation updated (Confluence)
- [ ] API documentation updated if any endpoint was added or changed
- [ ] Training materials updated if the feature changes an existing user workflow

### Gate 5: Stakeholder Sign-Off (for P0 features and major releases)
- [ ] PM has reviewed and approved in staging
- [ ] CSM / customer success lead notified of change if it affects current agency workflows
- [ ] Legal/compliance team notified if feature touches fund processing, eligibility rules, or reporting

---

## Compliance-Specific Add-Ons

For features that touch **fund disbursement, eligibility enforcement, or audit trails**, the following additional gates apply:

- [ ] Eligibility rule logic independently verified by PM against program policy documentation
- [ ] End-to-end transaction test completed in staging with a test wallet
- [ ] Audit trail entry verified: correct fields logged, immutable (cannot be edited or deleted)
- [ ] Error handling for failed transactions tested: decline message shown, log entry created, no partial state left in system
- [ ] Financial data reconciliation verified: no rounding errors, no phantom balances

---

## DoD Scope by Story Type

| Story Type | Standard Gates | Compliance Gates |
|---|---|---|
| UI / cosmetic change | 1, 2, 4 | — |
| New user-facing feature | 1, 2, 4, 5 | — |
| Data collection / reporting | 1, 2, 3, 4, 5 | ✅ |
| Eligibility rule change | 1, 2, 3, 4, 5 | ✅ |
| Fund disbursement flow | 1, 2, 3, 4, 5 | ✅ |
| Audit trail / logging | 1, 2, 3, 4 | ✅ |
| Admin permission change | 1, 2, 3, 4, 5 | ✅ |

---

## Why This DoD Exists

In a compliance product, an incomplete story doesn't just create technical debt — it creates audit exposure, recipient harm, and agency trust erosion. A transaction that clears an ineligible purchase because eligibility logic wasn't fully tested is not a "we'll fix it next sprint" issue. It's a program integrity failure.

The compliance-specific gates in this DoD exist to make that failure mode impossible by design, not by luck.

---

## Using This DoD in JIRA

Each story template in our JIRA project includes the relevant DoD checklist as a sub-task list. No story can be moved to "Done" until all sub-tasks are checked. The sprint board is configured to enforce this — incomplete sub-tasks block the Done column transition.

---

*Deepshikha Dash · Product Manager · Austin, TX*
