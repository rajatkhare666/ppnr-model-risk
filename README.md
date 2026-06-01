# ppnr-model-risk
```
# PPNR Model Risk Framework

> End-to-end PPNR forecasting, stress testing and model validation 
> framework built for regulatory stress testing environments (CCAR/DFAST)


---

## Overview

This repository demonstrates an end-to-end workflow for 
Pre-Provision Net Revenue (PPNR) component modelling, 
stress testing and model validation following SR 11-7 
model risk management guidelines.

**Key capabilities:**
- Time series stationarity testing (ADF)
- Cointegration analysis and MEVA pair selection
- VIF-based multicollinearity filtering
- ECM, ARX Level and ARX D1 model development
- Model selection via BIC/AIC with economic diagnostics
- Backtesting and out-of-sample validation
- Stress scenario projection (Baseline, Adverse, Severely Adverse)

---

## PPNR Component Modelled

**NIR Component**

| Attribute | Detail |
|---|---|
| Component type | Non-Interest Revenue (NIR) |
| Target variable | NIR subcomponent combined |
| Key macro driver | ..... |
| Model class selected | .... |
| Selection basis | Economic diagnostics + BIC |
| Known limitation | Error compounding documented (SR 11-7 compliant) |

---

## Methodology

```
Data Preparation & Time Series Indexing
            ↓
ADF Stationarity Test
            ↓
MEVA Correlation Analysis 
            ↓
Cointegration Testing
(combinatorial pairs generated)
            ↓
VIF Filtering (selected pairs survived)
            ↓
Model Estimation
(ECM | ARX Level | ARX D1)
            ↓
Model Selection
(BIC + AIC + Economic Diagnostics)
            ↓
Backtesting (Full historical window)
            ↓
Stress Scenario Projection
(Baseline | Adverse | Severely Adverse)
```

---

## Model Selection Philosophy

Model selection prioritizes **economic diagnostics** 
over pure statistical metrics:

| Priority | Criterion | Rationale |
|---|---|---|
| 1 | Cointegration result | Determines model class |
| 2 | Coefficient sign direction | Economic intuition |
| 3 | Long run stability | 9 quarter horizon requirement |
| 4 | BIC / AIC | Secondary filter within model family |
| 5 | R² | Tertiary check only |

> A model with strong economic foundation and documented 
> limitations is more regulatory defensible than one that 
> optimizes statistical metrics alone. (SR 11-7)

---

## Repository Structure

```
├── notebooks/          # Step by step Jupyter notebooks
│   ├── 1a_data_preparation.ipynb
│   ├── 1b_statistical_tests.ipynb
│   ├── 2a_ecm_estimation.ipynb
│   ├── 2b_arxd1_estimation.ipynb
│   ├── 2c_arxlevel_estimation.ipynb
│   ├── 3a_backtesting.ipynb
│   ├── 3b_forecasting.ipynb
├── src/                # Modular Python source code
├── data/sample/        # Synthetic anonymized sample data
├── reports/            # Model validation summaries
└── requirements.txt
```

---

## Tech Stack

| Tool | Purpose |
|---|---|
| Python 3.9+ | Core language |
| statsmodels | ECM, ARX, cointegration tests |
| pandas | Time series manipulation |
| numpy | Numerical operations |
| matplotlib/seaborn | Visualization |
| scipy | Statistical tests |

---

## Regulatory Framework

- **SR 11-7** - Federal Reserve Model Risk Management
- **CCAR** - Comprehensive Capital Analysis and Review
- **DFAST** - Dodd-Frank Act Stress Test

---

## Notebooks Guide

| Notebook | Content |
|---|---|
| 01a | Data loading, exploration, visualization |

| 01b | ADF stationarity tests, differencing,Cointegration testing, VIF filtering |

| 02 | ECM, ARX Level, ARX D1 model building |

| 03a | Backtesting, actual vs predicted |

| 03b | Stress scenario projections |

---

## Author

**Senior Data Scientist | PhD Applied Mathematics (candidate)**
GCP Data Engineer | PPNR Model Development & Validation
Model Risk | Stress Testing | SR 11-7

---

## Disclaimer

All data used is synthetic or anonymized or available freely over the internet.
No proprietary or confidential information is included.
This repository is for educational and portfolio purposes only.
```
