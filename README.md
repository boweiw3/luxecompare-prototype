# LuxeCompare — Prototype Concept No. 2

An interactive web prototype for luxury purchase decisions. Uses only illustrative mock data; product prices, reviews, availability, and policies are not live or verified.

## Run

Requires Node.js 20.19+ or 22.12+.

```sh
cd /workspace/luxecompare
npm ci --cache /workspace/.npm-cache
npm run dev -- --port 3000
```

`npm run build` creates the production bundle. `npm run preview -- --port 3000` serves that bundle.

## Happy path

1. Search for a black shoulder bag, or use a suggested category.
2. Adjust the budget and style, select priorities, and weight each selected priority from 1 (slightly important) to 5 (essential).
3. Review the Gucci Jackie 1961, Prada Re-Edition 2005, and Saint Laurent Le 5 à 7 shortlist.
4. Select at least two products and compare their details.
5. Read the weighted recommendation, its factor-by-factor score explanation, and each product's tradeoffs.
6. Choose any product to complete the decision. Review the comparison or start again.

Broad category searches use the three-bag demo collection. Searches naming a featured brand or product narrow that collection. Budget filters products and priorities influence the recommendation. No authentication, checkout, payment, or backend is included. Bag illustrations are local SVGs. Optional Google Fonts fall back to system fonts.

## Concept No. 2 scoring

The four existing priority toggles now have 1–5 importance sliders. The recommendation averages the selected mock factor ratings weighted by importance, then retains the original 0.30 bonus for matching the chosen style. Reviews use stars × 2; value uses 10 minus price in thousands of dollars. The explanation shows each weight, its percentage, its score contribution, and the winner versus the next-best compared product. All other steps, products, and visual design stay the same.
