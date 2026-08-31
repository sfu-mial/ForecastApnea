# Multi-Horizon Forecasting of Apnea and Hypopnea Events from Polysomnographic Signals

[![Paper](https://img.shields.io/badge/IEEE%20JBHI-Paper-blue.svg)](https://ieeexplore.ieee.org/)
[![Python 3.9+](https://img.shields.io/badge/python-3.9+-blue.svg)](https://www.python.org/downloads/)
[![PyTorch 2.0+](https://img.shields.io/badge/PyTorch-2.0+-orange.svg)](https://pytorch.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

Official PyTorch implementation for **"Multi-Horizon Forecasting of Apnea and Hypopnea Events from Polysomnographic Signals"** under review in *IEEE Journal of Biomedical and Health Informatics (JBHI)*.

---

## 📖 Overview

Obstructive Sleep Apnea (OSA) affects nearly one billion individuals globally. Most clinical deep learning methods focus on **retrospective event detection** (identifying events while or after they occur). 

This work introduces a **multi-horizon anticipatory forecasting** framework designed to predict the upcoming onset of apnea and hypopnea events using a compact **10-second input window** of multimodal polysomnography (PSG) signals, including electroencephalography (EEG).
