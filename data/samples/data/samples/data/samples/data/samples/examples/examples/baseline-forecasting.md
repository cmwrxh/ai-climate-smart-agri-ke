# Baseline Forecasting (Explainable Starter)

This example shows a simple, explainable baseline for climate-smart agriculture analytics using the sample datasets.

## Goal
Provide basic signals:
- rainfall trend (7-day rolling)
- temperature range tracking
- simple “pest risk” heuristic using humidity + recent rain

> This is intentionally simple: teams should start with explainable baselines before complex ML.

---

## Inputs
- `data/samples/weather_daily.csv`
- `data/samples/pest_observation.csv`

---

## 1) Rainfall rolling average (trend)
**Idea:** average rainfall over last N days is often more useful than daily noise.

Pseudo-code:
```python
import pandas as pd

w = pd.read_csv("data/samples/weather_daily.csv")
w["date"] = pd.to_datetime(w["date"])
w = w.sort_values(["county", "date"])

w["rain_rolling_3"] = w.groupby("county")["rain_mm"].rolling(3, min_periods=1).mean().reset_index(level=0, drop=True)
print(w[["county", "date", "rain_mm", "rain_rolling_3"]])
