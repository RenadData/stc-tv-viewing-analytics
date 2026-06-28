# STC Jawwy — Viewing Analytics

A three-part data analytics project on the STC Jawwy TV platform, covering viewer engagement analysis, watch-time forecasting, and a movie recommendation engine.

## Project Overview

| # | Task | What it does | Key technique |
|---|------|---------------|----------------|
| 1 | [Engagement Analysis](./01-engagement-analysis) | Explores how users watch content — movies vs. series, HD vs. SD quality | EDA, pandas, Plotly |
| 2 | [Watch-Time Forecasting](./02-watch-time-forecasting) | Forecasts daily watch-time hours two months ahead | SARIMAX (seasonal time-series forecasting) |
| 3 | [Movie Recommender](./03-movie-recommender) | Recommends similar titles based on user rating patterns | Collaborative filtering, cosine similarity |

## Key Findings

**Engagement Analysis**
- Movies reach ~3x more unique viewers than series (11,355 vs. 3,901), but series content accounts for more than double the total watch-time hours (255,098 vs. 103,444) — a binge-watching pattern among a smaller, more engaged audience.
- SD viewers logged nearly 3x more total watch-time hours than HD viewers (268,364 vs. 90,178) despite HD having more unique users (11,000 vs. 6,728) — worth investigating against device or connection-quality data.

**Watch-Time Forecasting**
- Decomposed the daily watch-time series into trend, seasonal, and residual components.
- Grid-searched SARIMAX parameters and fit a seasonal model (order (0,1,1), seasonal order (0,1,1,12)) to forecast the next 60 days, with confidence intervals widening over the forecast horizon.

**Movie Recommender**
- Built an item-based collaborative filtering recommender using cosine similarity on a user-item rating matrix.
- Example: top 5 recommendations for viewers of *Moana* — Trolls (57.2% match), Surf's Up: WaveMania (52.9%), The Mermaid Princess (49.3%), The Boss Baby (44.9%), The Jetsons & WWE (43.9%) — all genre-coherent animated/family titles, discovered purely from rating behavior with no genre data used as input.

## Tech Stack
`Python` · `pandas` · `numpy` · `statsmodels` (SARIMAX) · `scikit-learn` · `Plotly` · `Matplotlib`

## Repository Structure
stc-tv-viewing-analytics/

├── 01-engagement-analysis/

│   ├── stc_TV_T1.ipynb

│   └── stc_TV_Data_Set_T1.xlsb

├── 02-watch-time-forecasting/

│   ├── stc_TV_T2.ipynb

│   └── stc_TV_Data_Set_T2.xlsx

└── 03-movie-recommender/

├── stc_TV_T3.ipynb

└── stc_TV_Data_Set_T3.xlsx