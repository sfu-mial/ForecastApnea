# Multi-Horizon Forecasting of Apnea and Hypopnea Events from Polysomnographic Signals

> **Status:** 🚧 Paper under review. Code and data will be released upon publication. 🚧

This repository accompanies the manuscript:

**"Multi-Horizon Forecasting of Apnea and Hypopnea Events from Polysomnographic Signals"**
Gurleen Kaur, Mohammadreza Hajipour, AJ Marcus Hirsch Allen, Najib T. Ayas, and Ghassan Hamarneh
*Submitted to IEEE Journal of Biomedical and Health Informatics*

## Authors and Affiliations

- **Gurleen Kaur** — School of Computing Science, Simon Fraser University, Burnaby, BC, Canada (gka82@sfu.ca)
- **Mohammadreza Hajipour** — Brigham and Women's Hospital, Harvard Medical School, Harvard University, Boston, MA, USA (mhajipour@bwh.harvard.edu)
- **AJ Marcus Hirsch Allen** — Department of Medicine, University of British Columbia, Vancouver, BC, Canada (ajhirschallen@gmail.com)
- **Najib T. Ayas** — Department of Medicine, University of British Columbia, Vancouver, BC, Canada (najib.ayas@vch.ca)
- **Ghassan Hamarneh**, *Senior Member, IEEE* — School of Computing Science, Simon Fraser University, Burnaby, BC, Canada (hamarneh@sfu.ca)

## Overview

Obstructive sleep apnea (OSA) is a prevalent sleep-related breathing disorder affecting nearly one billion people worldwide. While polysomnography (PSG) is the clinical gold standard for *detecting* apnea and hypopnea events after they occur, this work explores whether such events can be **forecast before onset** to support anticipatory intervention.

We formulate apnea/hypopnea prediction as a **multi-horizon binary time-series classification task** and propose a hybrid deep learning architecture that fuses:
- **Learned spectral-temporal EEG representations** (via an EEGNet-inspired CNN pipeline), and
- **Hand-crafted physiological descriptors** (band-power, spectral statistics, and wavelet features)

through a **cross-attention fusion mechanism**.

## Key Contributions

- A rigorous **multi-horizon forecasting formulation** (Δ ∈ {5, 10, 20, 30} seconds) with explicit post-event exclusion and guard-margin constraints, distinguishing true pre-event forecasting from during-event detection.
- A **cross-attention fusion architecture** combining CNN-based and analytical (hand-crafted) feature branches.
- Evaluation on **477 full-night PSG recordings** (University of British Columbia dataset) using subject-wise cross-validation — a substantially larger and more diverse cohort than prior EEG-inclusive forecasting studies.
- **Interpretability analysis** via SHAP to characterize channel-level contributions (e.g., nasal pressure, respiratory effort, EEG).
- **Uncertainty-based selective prediction (abstention)** to improve reliability on high-confidence subsets.

## Results Summary

| Horizon (Δ) | F1 Score | Accuracy (%) |
|---|---|---|
| 5 s | 0.73 | 71.44 |
| 10 s | 0.71 | 69.56 |
| 20 s | 0.68 | 64.06 |
| 30 s | 0.69 | 63.50 |

Performance is highest near event onset and decreases gracefully as the forecasting horizon increases, consistent with the expected reduction in available predictive signal at longer lead times.

## Dataset

This study uses a **private clinical PSG dataset** provided by the University of British Columbia (477 full-night recordings). The dataset is not publicly available due to privacy and institutional data-sharing restrictions.

## Repository Structure (planned)

```
.
├── data/            # Data loading and preprocessing scripts (dataset not included)
├── models/          # Model architecture definitions (EEGNet branch, analytical branch, cross-attention fusion)
├── training/        # Training and cross-validation scripts
├── analysis/        # SHAP interpretability and abstention/calibration analysis
└── README.md
```

*(Structure subject to change as the code release is finalized.)*

## Citation

A formal citation will be added once the paper is accepted/published. In the meantime, please reach out to the corresponding authors for reference details, or use the placeholder BibTeX entry below (update once accepted):

```bibtex
@article{kaur2026multihorizon,
  title   = {Multi-Horizon Forecasting of Apnea and Hypopnea Events from Polysomnographic Signals},
  author  = {Kaur, Gurleen and Hajipour, Mohammadreza and Hirsch Allen, AJ Marcus and Ayas, Najib T. and Hamarneh, Ghassan},
  journal = {IEEE Journal of Biomedical and Health Informatics},
  year    = {2026},
  note    = {Under review},
}
```

## Contact

- Gurleen Kaur — gka82@sfu.ca
- Ghassan Hamarneh — hamarneh@sfu.ca

## Acknowledgments

This work was supported by computational resources from the Digital Research Alliance of Canada.

---

*This README is a placeholder and will be updated with full documentation, setup instructions, and code upon completion of the peer-review process.*
