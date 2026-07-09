# Grants or Loans? How Financing Instrument Design Shapes Renewable Energy Investment Across EU Member States

Bachelor Thesis — Ana Srugies García, UC3M (Double Degree in International Studies and Economics)
Supervised by Juan Antonio Mayoral Díaz-Asensio
Madrid, 2026

## Overview

This repository contains the data and analysis code for a thesis examining whether the form of EU Recovery and Resilience Facility (RRF) financing — grants versus loans — differentially affects renewable energy capacity additions across EU member states, and whether that relationship is moderated by pre-existing renewable energy infrastructure.

## Repository structure
├── frozen/
│   ├── Thesis_Panel_Fina_Frozen.ipynb
│   └── panel_step6_official.xlsx
├── raw_data/
│   └── rrf_raw.xlsx
└── live_notebook/
├── Thesis_Panel_Final.ipynb
├── Data_WB_GovernEffectiveness.csv
└── view_cabinet.csv

## Two versions of the analysis

**`Frozen Files/`** — The version used to produce the results reported in the thesis. Loads directly from a locally saved snapshot (`panel_step6_official.xlsx`) to guarantee reproducibility, since Eurostat periodically revises its published figures after retrieval. **Run this notebook to reproduce the thesis results exactly.**

**`Live Notebook/`** — An earlier development version that pulls data live from the Eurostat API (via the `eurostat` Python package) and combines it with `Data_WB_GovernEffectiveness.csv` (World Bank Worldwide Governance Indicators) and `view_cabinet.csv` (ParlGov cabinet composition data). Included for transparency into the full data construction process, but **not guaranteed to reproduce the exact same results**, since Eurostat's live figures may have changed since the thesis data was retrieved — for example, Cyprus's loan receivables for 2022–2024 were removed from the live `gov_rrf_fa` table after the original data pull, and are only preserved via a hard-coded patch in the frozen version.

## Data sources

- **Eurostat**: `gov_rrf_fa` (RRF grant/loan receivables), `nrg_inf_epcrw` (installed renewable electricity capacity), `nrg_inf_epc` (total electricity capacity), `nrg_ind_ren` (renewable energy share), `nrg_ind_id` (energy import dependency), `nama_10_pc` (GDP per capita), `demo_pjan` (population)
- **World Bank**: Worldwide Governance Indicators (government effectiveness)
- **ParlGov**: cabinet composition and party left-right positioning (government ideology)

## Sample

Full panel: 27 EU member states, 2021–2024 (108 observations). Main regression specification: 13 member states that requested RRF loans (52 observations) — the 14 non-requesting states are excluded from the loan analysis, since their zero-loan values reflect a political decision not to borrow rather than a zero treatment effect.

## `raw_data/`

`rrf_raw.xlsx` — raw RRF disbursement data as retrieved from Eurostat (`gov_rrf_fa`), included for reference and transparency. Not required to run either notebook.

## Notes on reproducibility

All Eurostat and World Bank data were retrieved in April–May 2026. The frozen notebook and its accompanying `panel_step6_official.xlsx` reflect the state of these records at that time, rather than the live databases at the time of reading — this is a deliberate design choice, not an oversight, given that source data (particularly RRF disbursement figures) is periodically revised.

## Citation

If referencing this work, please cite:

Srugies García, A. (2026). *Grants or Loans? How Financing Instrument Design Shapes Renewable Energy Investment Across EU Member States* [Bachelor's thesis, Universidad Carlos III de Madrid].
