# Implementation and release plan

| Window | Work | Completion check |
|---|---|---|
| Week 1, before 23 Nov 2026 | Product spec, business rules, mobile wireframes, API and technical design | Both roles reviewed, design accepted, and blocking API and accounting decisions recorded |
| 23 Nov–6 Dec 2026 | Backend foundation, accounts and roles, pharmacy enrollment, catalog, and initial inventory | Test accounts for both roles and working catalog and stock records |
| 7–15 Dec 2026 | Exams 7–14 Dec and rest before restarting | Backend resumes 16 Dec |
| 16 Dec 2026–4 Jan 2027 | Complete verification, routing/search, sales, returns, expenses, dashboard and API integration tests | Test environment and example requests ready for mobile |
| 5–23 Jan 2027 | Build and integrate client and pharmacy-owner mobile flows | Both roles pass product acceptance checks on the target devices |

Task order within each phase is proposed. The schedule assumes backend work starts 23 November and wraps up 4 January. Assign owners for product and design acceptance, backend, mobile, and release verification during Week 1.

## Release checks

- Client test covers skippable onboarding, GPS denied, manual location, exact medicine filters, empty results, nearest reachable results, and external directions.
- Pharmacy test covers license upload and approval gating, camera fallback, stock receipts, sales, returns, reversals, write-offs, and expenses.
- Verify that selling the last unit removes the listing and restocking restores it. Race two sales for the last unit and retry a submitted sale.
- Reconcile dashboard figures against receipts, sales, partial refunds, supplier returns, and expenses.
- Confirm staging configuration, production credentials, routing quotas, support ownership, and recovery steps before release.

## Decisions for design acceptance

1. Confirm whether Recent searches ships on the client home screen and whether Saved pharmacies is in scope.
2. Confirm inventory costing, tax treatment, currency, and reporting time zone.
3. Confirm license authority coverage and handling of verification results the engine cannot resolve.
4. Confirm launch geography, routing provider and mode, recognition approach, and mobile platforms.
