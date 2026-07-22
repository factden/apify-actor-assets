# Apify Actor Assets

Public CDN repository for README screenshots and shared brand assets used by [factden](https://apify.com/factden?fpr=factden)'s Apify Store actors. Hosted as a public GitHub repo so `raw.githubusercontent.com` URLs render on the Apify Store actor pages.

## Why this repo exists

Apify Store renders actor READMEs from each actor's source. Relative image paths (`docs/images/foo.png`) don't resolve because Apify treats the README as standalone markdown. Absolute URLs to `raw.githubusercontent.com` work, but they require the source repo to be public.

To keep actor source code private (extraction logic is competitive moat) while still rendering screenshots publicly, this repo separates **public read-only assets** from **private actor source**.

## Structure

```
apify-actor-assets/
├── README.md                ← this file
├── <actor-slug>/            ← one subdirectory per actor
│   ├── 01-...png            ← numbered to match README sequence
│   ├── 02-...png
│   └── ...
└── shared/                  ← cross-actor assets (logos, common UI)
```

## URL pattern

Each image is referenced from its actor's README via:

```
https://raw.githubusercontent.com/factden/apify-actor-assets/main/<actor-slug>/<filename>.png
```

Example:

```
https://raw.githubusercontent.com/factden/apify-actor-assets/main/g2-reviews-scraper/01-input-form-reviews-mode.png
```

## How to add a new actor's assets

1. Generate processed PNGs in the actor repo (e.g., via that repo's `tools/prepare_readme_screenshots.py`)
2. Create a new subdirectory in this repo: `<actor-slug>/`
3. Copy the PNGs over with their numbered filenames preserved
4. Commit + push
5. Update the actor's `README.md` to reference the new URLs

## Actors hosted here

| Actor | Apify Store | Assets in this repo |
|---|---|---|
| `google-hotels-scraper` | [Google Hotels Scraper](https://apify.com/factden/google-hotels-scraper?fpr=factden) | [8 screenshots](./google-hotels-scraper/) |
| `g2-reviews-scraper` | [G2 Reviews Scraper](https://apify.com/factden/g2-reviews-scraper?fpr=factden) | [7 screenshots](./g2-reviews-scraper/) |
| `expedia-hotel-reviews-scraper` | [Expedia Reviews Scraper](https://apify.com/factden/expedia-hotel-reviews-scraper?fpr=factden) | [5 screenshots](./expedia-hotel-reviews-scraper/) |
| `hotels-com-reviews-scraper` | [Hotels.com Reviews Scraper](https://apify.com/factden/hotels-com-reviews-scraper?fpr=factden) | [6 screenshots](./hotels-com-reviews-scraper/) |
| `ctrip-trip-reviews-scraper` | [Trip.com & Ctrip Reviews Scraper](https://apify.com/factden/ctrip-trip-reviews-scraper?fpr=factden) | [9 screenshots](./ctrip-trip-reviews-scraper/) |
| `indeed-jobs-scraper` | [Indeed Jobs Scraper](https://apify.com/factden/indeed-jobs-scraper?fpr=factden) | [5 screenshots](./indeed-jobs-scraper/) |
