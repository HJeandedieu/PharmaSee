# PharmaSee

PharmaSee connects people with nearby verified pharmacies that have the medicines they need in stock. Clients can compare availability, prices, and travel distances, then get directions to buy at the pharmacy.

Pharmacy owners use PharmaSee to manage inventory and record the transactions that keep stock and financial reports up to date.

## Client experience

- Create an account or log in, with skippable onboarding for new clients.
- Search for a medicine or pharmacy using a current or manually entered location.
- Filter medicines by strength and dosage form.
- Find approved pharmacies with matching stock, ranked by route distance.
- View medicine details, price, and pharmacy information.
- Open external directions, preferably in Google Maps, and purchase in person.

## Pharmacy owner experience

- Enroll a pharmacy, submit its license for verification, and set up its profile.
- Add stock from a shared medicine catalog, using camera suggestions or manual entry.
- Record quantities, purchase costs, and selling prices.
- Log sales, reverse incorrect entries, and manage customer and supplier returns.
- Record damaged or expired stock and operating expenses.
- Track revenue, gross profit, and net profit or loss.

## How stock availability works

A pharmacy becomes searchable after approval. Medicine results include the matching product variant when the pharmacy has a positive sellable quantity. Owners record in-person sales in PharmaSee, which deducts stock and updates revenue. Returns and corrections create linked adjustments to inventory and financial records.

## Project status

The project is in the specification phase. This repository contains the MVP requirements, business rules, technical design, and draft API contract. Proposed decisions are identified in the documentation.

## Documentation

| Document | Contents |
|---|---|
| [MVP product specification](docs/pharmasee-user-flow.md) | Complete client and pharmacy-owner journeys, MVP scope, and acceptance criteria |
| [Business rules and data model](docs/business-rules.md) | Catalog, inventory, sales, returns, expenses, and profit calculations |
| [Technical design](docs/technical-design.md) | System boundaries, verification, recognition, routing, and data consistency |
| [Draft API contract](docs/openapi.json) | OpenAPI 3.0.3 endpoints and request and response schemas |

Start with the product specification, then read the business rules and technical design alongside the API contract.
