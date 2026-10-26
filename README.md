# Paramount Signature

Presentation MVP for the Paramount Signature restaurant and bar platform. This team project brings the customer experience, branch operations, deliveries and supplier workflows into one browser-based demonstration.

## Run locally

From the repository root, run:

```sh
python -m http.server 8000 --directory dist
```

Open http://localhost:8000. No dependency installation or build step is required. Python only serves the static files; any static HTTP server can be used instead.

## Customer experience

- Full-screen grill video, photographic menu panels, venue information and gallery.
- Hardware black, warm chalk and walnut finishes, with a pinned header and serving tray.
- Dockable navigation that starts compact in each new tab session. Click the logo to toggle navigation; double-click to return to the top.
- Separate ordering catalogue with product search, category filters, branch availability and checkout.
- Order tracking and gathering enquiries.
- Responsive layouts, keyboard controls, video pause and reduced-motion support.

## Operations

The shared demonstration covers orders, kitchen and bar preparation, availability, dispatch, driver assignments, supplier replenishment, reporting and reconciliation. Branches are CBD, Chitungwiza, Borrowdale and Hatfield.

To walk through a delivery, place an order, switch to Orders, accept it, start preparation, finish the kitchen and bar tasks, assign a driver, confirm pickup and complete delivery. Use the role selector to explore each workspace. The Scenarios control loads repeatable examples; Reset restores the initial demonstration data.

## Project structure

| Path | Purpose |
| --- | --- |
| `dist/index.html` | Application entry point |
| `dist/app.mjs` | Routing, views, interactions and browser persistence |
| `dist/domain.mjs` | Ordering, stock reservations, fulfilment and supply rules |
| `dist/style.css` | Layout, components, textures and motion |
| `dist/assets/` | Bundled images, video and brand artwork |
| `tests/domain.test.mjs` | Domain behaviour checks |

## Validation

Requires Node.js with the built-in test runner:

```sh
node --check dist/app.mjs
node --check dist/domain.mjs
node --test tests/domain.test.mjs
```

The tests cover stock reservations, order expiry, payment rejection, receipt quantities, valid transitions, currency arithmetic, fulfilment modes, branch availability, replacements and branch-label migration.

## Current scope

This iteration is a presentation and workflow prototype. Records persist in the browser on the same origin; separate devices do not share data. The role selector previews workspaces and does not provide authentication or access control. Payments, refunds, messages, deliveries and enquiries are simulated. There is no live POS integration or automatic physical-stock synchronisation.

Production work includes a shared backend, authentication, server-side permissions, transactional stock reservations, payment integration and confirmed business data. The existing Touch Africa POS remains outside this presentation MVP.

## Visual assets

Food and venue photographs are illustrative Unsplash assets. The locally bundled grill video is a silent excerpt of [Pexels stock footage](https://www.pexels.com/video/person-grilling-meat-4781575/). The chilli logo is a vector recreation of the supplied reference and should be replaced with original brand artwork when available. Product photographs, street addresses, opening hours and operational policies require business confirmation. Web fonts use Google Fonts with system fallbacks.

## Team collaboration

`PRESENTATION_MVP` holds this presentation iteration. Keep feature work on separate branches and review changes together before merging. Document agreed requirements and validate customer and operational flows as the team develops the production system.
