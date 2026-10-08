# LuxeCompare — Prototype Concept No. 3

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

1. Describe a shopping goal in natural language, including a budget and priorities.
2. Click **Find my shortlist** to interpret the goal and view the matching demo bags directly.
3. Review the interpreted criteria and adjust the retained 1–5 priority weights on the shortlist if desired.
4. Select at least two products and compare their details.
5. Read the same weighted recommendation, score explanation, and tradeoffs.
6. Choose a product to complete the decision, or edit the goal and try again.

The mock interpreter recognizes dollar budgets (including $3,000 or 3k), everyday use, versatility, reviews, value for money, and timeless/minimal/modern style terms. It uses the same three black shoulder bags. Unspecified budget and style default to $3,000 and Timeless. Mentioned priorities start at 3/5, “matters” at 4/5, and “most important” at 5/5. This is a local rules-based demo, with no AI service or backend. No authentication, checkout, or payment is included. Illustrations are local SVGs; optional Google Fonts fall back to system fonts.

## Retained Concept No. 2 scoring

The four existing priority toggles now have 1–5 importance sliders. The recommendation averages the selected mock factor ratings weighted by importance, then retains the original 0.30 bonus for matching the chosen style. Reviews use stars × 2; value uses 10 minus price in thousands of dollars. The explanation shows each weight, its percentage, its score contribution, and the winner versus the next-best compared product. Concept No. 3 retains this scoring unchanged.
