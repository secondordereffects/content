# Second Order Effects — Content Repository

The structured content database for [soe.lagbase.com](https://soe.lagbase.com).

This repo contains all 204 entry analyses organized by category. The engine repo ([secondordereffects.github.io](https://github.com/secondordereffects/secondordereffects.github.io)) renders this content into a static site.

## Structure

```
entries/
├── technology/T001/meta.json     35 entries (T001-T035)
├── ai/A001/meta.json             35 entries (A001-A035)
├── markets/M001/meta.json        25 entries (M001-M025)
├── policy/P001/meta.json         22 entries (P001-P022)
├── organizations/O001/meta.json  26 entries (O001-O026)
├── society/S001/meta.json        25 entries (S001-S025)
├── infrastructure/I001/meta.json 18 entries (I001-I018)
└── science-health/H001/meta.json 18 entries (H001-H018)

_shared/
├── categories.json               Category definitions
├── tags.json                     Tag overrides
└── featured.json                 Homepage featured entries
```

## Entry Schema

Every entry follows the CHAIN framework. See the [CHAIN Framework](https://soe.lagbase.com/framework/) for details.

- `status: "card"` — Complete CHAIN analysis, rendered by shared card component
- `status: "full"` — Complete CHAIN analysis + custom `page.tsx` with unique visualization
- `status: "draft"` — Work in progress, not published

## How It Works

1. Push to `main` → triggers GitHub Actions
2. Actions dispatches `content-updated` event to engine repo
3. Engine repo rebuilds: clones this content, validates, generates OG images, builds, deploys

## License

Content: [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)
