# oss-pricing-data

Open dataset behind Beton's commercial open-source pricing teardowns.

We tear down the pricing of commercial open-source software — what it actually
costs, what the license allows, and whether the paid tier is worth it. This repo
is the raw, verified data behind that analysis.

## What's here

| File | Rows | What |
|---|---|---|
| `data/pricing-2023-2026.csv` | 20 tools | License, stars, pricing model, entry price, free tier, and SSO tier for 2026 — plus 2023 baselines |
| `data/unit-price-changes.csv` | 4 | Verified per-unit price deltas 2023→2026 (per event, per TB, per seat) |
| `data/sso-tax.csv` | 11 | The plan tier where SSO unlocks, and the cost of that tier |

## Methodology

- **2026 figures** come from each vendor's live pricing page, captured in 2026 and
  re-verified (JS-rendered pages fetched with a rendering scraper, not a plain GET;
  usage-priced pages cross-checked against the vendor's own calculator).
- **2023 figures** are quoted from Wayback Machine snapshots of the *same vendor's
  pricing page* — the `source_2023_wayback` column links the exact snapshot. Numbers
  are never reconstructed from memory.
- Tools too new to have a 2023 pricing page (Firecrawl, Coolify) or with no 2023
  snapshot (Langfuse) are marked accordingly rather than guessed.

## The analysis

Full write-up with charts: **[Pricing the Open Source Software, Vol 2](https://www.getbeton.ai/blog/commercial-open-source-pricing-2026/)**
· All individual teardowns: **[getbeton.ai/blog/teardowns](https://www.getbeton.ai/blog/teardowns/)**

## License

Data is published under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) —
use it freely, just credit [Beton](https://www.getbeton.ai/) and link back.

Found an error or a stale number? Open an issue or PR.
