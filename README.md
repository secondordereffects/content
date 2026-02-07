# Second Order Effects — Content Repository

The structured content database for [soe.lagbase.com](https://soe.lagbase.com).

This repo contains entry analyses organized by category. The engine repo (private) renders this content into a static site at [soe.lagbase.com](https://soe.lagbase.com).

## Structure

```
entries/
├── technology/T001/meta.json     Technology entries (T prefix)
├── ai/A001/meta.json             AI & Automation entries (A prefix)
├── markets/M001/meta.json        Markets entries (M prefix)
├── policy/P001/meta.json         Policy entries (P prefix)
├── organizations/O001/meta.json  Organizations entries (O prefix)
├── society/S001/meta.json        Society entries (S prefix)
├── infrastructure/I001/meta.json Infrastructure entries (I prefix)
└── science-health/H001/meta.json Science & Health entries (H prefix)

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
3. Engine repo rebuilds: clones this content, validates, builds, deploys

## License

Content: [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)
