# Mobile design review

Review the [refined iPhone 17 flow board](pharmasee-iphone-17-flow-green.png) for screen structure and the client and pharmacy-owner journeys. It uses illustrative products, prices, and locations. Use the product spec and the screen notes below for implementation requirements.

PharmaSee uses the five colors and typeface shown in the supplied green brand reference. Apply them to PharmaSee's own screens and identity.

| Brand color | Hex | UI use |
|---|---|---|
| Deep green | `#0B3D1E` | Main text and primary buttons |
| Forest green | `#116B37` | Links, icons, and secondary emphasis |
| Bright green | `#24C55E` | Availability and success accents with dark text |
| Soft green | `#9EE78D` | Selected and highlighted surfaces with dark text |
| Off-white | `#F2F9F3` | Base surfaces and light text on deep green |

**Typography** uses Poppins throughout.

| Client screen | Main action and states |
|---|---|
| Sign in or sign up | Sign in opens search. Sign up opens the skippable introduction. |
| Introduction | Start a medicine or pharmacy search, or skip to home. |
| Search | Choose medicine or pharmacy, enter a query, and use device location or enter an area. Recent searches is proposed. |
| Results | Medicine results show strength, form, price, stock status, pharmacy, and route distance. Offer strength and form filters. Provide loading, empty and retry states. |
| Pharmacy details | Show address and estimated route distance, then open directions externally. |

| Pharmacy owner screen | Main action and states |
|---|---|
| Enrollment and approval | Enter pharmacy and location, upload license, view pending, approved, and resubmission states. |
| Dashboard | Show revenue, gross profit, and net profit or loss for a selected period. Link to owner actions. |
| Inventory intake | Start the camera suggestion flow or select a catalog item manually. Allow adding a missing product. Confirm variant, quantity, cost and price before saving. |
| Sales, returns and corrections | Select a stock item or source transaction, enter the quantity and disposition, and show the effect before confirming. |
| Expenses | Enter date, category and amount. Confirm recording and refresh dashboard figures. |

During review, test the manual location, empty search, pending license, unreadable license, failed camera suggestion, and return disposition flows. Confirm what belongs in the owner navigation and whether Recent searches is included.
