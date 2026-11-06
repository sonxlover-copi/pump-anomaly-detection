# Pump Anomaly Detection

An offline anomaly detection laboratory built around industrial sensor time series. The workflow compares classical detectors and forecast-based signals, selects a configuration on validation data, then reports a frozen holdout evaluation.

## What it covers

- Causal rolling and robust time-series features
- Robust-statistics, PCA, and Isolation Forest detectors
- Forecast diagnostics and score fusion
- Validation-based threshold selection
- Point- and event-level evaluation on a separate holdout

## Run locally

Python 3.10 or newer is recommended. Chronos-2 may require a compatible PyTorch build and additional model weights on first use. Create an environment and install the dependencies:

```bash
python -m venv .venv
source .venv/bin/activate  # Windows: .venv\Scripts\activate
python -m pip install -r requirements.txt
jupyter lab
```

Open `pump_anomaly_detection.ipynb` and run all cells. The notebook contains the small verified runtime assets needed for its offline laboratory workflow; the forecast model may need to be downloaded depending on the selected execution path.

## Validation

The recorded run selected `ensemble_mean` on validation data. Validation average precision / F1 / coverage were 0.877 / 0.520 / 0.406; holdout values were 0.921 / 0.514 / 0.358. The normal-data alarm fraction was 0.010 on validation and 0.001 on holdout.

## Attribution

This is an adapted solution to an educational laboratory. The original assignment, data, and model attribution should be retained when redistributing the notebook.
