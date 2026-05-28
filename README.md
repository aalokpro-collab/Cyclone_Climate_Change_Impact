# 🌪️ Dynamic Climate-Conditioned Catastrophe Pipeline

**A Bayesian Frequency and Thermodynamic Hazard Engine for Modern Reinsurance Portfolio Pricing.**

![Python](https://img.shields.io/badge/Python-3.12-blue?logo=python)
![PyMC](https://img.shields.io/badge/PyMC-Bayesian_Inference-red?logo=python)
![GEE](https://img.shields.io/badge/Google_Earth_Engine-Atmospheric_Reanalysis-green?logo=google)
![Status](https://img.shields.io/badge/Status-Production_Ready-success)

## 📌 Executive Summary
Traditional catastrophe models share a critical vulnerability: they price modern accumulation risk using a stationary historical baseline (e.g., 1980–2010). However, the climate is non-stationary. Pricing Probable Maximum Loss (PML) limits against 40-year historical averages structurally underprices extreme tail risk in the current warming regime.

This project represents a complete architectural overhaul of how cyclone hazard is modeled. It shifts from empirical historical lookbacks to **physics-based thermodynamic capacity**, integrating localized Sea Surface Temperature (SST) anomalies into a **Bayesian Negative Binomial MCMC engine**, and applying **Super-Clausius-Clapeyron** scaling to 10,000-year stochastic event sets. 

**Core Finding:** The mathematical reality of 2026 is that the historical 99th percentile extreme is rapidly becoming the standard active season. The models prove significant hazard footprint expansions, specifically in the **Gulf of Mexico (+21.5% frequency shift)** and the **Arabian Sea (+11.7% frequency shift)**.

---

## 🏗️ Pipeline Architecture

This pipeline is built in three distinct phases, bridging the gap between raw atmospheric reanalysis and actuarial treaty pricing:

### Phase 1: Geospatial & Atmospheric Data Engineering
* **Data Sources:** NOAA IBTrACS (Best Track data) and Google Earth Engine (ERA5-Land / OISST).
* **Spatio-Temporal Masking:** Built a ±1 day temporal buffer around specific historical storm tracks to perfectly isolate cyclone-induced maximum precipitation, mathematically stripping out ambient monsoon and atmospheric river noise.
* **True VMAX Extraction:** Overcame atmospheric dilution by pulling localized peak gust velocity directly from IBTrACS, rather than relying on basin-wide ERA5 ambient wind averages.

### Phase 2: Bayesian Frequency Engine
* **Model:** Bayesian Negative Binomial Regression (`PyMC`).
* **Logic:** Models the non-linear elasticity between cyclogenesis and thermodynamic fuel (SST anomalies & Dewpoint Depression).
* **Validation:** Achieved mathematically sound convergence (`r_hat` = 1.00) and generated Posterior Predictive Checks that dynamically trace the volatile peaks and valleys of extreme seasons, proving the model dynamically tracks climate reality rather than flatline averages.

### Phase 3: Thermodynamic Hazard Scaling (Severity Expansion)
* **Precipitation:** Applied **Super-Clausius-Clapeyron (Super-CC)** scaling (+10% volumetric capacity per +1.0°C anomaly) to simulated lognormal distributions.
* **Wind Speed:** Applied **Maximum Potential Intensity (MPI)** scaling (+5% velocity per +1.0°C anomaly) to extreme value distributions.
* **Result:** A 10,000-year Monte Carlo simulated event set that explicitly maps the "Shocked 99th Percentile" against the immutable Historical Maximums, quantifying the exact dollar-value gap in un-modeled risk.

---

## 📊 Key Actuarial Findings

| Basin | Analog Event | SST Shock | $\mu$ Shift | 99th Pctl Volumetric Penalty | Commercial Implication |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Gulf of Mexico** | Harvey (2017) | +0.98°C | +21.5% | +9.8% | Requires immediate recalibration of US Gulf Coast inland flood exclusions. |
| **Arabian Sea** | Biparjoy (2023) | +0.22°C | +11.7% | +2.2% | Emerging risk vector. High elasticity to minor heat anomalies threatens un-modeled Indian west-coast exposures. |
| **Eastern Pacific** | Otis (2023) | +0.27°C | -0.7% | +2.6% | Validates spatial precision; local cooling downgraded frequency, but severity tail risk still expanded past historical ceilings. |
| **South Indian** | Freddy (2023) | +0.60°C | -1.1% | +5.9% | Proves the "Wind vs. Water" paradox: Severity expansion outpaces frequency shifts. |

---

## 📈 Core Visualizations (Available in `/output`)

1. **Hazard Tail-Risk Expansion (`hazard_tail_risk_expert.png`):** The "smoking gun" plot. Explicitly overlays the historical maximums (solid black) against the climate-shocked 99th percentile (dashed red) to visualize how modern physics has decoupled from historical limits.
2. **Complete Hazard Anatomy (`complete_hazard_anatomy.png`):** A multi-axis visualization proving the correlation between SST Anomaly (Fuel), Peak VMAX Wind (Intensity), and true Cyclone-Induced Precipitation (Footprint), while visually proving that weaker wind storms can produce catastrophic flood events.
3. **Posterior Predictive Tracking (`time_series_fit.png`):** Validates the Bayesian engine's dynamic response to yearly localized marine heatwaves.

---

## 🚀 Setup & Execution

### Prerequisites
* Python 3.10+
* Google Earth Engine API Access (`earthengine-api`)

### Installation
```bash
git clone [https://github.com/aalokpro-collab/Cyclone_Climate_Change_Impact.git](https://github.com/aalokpro-collab/Cyclone_Climate_Change_Impact.git)
cd Cyclone_Climate_Change_Impact
