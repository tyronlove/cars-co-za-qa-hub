# Cars.co.za Answers — MVP handoff

[Open the MVP](https://tyronlove.github.io/cars-co-za-qa-hub/)

This is the clean frontend reference for implementing the question hub. It includes the supplied Cars.co.za logo, 8 in-depth guides, 20 quick answers and 7 topics. All presentation annotations, strategy panels and mockup controls have been removed.

## Run locally

Open `index.html` in a browser, or run `python3 -m http.server 8000` from this folder and open `http://localhost:8000`. There are no packages or build steps.

## Files

- `index.html`: page structure, styles, content fixtures and browser interactions.
- `assets/cars-logo.png`: supplied brand asset, displayed at 160 × 48 pixels.

## Included behaviour

- Search filters guide titles, summaries and topics, plus quick-answer questions and answers. Multiple search words must all match. Search works as you type and on form submission.
- Topic filters apply to both sections and combine with search. Each section shows its result count and an empty state.
- Guide cards open the full article with a summary, sections, comparison tables, related cars, related guides and a table of contents.
- Quick answers expand inline. Links from a guide open the relevant answer on its topic, clearing the search so the answer remains visible.
- Logo, Answers navigation and article breadcrumbs return to the hub. Guide cards are keyboard accessible; filters and answer controls expose their state.

## Implementation work for the application team

This handoff is a static frontend reference, not a connected production service. Guide navigation currently switches views in one document; it does not create separate page routes or browser-history entries.

1. Implement `/answers/`, topic pages at `/answers/{topic}/`, and guide pages at `/answers/{topic}/{guide}/`. The `SLUG` mapping and guide `slug` fields supply the intended path segments. Quick answers belong on topic pages with their existing IDs as anchors.
2. Move `CATS`, `GUIDES` and `QUICK` into the chosen content system. Render the page content and links through the application framework and support direct visits, refresh, and browser Back/Forward.
3. Replace `CARS` fixtures and decorative vehicle silhouettes with inventory records, photos, prices and listing URLs. Keep the guide-specific selection of relevant cars.
4. Connect the existing site navigation, sign-in, listing buttons, calculators, insurance links and sell/valuation flows. These controls are visual placeholders in this handoff; no form submissions or lead capture are implemented.
5. Have the editorial team approve the example copy, dates and finance calculations before launch. Listings, prices and financing assumptions are illustrative.

The original annotated design remains available in Git history before the MVP change.
