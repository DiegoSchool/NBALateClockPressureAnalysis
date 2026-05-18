# NBA Late Clock Pressure Analysis

## Overview

This project explores whether NBA teams that force more late-clock offensive disruption tend to have stronger overall defense.

To investigate this, I created a custom metric called the **Late Clock Pressure Index (LCPI)** that combines:
- shot-clock violations forced
- pressure-related turnovers forced
- difficult/desperation missed shots forced

The project compares these metrics against team Defensive Rating (DRtg) using standardized z-scores and correlation analysis.

---

## Motivation

Shot-clock violations alone are relatively rare and may not fully capture defensive pressure. This project attempts to broaden the definition of late-clock defensive disruption by incorporating additional pressure-related outcomes from play-by-play data.

The goal is to better understand whether forcing difficult late-clock possessions is associated with stronger defensive performance overall.

---

## Methods

### Data Sources
- NBA play-by-play data
- Team defensive statistics
- NBA API endpoints via `nba_api`

### Key Techniques
- Play-by-play event filtering
- Possession normalization
- Z-score standardization
- Correlation analysis
- Data visualization with Plotly

### Standardization

The metrics in this project exist on different numerical scales, making direct comparison difficult. To address this, I standardized the variables using z-scores:

z = (x - μ) / σ

This allows all metrics to be compared relative to league average performance and helps evaluate their relationship with defensive rating on a common scale.

---

## Late Clock Pressure Index (LCPI)

The LCPI metric is designed to capture multiple forms of defensive late-clock disruption:

- Shot-clock violations forced
- Pressure turnovers forced
- Difficult/desperation missed shots forced

The metric expands beyond traditional shot-clock violations alone in order to better represent defensive pressure that affects offensive possessions late in the shot clock.

---

## Key Findings

- Shot-clock violations alone showed only a modest relationship with defensive rating.
- The broader LCPI metric demonstrated a stronger negative correlation with defensive rating.
- Teams with stronger late-clock pressure metrics generally tended to allow fewer points per 100 possessions.

Because lower Defensive Rating values indicate stronger defense, negative correlations with LCPI represent positive defensive relationships.

---

## Limitations

This project is exploratory and has several limitations:

- Some “desperation shot” classifications are inferred heuristically from play-by-play text.
- Metric weights are manually selected rather than model-optimized.
- Correlation does not imply causation.
- Possession estimates are simplified approximations.
- Playoff and regular season data may both be included depending on the dataset version.

---

## Future Improvements

Potential future extensions include:

- Incorporating true shot-clock timestamps
- Optimizing LCPI weighting schemes
- Separating regular season and playoff data
- Building predictive models using possession-level features
- Adding lineup and player-level analysis

---

## Technologies Used

- Python
- pandas
- NumPy
- Plotly
- nba_api
- SciPy

---

## Project Goal

The purpose of this project is to explore how custom basketball analytics metrics can be built from raw play-by-play data and evaluated using statistical methods.

This project also serves as part of my broader sports analytics and data science portfolio.
