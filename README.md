# Apify Actor Assets

Public CDN repository for README screenshots and shared brand assets used by [factden](https://apify.com/factden)'s Apify Store actors. Hosted as a public GitHub repo so `raw.githubusercontent.com` URLs render on the Apify Store actor pages.

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

| Actor | Apify Store | Source (private) |
|---|---|---|
| `g2-reviews-scraper` | [factden/g2-reviews-scraper](https://apify.com/factden/g2-reviews-scraper) | factden/g2-reviews-scraper |
