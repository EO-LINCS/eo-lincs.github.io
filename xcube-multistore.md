---
title: xcube-multistore
layout: default
nav_order: 3
---

# xcube-multistore

**`xcube-multistore`** is the open-source Python package at the heart of EO-LINCS. It **unifies data access and processing** across many Earth Observation archives, turning a heterogeneous set of satellite and *in situ* sources into harmonised, analysis-ready data cubes.

[xcube-multistore on GitHub](https://github.com/xcube-dev/xcube-multistore){: .btn .btn-primary }
[Documentation](https://xcube-dev.github.io/xcube-multistore/){: .btn }
[How-to guides](https://xcube-dev.github.io/xcube-multistore/howto/){: .btn }

A guiding principle of EO-LINCS is that the project delivers **open data pipelines and a framework** — not fixed data products or cubes. `xcube-multistore` is that framework: it orchestrates a suite of `xcube` data-store plugins behind a single, configuration-driven workflow, so that data extraction becomes a single notebook whose sources, variables, spatial domain and resolution are all set in a YAML configuration.

![Conceptual overview of the xcube-multistore package](assets/images/xcube/meta_store_structure.jpeg)
*Conceptual overview of the `xcube-multistore` Python package.*

## What it does

- **Combines multiple stores** — access and merge data from many EO archives through one interface.
- **Configuration-driven** — a YAML config defines data sources, variables, grid, and time range; fully configurable by the user/scientist.
- **Robust at scale** — splits large requests to avoid oversized Dask graphs, resamples and interpolates onto a common grid, and merges cubes with differing time axes.
- **Reliable, reproducible runs** — skips already-generated datasets, integrates with preloading (`skip-preloaded`, `force_preload`, progress visualisation), and cleans up on failure or interruption. Developed with ~99% test coverage.

## Data stores used and enhanced in EO-LINCS

Each store is a public `xcube` plugin. Several were newly developed or substantially enhanced during EO-LINCS.

| Plugin | Description | Data source | Install |
|---|---|---|---|
| [`xcube-clms`](https://github.com/xcube-dev/xcube-clms) | Copernicus Land Monitoring Service datasets (land cover, forest characteristics, phenology) | CLMS | `conda install -c conda-forge "xcube-clms>=1.0.0"` |
| [`xcube-zenodo`](https://github.com/xcube-dev/xcube-zenodo) | Publicly shared scientific datasets, model outputs, benchmark products | Zenodo | `conda install -c conda-forge "xcube-zenodo>=1.0.0"` |
| [`xcube-stac`](https://github.com/xcube-dev/xcube-stac) | Sentinel data via open STAC APIs (Sentinel-2 L1C/L2A, Sentinel-3 SYNERGY) | CDSE & Planetary Computer STAC | `conda install -c conda-forge "xcube-stac>=1.0.0"` |
| [`xcube-gedidb`](https://github.com/xcube-dev/xcube-gedidb) | GEDI L2A/L2B/L4A/L4C (AGB density, canopy cover, DEM) | GEDI database | `pip install xcube-gedidb` |
| [`xcube-icosdp`](https://github.com/xcube-dev/xcube-icosdp) | Carbon & water flux products (currently FLUXCOM-X-BASE) | ICOS Data Portal | — |
| [`xcube-cds`](https://github.com/xcube-dev/xcube-cds) | ERA5 hourly time series & drought indices (1940–present) | Copernicus Data Store | — |
| [`xcube-cci`](https://github.com/esa-cci/xcube-cci) | ESA Climate Change Initiative (land cover, biomass, soil moisture, fire, GHGs) | ESA CCI Open Data Portal | — |
| [`xcube-eopf`](https://github.com/xcube-dev/xcube-eopf) | EOPF Sentinel Zarr — ESA's open, analysis-ready archive (Sentinel-1/2/3) | EOPF Zarr samples | — |
| [`xcube-sh`](https://github.com/xcube-dev/xcube-sh) | Sentinel Hub — optional paid mirror (Sentinel-1/2/3/5P) | Sentinel Hub | — |

Planned extensions include Proba-V and Sentinel-1 support via `xcube-stac`.
