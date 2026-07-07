# Spectrum Outages Dataset

Community-reported Spectrum internet, TV, and phone outage data from the United States, published as an open dataset for research, journalism, business intelligence, and public awareness.

## Source & Attribution

This dataset is derived from community outage reports collected by **[SpectrumOutage.us](https://www.spectrumoutage.us/)** — an independent, community-powered Spectrum outage tracker built from real user submissions across the United States.

SpectrumOutage.us is **not affiliated with Charter Communications or Spectrum™**. Reports reflect what users voluntarily submit; they are not official outage confirmations from the provider.

If you use this dataset in research, analysis, products, or publications, please credit the source:

> Data sourced from [SpectrumOutage.us](https://www.spectrumoutage.us/) — community-reported Spectrum outage tracker.

## Dataset Summary

| Property | Value |
|----------|-------|
| **Records** | ~5,000 |
| **Date range** | 2026-06-16 → 2026-06-30 |
| **Geography** | United States |
| **Formats** | JSON, CSV |
| **Fields** | `created_at`, `city`, `state`, `zip_code`, `service`, `note` |

## Try a Sample on CodePen

Explore a **200-record sample** of this dataset in your browser — no download required. Each demo links back to [SpectrumOutage.us](https://www.spectrumoutage.us/) for live data and the full dataset.

| Demo | Description | Link |
|------|-------------|------|
| **Live outage stats** | Nationwide counters from the community dataset | [View on CodePen](https://codepen.io/usspectrumoutage-us/pen/019f3ca9-c594-73b0-abcb-9bab450c4a00) |
| **City outage checker** | Pick a US city and see report totals | [View on CodePen](https://codepen.io/usspectrumoutage-us/pen/019f3caa-ab9b-73fd-a60e-27fc8b15f579) |

Download the complete ~5,000-record release from the `data/` folder below or from [spectrumoutage.us/support-us](https://www.spectrumoutage.us/support-us).

## Files

```
spectrum-outage-dataset/
├── README.md
├── LICENSE
├── data/
│   ├── spectrum-outages-2026-06.json
│   └── spectrum-outages-2026-06.csv
└── docs/
    └── schema.md
```

## Quick Start

### JSON

```json
{
  "spectrum_outages_datasets": [
    {
      "created_at": "2026-06-30T18:07:13Z",
      "city": "Orlando",
      "state": "FL",
      "zip_code": "32822",
      "service": "All",
      "note": null
    }
  ]
}
```

### CSV

```csv
created_at,city,state,zip_code,service,note
2026-06-30T18:07:13Z,Orlando,FL,32822,All,
```

### Load with Python

```python
import pandas as pd

df = pd.read_csv("data/spectrum-outages-2026-06.csv", parse_dates=["created_at"])
print(df.head())
```

### Load with Node.js

```javascript
import data from "./data/spectrum-outages-2026-06.json" with { type: "json" };

console.log(data.spectrum_outages_datasets.length);
```

## Use Cases

- **Research** — Study outage frequency, geography, and timing patterns
- **Journalism** — Support local reporting on service disruptions
- **Business & analytics** — Benchmark regional connectivity issues
- **Civic tech** — Build dashboards, alerts, or neighborhood tools

## Schema

See [docs/schema.md](docs/schema.md) for full field definitions and allowed values.

## License

This dataset is released under [CC BY 4.0](LICENSE). You may share and adapt the data with attribution to [SpectrumOutage.us](https://www.spectrumoutage.us/).

## Disclaimer

Community reports indicate user-perceived outages. They do not represent confirmed network status from Spectrum or Charter Communications. Use this data as a signal, not as an official outage record.

## Contributing

New reports are submitted live at [spectrumoutage.us/report-spectrum-outage](https://www.spectrumoutage.us/report-spectrum-outage). Future dataset releases may be published as additional monthly files in `data/`.
