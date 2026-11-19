# Business rules and data model

## Records

| Record | Core fields and relationships |
|---|---|
| Account and pharmacy membership | Account ID, role, pharmacy ID for owners |
| Pharmacy | ID, display name, address, coordinates, verification status |
| License review | Pharmacy ID, private upload reference, status, timestamps, decision reason |
| Catalog product | ID, name, strength, dosage form, optional manufacturer and barcode |
| Pharmacy stock item | Pharmacy ID, catalog product ID, selling price, sellable quantity |
| Stock receipt | Stock item ID, quantity, unit purchase cost, received time, optional supplier reference |
| Stock movement | Stock item ID, quantity delta, reason, source record, actor, timestamp |
| Sale and sale line | Pharmacy, transaction time, stock item, quantity, actual unit selling price, allocated cost |
| Return or reversal | Source sale line or receipt, quantity, amount credited, stock disposition, reason |
| Expense | Pharmacy, category, amount, date, optional note |

## Stock and sales

- A product variant has its own pharmacy stock record. Search uses the shared catalog identity and the pharmacy's sellable quantity and price.
- Stock receipts increase sellable stock. Sales reduce it and record actual transaction prices. Save the transaction and stock movement atomically, and reject sales that would oversell.
- Keep a movement history. Reverse an incorrect sale through a linked record, with stock and revenue adjusted once. Record expired and damaged stock as movements out of sellable inventory.
- Customer returns reduce revenue. A resellable return restores inventory and reverses its associated cost of goods sold. A non-resellable return records the refund and keeps the item out of sellable stock.
- Supplier returns reduce inventory and record the supplier credit separately from sales. Cap linked returns at the quantity eligible to return. Store return disposition and movement together.

## Financial reporting

- Net sales revenue equals recorded sales less customer refunds and sale reversals.
- Gross profit equals net sales revenue less adjusted cost of goods sold.
- Net profit or loss also includes operating expenses and any applicable inventory losses. Classify each loss once so the same cost is never deducted twice.
- Proposed costing method is moving weighted average per pharmacy and product. Store the cost applied to each sale so later receipts cannot change historical margins. Confirm costing, partial return valuations, and supplier credit differences before implementing ledger calculations.
- Proposed representation is integer minor currency units with an explicit currency code. Confirm launch currency, reporting time zone, and tax treatment before finalizing reports.

## Search visibility

Both search modes require pharmacy approval and a usable location. Medicine search additionally requires sellable quantity above zero and a matching catalog variant. Proposed handling for catalog duplicates is to normalize names, strengths, and forms and prompt owners to reuse matching products.
