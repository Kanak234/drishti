# DRISHTI — AI-Driven Crime Analytics & Visualization

A Streamlit application that turns FIR-style crime records into zone-level
intelligence: hotspot maps, ML risk prediction, demand forecasting,
emerging-cluster detection, plain-English querying, and data-driven patrol
allocation. Runs fully offline.

## The console

`app.py` opens six tabs:

| Tab | What it does |
|---|---|
| Command Overview | Incident KPIs against the selected date range |
| Hotspot Map | Folium heat/marker map of incident density |
| Prediction & Forecast | Risk scoring and demand forecast per area |
| Trends & Patterns | Plotly breakdowns by crime type, hour, weekday |
| Ask DRISHTI | Plain-English queries over the records |
| Patrol Allocation | Units per area, ranked by computed risk |

## Modules

- `app.py` — the Streamlit console and all six tabs
- `ml_engine.py` — `HotspotPredictor`, `DemandForecaster`, `ClusterDetector`
- `nlq_engine.py` — `parse_query` / `apply_filters`, the natural-language layer
- `patrol.py` — `allocate`, risk-weighted patrol distribution
- `generate_data.py` — writes the synthetic `data/crime_records.csv`
- `test_core.py` — end-to-end smoke suite

## Run

```bash
pip install -r requirements.txt
python generate_data.py     # writes data/crime_records.csv
streamlit run app.py
```

`data/crime_records.csv` is generated, not committed — `.gitignore` excludes it,
and `app.py` reports its absence rather than crashing.

## Test

```bash
python test_core.py
```

Exercises the ML engine, the NLQ parser and patrol allocation end to end. It
generates its own data if none is present.

## Relationship to `dristi`

This is the same application as [`dristi`](https://github.com/Kanak234/dristi),
the KSP Datathon 2026 (Karnataka State Police × Hack2skill) entry. The two
repositories hold near-identical sources that have drifted by a few lines;
`dristi` is the original entry and carries the licence and the committed
dataset. Treat that one as canonical.

## Status

Working prototype. The smoke suite passes and the console runs offline against
generated data.
