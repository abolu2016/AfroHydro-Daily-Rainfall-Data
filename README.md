# AfroHydro-1 V2: Near-Real-Time Daily Precipitation Analysis for Africa

Overview

AfroHydro-1 V2 is a near-real-time daily precipitation analysis framework developed to provide spatially continuous rainfall estimates across Africa.

The current operational version integrates two precipitation information sources:

- NOAA Global Forecast System (GFS):24-hour accumulated precipitation, used as the background field.
- NASA Integrated Multi-satellitE Retrievals for GPM (IMERG) V07:Daily satellite precipitation estimates, used as pseudo-observations. IMERG Early is preferred, with IMERG Late as a fallback when available.

The datasets are integrated using a spatial optimal interpolation (OI) framework operating in log-transformed precipitation space.

Operational Coverage and Availability

Attribute Description 

Geographic coverage: Africa 
Operational start date: 1 October 2026 
Temporal resolution: Daily 
Analysis period: 00:00–24:00 UTC 
Background dataset: GFS 24-hour accumulated precipitation 
Pseudo-observation dataset: IMERG Early V07, with Late fallback 
Analysis method: Local spatial optimal interpolation 
Output format: GeoTIFF 
Publication schedule: Typically by 21:00 UTC daily 
Gauge assimilation Not included in the current near-real-time version

Daily products represent the preceding completed UTC calendar day. Publication is subject to the availability of upstream datasets, successful processing, and quality-control checks.

Rain-Gauge Observations and Retrospective Reanalysis

The current operational version does not assimilate ground-based rain-gauge observations.

Although Global Historical Climatology Network–Daily (GHCN-D) station observations are valuable for precipitation analysis, sufficiently timely and spatially representative gauge records are not consistently available across Africa within the operational 24-hour processing window.

Consequently, AfroHydro-1 V2 currently uses IMERG satellite precipitation as pseudo-observations rather than direct ground measurements.

However, the framework is designed to support retrospective gauge-informed reanalysis. As additional GHCN-D and other quality-controlled station observations become available in subsequent weeks or months, historical daily analyses can be regenerated using those observations.

Such retrospective analyses would be identified and versioned separately from the original near-real-time products to preserve scientific traceability.

Data Access

Daily precipitation GeoTIFFs are organized by year and month:

`data/YYYY/MM/AfroHydro_Daily_YYYYMMDD.tif`

The repository also provides:

- `catalog.csv` — available daily precipitation products.
- `latest.json` — metadata identifying the latest published analysis.
- `docs/latest.png` — visualization of the latest rainfall analysis.
- `docs/map_metadata.json` — date and file information used by the web portal.

Interactive portal: https://abolu2016.github.io/AfroHydro-Daily-Rainfall-Data/

Scientific Interpretation

AfroHydro-1 V2 is a satellite- and forecast-informed precipitation analysis, not a gauge-validated observational product.

The near-real-time analyses should be interpreted with appropriate consideration of satellite retrieval uncertainty, numerical weather prediction biases, and spatial interpolation assumptions.

Future retrospective gauge-informed versions may provide improved observational constraints, but such improvements require independent evaluation and validation.

Version Information

AfroHydro-1 V2 — Operational Near-Real-Time Release

- Start date: 1 October 2026
- Background: GFS daily 24-hour precipitation accumulation
- Pseudo-observations: IMERG V07 daily precipitation
- Gauge assimilation: Not currently included
- Planned extension: Retrospective gauge-informed precipitation reanalysis

The operational version is distinct from earlier AfroHydro-1 research analyses that incorporated ground-based gauge observations.
