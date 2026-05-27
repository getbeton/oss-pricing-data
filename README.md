# Open-source pricing data

The raw, verified dataset behind Beton's open-source pricing teardown series —
**20 commercial open-source tools, priced in 2026 and compared to 2023.**

📊 **Read the analysis →** [Pricing the Open Source Software, Vol 2](https://www.getbeton.ai/blog/commercial-open-source-pricing-2026/)
🔍 **All 20 individual teardowns →** [getbeton.ai/blog/teardowns](https://www.getbeton.ai/blog/teardowns/)

Each teardown reads a tool's pricing page line by line, reads its license more
carefully, and answers one question: is the paid tier worth it, or can you
self-host? This repo is the data behind that — every number with its source.

## Datasets

| File | Rows | What it holds |
|---|---|---|
| [`data/pricing-2023-2026.csv`](data/pricing-2023-2026.csv) | 20 | License, GitHub stars, pricing model, entry price, free tier, and SSO tier for 2026 — plus the 2023 baseline and a `what_changed_2023_to_2026` summary |
| [`data/unit-price-changes.csv`](data/unit-price-changes.csv) | 4 | Per-unit price deltas 2023→2026 (per event, per TB, per seat) |
| [`data/sso-tax.csv`](data/sso-tax.csv) | 11 | The plan tier where SSO unlocks, and the monthly cost of that tier |

### `pricing-2023-2026.csv` columns

`tool`, `slug`, `license_2026`, `github_stars_2026`, `pricing_model_2026`,
`entry_price_2026`, `free_tier_2026`, `sso_tier_2026`, `sso_tier_cost_2026`,
`entry_price_2023`, `pricing_model_2023`, `sso_tier_2023`,
`source_2023_wayback` (the exact archived snapshot each 2023 number is quoted from),
`covered_in_vol1`, `what_changed_2023_to_2026`.

## How it's verified

- **2026 figures** come from each vendor's live pricing page, re-verified in 2026.
  JS-rendered pages are fetched with a rendering scraper (not a plain GET);
  usage-priced pages are cross-checked against the vendor's own calculator.
- **2023 figures** are quoted from Wayback Machine snapshots of the *same vendor's
  pricing page* — see the `source_2023_wayback` column for the exact snapshot.
  Numbers are never reconstructed from memory.
- Tools too new to have a 2023 pricing page (Firecrawl, Coolify) or with no 2023
  snapshot (Langfuse) are flagged as new to this volume, not guessed.

## Cite it

> Beton, *Open-source pricing data* (2026), CC BY 4.0.
> https://github.com/getbeton/oss-pricing-data

## License

Published under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) — use it
freely, even commercially; just credit Beton and link back.

## About Beton

[Beton](https://www.getbeton.ai/) is open-source revenue intelligence: it detects
buying signals in your product-usage data (PostHog, Stripe, your warehouse) and
routes the warmest accounts to sales. Self-hostable — [github.com/getbeton/inspector](https://github.com/getbeton/inspector).

---

Found a stale number or an error? [Open an issue](https://github.com/getbeton/oss-pricing-data/issues) or a PR — corrections welcome.
