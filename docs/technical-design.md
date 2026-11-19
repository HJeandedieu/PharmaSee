# Technical design

## System boundaries

- The mobile app presents client and pharmacy-owner flows. The backend enforces authentication, role permissions, and pharmacy ownership on each request.
- Use a transactional data store for inventory, sales, returns, and expenses. Persist each stock-changing transaction with its movement records, enforce nonnegative sellable quantity, and support idempotency keys for retried writes.
- Keep license files private. Store upload references separately from public pharmacy profiles. Restrict file reads to the verification process and authorized staff.
- Keep the shared catalog separate from each pharmacy's stock and prices. Use stable variant IDs across catalog, stock, and sale lines.

## License verification

An upload enters pending review. The engine evaluates the uploaded license against learned examples and returns a decision. Only an approved pharmacy becomes searchable. Proposed handling for unclear or unsupported documents is to keep the pharmacy unpublished and request a clearer submission or manual review. Confirm supported issuing authorities, reliable evidence of authenticity, review ownership, and renewal or expiry handling before release.

## Product recognition

An owner points the camera at the package. The recognition flow suggests a catalog product or reports no match. The owner confirms the name, strength, and form, then enters quantity, purchase cost, and selling price. Manual catalog search and entry remain available from the same flow. Confirm whether the first implementation uses barcodes, package text, image recognition, or a combination.

## Search and routing

Resolve current coordinates or a manually entered place to a search origin. Filter eligible candidates in the database, then compute route distances through a routing provider and sort the returned routable candidates. A geographic prefilter must not silently omit closer routes. If distances are unavailable, show an explicit error or retry state. Pass the selected pharmacy location to the external maps app. Confirm the provider, transport mode, and launch coverage. Google Maps is preferred for the directions handoff.

## Operational checks

Track verification errors, routing errors, failed inventory writes, and request latency. Keep medicine-search terms, locations, and license images out of routine logs. Before release, prove concurrent sale-recording attempts cannot oversell and a retried write cannot double-count a movement. Review privacy and retention for license files, location, and search history.

Framework, hosting, database engine, and processing providers remain open. The [API draft](openapi.json) defines the mobile boundary independently of those choices.
