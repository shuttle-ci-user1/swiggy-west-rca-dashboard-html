# swiggy-west-rca-dashboard-html
Single-file Brand RCA search dashboard

## Monthly trend view

`monthly.html` is the monthly RCA trend dashboard for the West brands (scope: devlekar.a@swiggy.in — West / Gourmet). It covers:

- **Brand-level monthly trend** — full Apr–Oct MTD series (orders, GMV, net GMV, AOV, M2C, C2O, P2O, M2O) for the brand present in the uploaded monthly workbook.
- **Month-over-month deltas** — per-metric MoM columns plus Aug→Sep ads, discount and ops deltas.
- **Top degrowth brands** — snapshot GMV-loss ranking of the West portfolio.
- **Platform monthly benchmark** — portfolio aggregate monthly view.
- Searchable by brand, KAM, cuisine and status; brand rows are clickable.

### Data model

The monthly view is assembled from part files; replace the parts to refresh, no code change needed:

| File | Contents |
|---|---|
| `monthly_parts.json` | Manifest (scope, updated_at, part list) |
| `monthly_part_full_series.json` | Full monthly series for the workbook brand |
| `monthly_part_snapshot_brands.json` | Snapshot loss rows for the other West brands |
| `monthly_part_top_degrowth.json` | Top 10 degrowth ranking |
| `monthly_part_platform_benchmark.json` | Platform monthly benchmark |

Monthly flow: run the West RCA monthly query → export CSV → regenerate the part files → the dashboard auto-refreshes on load.

## Daily view

`index.html` is the daily Brand RCA search dashboard, fed by `data.json`.
