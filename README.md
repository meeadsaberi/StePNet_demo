# StePNet demo: pedestrian flows in Sydney and NYC

Interactive maps of estimated pedestrian volumes on every sidewalk link, from the [StePNet](https://github.com/fanmdi/StepNet) model calibrated to local pedestrian counts.

Live site: https://meeadsaberi.github.io/StePNet_demo/

| City | Map | Data | Units | Counts | Calibration R² | Validation R² |
|---|---|---|---|---|---|---|
| Sydney | [sydney/](sydney/) | [GeoJSON zip](sydney/Sydney_weekday_link_flows_calibrated.geojson.zip) (EPSG:7856) | pedestrians per weekday | City of Sydney, autumn 2025, 113 sites | 0.80 | 0.38 |
| New York City | [nyc/](nyc/) | [GeoJSON zip](nyc/NYC_link_flows_calibrated.geojson.zip) (EPSG:4326) | pedestrians in the AM (8–9), midday (12:30–1:30) and PM (5–6) peak hour | NYC DOT automated counts, 2018–19, 1,009 sites | 0.79–0.81 | 0.59–0.64 |

## Method

Demand models transferred from Brisbane (Sydney) and Seattle (NYC), routed over up to 10 paths per trip. Demand is first scaled by one citywide factor, then calibrated to the counts.

Validation predicts each count site with its own count left out (random 20% splits). Errors are larger far from counted streets.

Nourmohammadi, Rashidi & Saberi (2026), [npj Sustainable Mobility and Transport 3, 65](https://www.nature.com/articles/s44333-026-00134-z).
