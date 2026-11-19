# PharmaSee MVP product spec

PharmaSee helps clients find verified pharmacies with the medicine they need in stock. Clients buy in person. Pharmacy owners manage stock and track sales, returns, expenses, and profit.

## Client journey

1. Sign up or log in. After sign-up, offer a skippable walkthrough for finding a medicine or pharmacy.
2. On the home screen, search by medicine or pharmacy name. Proposed home shortcut: Recent searches, with each entry rerunning a live search.
3. Use current location or enter a location manually. Rank results by estimated route distance.
4. For medicine searches, allow optional strength and form filters. Show the matching product name, strength, form, selling price, pharmacy, and distance. Include only approved pharmacies with a positive quantity for that product.
5. Select a pharmacy and open external directions, preferably in Google Maps. Purchase at the pharmacy. Reservations and checkout are outside MVP scope.

## Pharmacy owner journey

1. Enroll the pharmacy and upload its license. The verification engine assesses the license. The pharmacy appears in client search once approved.
2. Set up the pharmacy profile and location. Use the camera to get a suggested product identity, then confirm the product and enter quantity, purchase cost, and selling price. Owners can search the shared catalog manually or add missing products.
3. Log in-person sales, stock corrections, customer returns, supplier returns, and operating expenses.
4. View revenue, gross profit, and net profit or loss for a selected period.

## Acceptance criteria

| Flow | Acceptance check |
|---|---|
| Signup and login | A new client can skip onboarding and search. A returning client lands on search. |
| Location and ranking | A client who declines location access can enter an area. Results with a route are ordered by route distance. |
| Search and directions | Filters identify the intended strength and form. Pending pharmacies and out-of-stock variants are omitted from medicine results. Directions use the selected pharmacy as the destination. |
| Owner enrollment | An unapproved pharmacy remains absent from both search modes. An approved pharmacy with a usable location can appear. |
| Stock setup | A failed camera suggestion still allows manual product selection or entry. |
| Sales | Logging a sale reduces the selected variant's stock and increases recorded revenue. The last unit sold removes that listing from medicine search. |
| Corrections and returns | Sale reversals, customer returns, supplier returns, and damaged or expired stock produce traceable adjustments. A customer return only restores sellable stock when eligible. |
| Dashboard | Period totals reconcile with recorded sales, returns, inventory cost, and expenses under the agreed accounting rules. |

See [business rules](business-rules.md), [technical design](technical-design.md), and the [release plan](implementation-plan.md).
