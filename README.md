# iGaming Slot Specs

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.24331735.svg)](https://doi.org/10.5281/zenodo.24331735)
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)

Open specs of **1,333 online casino games** from 9 studios: maths, grid, mechanics,
148 themes and 83 features as taxonomies, bonus buy prices, **618 games with
several RTP configurations**, and **8,660 accessibility notes** (colour-blind play, sound-only cues).

Version **2026-11-18** · captures 2026-06-13 → 2026-11-18 · re-published monthly, see
[CHANGELOG](CHANGELOG.md).

## Where the data comes from

Every game is opened in its **official provider demo** in a headless browser; rules, paytable and settings screens
are recorded and the values are verified with OCR. Each row carries the capture date, and `coverage_gaps` lists
what could not be captured, so missing values are missing, not guessed. The capture pipeline is run by
[iGaming Tools](https://i-gaming.tools/), a data API (not a casino: no games, no bets).

## Tables

| file | contents |
|---|---|
| [`slots.csv`](slots.csv) | one row per game: identity, maths, grid, mechanics, themes, features, bonus economics, capture date |
| [`rtp_variants.csv`](rtp_variants.csv) | one row per RTP configuration a game ships with, and the condition when stated |
| [`bonus_buys.csv`](bonus_buys.csv) | bonus buy options with their cost in bets |
| [`accessibility.csv`](accessibility.csv) | per-game accessibility notes: colour-blind, hearing and other groups |
| [`coverage_gaps.csv`](coverage_gaps.csv) | what was and was not captured for each game, so gaps are explicit, not guessed |
| [`providers.csv`](providers.csv) | studio profile: HQ, offices, founding year where known, RTP spread, releases by year |
| [`licences.csv`](licences.csv) | provider licences with regulator and licence number, across jurisdictions |
| [`themes.csv`](themes.csv) | theme taxonomy with aliases (entity resolution layer) |
| [`features.csv`](features.csv) | feature taxonomy with aliases |

Field descriptions: [SCHEMA.md](SCHEMA.md). Join on `slot_slug` → `slots.slug` and `provider_slug` → `providers.slug`.

## Get it

- this repository (CSV), or Parquet from [Zenodo](https://doi.org/10.5281/zenodo.24331735)
- `datasets.load_dataset("iGaming/igaming-slot-specs", "slots")` from [Hugging Face](https://huggingface.co/datasets/iGaming/igaming-slot-specs)
- [Kaggle](https://www.kaggle.com/datasets/igamingtools/igaming-slot-specs-rtp-features-accessibility) for notebooks

## Query it live

The monthly snapshot is free. Daily captures, full spec sheets and search demand by country are in the
[REST API](https://i-gaming.tools/docs/quickstart/) (free tier, 10,000 requests a month), or ask an AI agent through the MCP server
`https://mcp.i-gaming.tools/mcp`: no key, no sign-up ([source](https://github.com/igamingtools/igaming-tools-mcp)).
Uptime: [statuspage.i-gaming.tools](https://statuspage.i-gaming.tools/).

## How to cite

CC BY 4.0: use it for anything, including commercially, with credit and a link.

> iGaming Tools (2026). *iGaming Slot Specs* (Version 2026-11-18) [Data set]. Zenodo. https://doi.org/10.5281/zenodo.24331735

[CITATION.cff](CITATION.cff) is read by GitHub's "Cite this repository" button.

## Feedback

Wrong value, missing provider, a field you need? [Open an issue](https://github.com/igamingtools/igaming-slot-specs/issues). Corrections
from people who know the games are the fastest way this dataset gets better.

Not included: screenshots, symbol art and game texts (they belong to the providers).
