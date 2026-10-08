# LuxeCompare — Final prototype

An interactive web prototype for luxury purchase decisions. Uses only illustrative mock data; product prices, reviews, availability, and policies are not live or verified.

## Run

Requires Node.js 20.19+ or 22.12+.

```sh
cd /workspace/luxecompare
npm ci --cache /workspace/.npm-cache
npm run dev -- --port 3000
```

`npm run build` creates the production bundle. `npm run preview -- --port 3000` serves that bundle.

## Final happy path

1. Describe a shopping goal in natural language.
2. Click **Review my preferences**. Review the interpreted product, budget, intended use, priorities, and style; adjust selected priorities and 1–5 importance weights.
3. Click **Confirm & view shortlist** to generate the personalized shortlist.
4. Select at least two products and compare side by side.
5. Review the weighted recommendation and tradeoffs.
6. Choose the preferred product and complete the decision.

The local mock interpreter recognizes budgets such as $3,000 and 3k, everyday use, versatility, reviews, value for money, and explicitly mentioned timeless/minimal/modern styles. Unspecified style remains **Not specified** and contributes no style bonus. Mentioned priorities start at 3/5, “matters” at 4/5, and “most important” at 5/5. Priority adjustments are preserved when reviewing preferences from the shortlist. The same three mock products are retained. No AI service, authentication, checkout, or payment is included.

## Retained Concept No. 2 scoring

The four existing priority toggles now have 1–5 importance sliders. The recommendation averages the selected mock factor ratings weighted by importance, then retains the original 0.30 bonus for matching the chosen style. Reviews use stars × 2; value uses 10 minus price in thousands of dollars. The explanation shows each weight, its percentage, its score contribution, and the winner versus the next-best compared product. The final prototype retains weighted scoring; the style bonus applies only when the goal specifies a matching style.
