# GeoAI for Future Earth – ACRS 2026 Training Notebooks



Hands-on Python notebooks for the **ACRS 2026 Training Workshop on GeoAI for Future Earth**. The series covers cloud-native satellite image analysis using open-source Python tools — from Colab basics to creating publication-ready median composites.

---

## Notebooks

| # | Notebook | Topics |
|---|----------|--------|
| 00 | [Hello Colab](00_hello_colab.ipynb) | Colab environment, package management, downloading Sentinel-2 data, band visualisation, RGB & false-colour composites |
| 01 | [XArray Basics](01_xarray_basics_for_satellite_image_visualisaton.ipynb) | XArray Dataset/DataArray, time-series selection, aggregation, NDVI, monthly composites, pixel time series |
| 02 | [STAC & Dask Basics](02_stac_dask_basics.ipynb) | STAC catalog queries, Dask parallel computing, loading cloud-hosted Sentinel-2, scene visualisation |
| 03 | [Median Composite](03_median_composite.ipynb) | Area-of-interest loading, multi-scene compositing, clipping to a boundary, COG export |

All notebooks open directly in **Google Colab** via the badge links at the top of each file — no local installation needed.

---

## Data

| File | Description |
|------|-------------|
| `Data/Sentinel2_jan2023.tif` | Sentinel-2 L2A GeoTIFF (4 bands: Red, Green, Blue, NIR), January 2023, UTM Zone 43N |
| `Data/delhi_1997-2012_district.json` | Delhi district boundaries GeoJSON — 9 districts (Central, East, North, North East, North West, New Delhi, South, South West, West) |

---

## What You Will Learn

```
Cloud-native RS workflow
│
├── 00  Colab basics → download GeoTIFF from GitHub → visualise bands
│
├── 01  XArray ──── load STAC data ──── select / slice / aggregate
│         └── Exercises: indexing, NDVI, seasonal comparison, time series
│
├── 02  STAC catalog query ──── Dask parallel load ──── scene inspection
│         └── Exercise: extract product IDs from metadata
│
└── 03  Load AOI (Delhi district) ──── median composite ──── clip ──── export COG
          └── Exercise: compare two districts
```

---

## Quick Start

**On Google Colab (recommended):** Click any "Open in Colab" badge — packages are installed automatically in the first cell.

**Locally:**

```bash
git clone https://github.com/nilaynishant/acrs.git
cd acrs
pip install pystac-client odc-stac rioxarray dask[distributed] botocore matplotlib numpy geopandas
jupyter notebook
```

---

## Key Libraries

| Library | Purpose |
|---------|---------|
| [XArray](https://docs.xarray.dev) | Multi-dimensional labelled arrays for raster time series |
| [rioxarray](https://corteva.github.io/rioxarray) | Geospatial extensions for XArray (CRS, clipping, COG export) |
| [pystac-client](https://pystac-client.readthedocs.io) | Query STAC catalogs for satellite imagery |
| [odc-stac](https://odc-stac.readthedocs.io) | Load STAC items into XArray Datasets |
| [Dask](https://www.dask.org) | Parallel & lazy computation |
| [GeoPandas](https://geopandas.org) | Vector data handling (AOI boundaries) |



