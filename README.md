# Dynamic Climate-Conditioned Catastrophe Modeling
**Evaluating Non-Stationary Cyclone Tail-Risk via Thermodynamic & Bayesian Constraints**

**Focus:** Catastrophe Modeling | AI Engineering | Spatial Data Analysis  
**Date:** May 2026  

---

## 📌 Project Objective
Standard catastrophe models fundamentally rely on stationary historical baselines (e.g., 1980–2010) to generate Probable Maximum Loss (PML) limits. However, atmospheric physics dictates that the climate is non-stationary. 

This project demonstrates a modernized hazard modeling architecture designed to evaluate how current climate conditions expand extreme tail risks. By integrating localized Sea Surface Temperature (SST) anomalies into a Bayesian Negative Binomial framework and applying Super-Clausius-Clapeyron (Super-CC) scaling to 10,000-year stochastic event sets, this pipeline quantifies the exact expansion of 1-in-100 year severity limits across four critical global basins.

---

## 🏗️ Methodological Framework
1. **Spatio-Temporal Masking:** Utilized a ±1 day temporal buffer around historical IBTrACS storm tracks to isolate true cyclone-induced maximum precipitation in ERA5 data, filtering out ambient seasonal noise.
2. **True VMAX Extraction:** Overcame atmospheric reanalysis dilution by extracting localized peak gust velocities directly from best-track data.
3. **Bayesian Frequency Elasticity:** Deployed `PyMC` to model the non-linear elasticity between cyclogenesis rates ($\mu$) and localized thermodynamic fuel.
4. **Thermodynamic Hazard Scaling:** Applied Maximum Potential Intensity (MPI) and Super-CC constraints to historical distributions to simulate mathematically sound 10,000-year event sets under current SST anomalies.

---

## 📊 Basin-Specific Hazard Analyses

### 1. Gulf of Mexico — Analog: Harvey (2017)
*Observation: Extreme Frequency & Volumetric Expansion*

* **Current Climate Shock:** +0.98°C Anomaly
* **Frequency Shift:** **+21.0%** (Baseline: 2.89 → Current: 3.50 storms/year)
* **Severity Expansion:** * Precipitation Capacity: +9.8% 
    * Wind Capacity: +4.9%
* **Tail-Risk Evaluation (1-in-100 Year):** Simulated peak precipitation reaches **595 mm**, heavily decoupling from the historical maximum observation of 386 mm. 
* **Hazard Profile Shift:** The thermodynamic environment demonstrates a compounding expansion of both frequency and volumetric capacity. The simulated output illustrates a significant divergence between stationary historical severity limits and the current mathematical capacity for coastal and inland precipitation.

### 2. Arabian Sea — Analog: Biparjoy (2023)
*Observation: High Elasticity to Minor Heat Shocks*

* **Current Climate Shock:** +0.22°C Anomaly
* **Frequency Shift:** **+11.7%** (Baseline: 1.45 → Current: 1.62 storms/year)
* **Severity Expansion:** * Precipitation Capacity: +2.2% 
    * Wind Capacity: +1.1%
* **Tail-Risk Evaluation (1-in-100 Year):** Simulated extreme wind reaches **96.11 m/s** (vs. historical 74.59 m/s). Simulated precipitation reaches **192 mm** (vs. historical 122 mm).
* **Hazard Profile Shift:** Despite a relatively modest +0.22°C SST anomaly, the Arabian Sea demonstrates extreme frequency elasticity. The model successfully captures the physical dynamics of a historically low-data basin approaching new thermodynamic thresholds, mapping a distinct upward shift in the 99th percentile wind ceiling.

### 3. South Indian Ocean — Analog: Freddy (2023)
*Observation: Severity Expansion Outpacing Frequency*

* **Current Climate Shock:** +0.60°C Anomaly
* **Frequency Shift:** **-1.4%** (Baseline: 8.49 → Current: 8.38 storms/year)
* **Severity Expansion:** * Precipitation Capacity: +5.9% 
    * Wind Capacity: +3.0%
* **Tail-Risk Evaluation (1-in-100 Year):** Simulated extreme precipitation reaches **1195 mm** (vs. historical 860 mm). Simulated wind speeds reach **83.91 m/s** (vs. historical 74.59 m/s).
* **Hazard Profile Shift:** A slight suppression in overall storm frequency occurs alongside a massive expansion in tail severity. This isolates the specific dynamic where absolute storm counts do not directly correlate with the physical ceiling for flood inundation and localized wind damage.

### 4. Eastern Pacific — Analog: Otis (2023)
*Observation: Validation of Localized Spatial Constraints*

* **Current Climate Shock:** +0.27°C Anomaly
* **Frequency Shift:** **-1.2%** (Baseline: 15.67 → Current: 15.49 storms/year)
* **Severity Expansion:** * Precipitation Capacity: +2.6% 
    * Wind Capacity: +1.3%
* **Tail-Risk Evaluation (1-in-100 Year):** Simulated extreme precipitation reaches **1605 mm** (vs. historical 1179 mm). Simulated wind speeds reach **86.67 m/s** (Historical max: 95.17 m/s).
* **Hazard Profile Shift:** The Eastern Pacific output provides critical validation of the model's spatial constraints. The localized ambient current anomaly (+0.27°C) pushed the 99th percentile wind ceiling to 86.67 m/s, remaining strictly below the historical maximum (Otis at 95.17 m/s). This mathematically isolates the analog event as a statistical outlier that exceeded even modern climate-shocked percentiles, while confirming the structural rise of the volumetric rainfall limit.

---

## 🎯 System Capabilities Demonstrated
This modeling exercise proves the efficacy of moving beyond flat-line historical baselines in risk evaluation. By coupling spatio-temporal satellite data masking with Bayesian inference, the architecture successfully:
1. **Dynamically Tracks Climate Reality:** Proves capability to model non-stationary environments where historical maximums no longer represent the 99th percentile.
2. **Isolates Hazard Vectors:** Effectively separates volumetric flood hazard footprints from standard wind-intensity categorizations, demonstrating that non-major cyclonic events are physically capable of breaching historical precipitation limits.
3. **Applies Physics-Based Constraints:** Utilizes established thermodynamic laws (Super-CC and MPI) to generate synthetic, physically sound event sets for historically sparse or emerging risk basins.
