# AquaSafeTwin

**A Risk-Aware Multimodal Digital Twin for Aquaculture: Agentic AI for Safe Decision Support**

AquaSafeTwin is a research-oriented framework for integrating fish behaviour analysis, water-quality monitoring, multimodal digital twins, and risk-aware AI agents to support safer and more reliable aquaculture operations.

## Overview

Modern aquaculture facilities generate heterogeneous information from environmental sensors, underwater cameras, and operational monitoring systems. However, transforming these observations into reliable management decisions remains challenging, particularly when measurements are incomplete, uncertain, or inconsistent.

AquaSafeTwin investigates how multimodal digital twins and AI agents can jointly support predictive monitoring and risk-informed decision-making.

The framework emphasizes independent safety verification before AI-generated recommendations are presented to human operators.

## Research Objectives

1. Develop multimodal representations integrating underwater fish videos and water-quality measurements.
2. Investigate temporal prediction and uncertainty estimation for aquaculture monitoring.
3. Design AI agents capable of generating context-aware operational recommendations.
4. Introduce independent safety checks for risk-sensitive recommendations.
5. Evaluate predictive accuracy, robustness, and safety-constraint compliance using reproducible experiments.

## Proposed Architecture

```text
Underwater Video       Water-Quality Sensors
       |                       |
       v                       v
Fish Behaviour         Environmental State
   Analysis                Estimation
       |                       |
       +-----------+-----------+
                   |
                   v
         Multimodal Digital Twin
                   |
                   v
          AI Decision Agent
                   |
                   v
       Independent Safety Verifier
                   |
                   v
        Human-Reviewed Decision
```

## Project Structure

```text
AquaSafeTwin/
├── configs/
├── data/
├── docs/
├── experiments/
├── notebooks/
├── paper/
├── results/
├── src/
│   └── aquasafetwin/
├── tests/
├── README.md
├── requirements.txt
└── pyproject.toml
```

## Installation

Clone the repository:

```bash
git clone https://github.com/YOUR_USERNAME/AquaSafeTwin.git
cd AquaSafeTwin
```

Create a virtual environment and install dependencies:

```bash
python -m venv .venv
source .venv/bin/activate
pip install -e .
```

On Windows, activate the environment using:

```powershell
.venv\Scripts\activate
```

## Running Initial Experiments

Generate demonstration data:

```bash
python experiments/make_demo_data.py
```

Run the baseline experiment:

```bash
python experiments/run_baselines.py \
  --csv data/processed/SYNTHETIC_demo.csv \
  --timestamp timestamp \
  --target dissolved_oxygen \
  --water temperature ph \
  --video mean_speed dispersion \
  --lookback 6 \
  --horizon 1
```

Run automated tests:

```bash
python -m pytest -q
```

**Note:** Synthetic demonstration data are provided only to test the experimental pipeline. They must not be interpreted as real aquaculture measurements.

## Research Datasets

The research considers publicly available aquaculture datasets containing underwater video recordings, fish-behaviour information, and environmental sensor measurements.

A primary candidate is:

**Video Footage of Fish and Water Quality Variables in a Fish Farming Scenario**

https://doi.org/10.25452/figshare.plus.19653321.v2

Additional datasets may be used for external validation.

Original datasets are not redistributed in this repository. Users should consult the original repositories for access conditions and citation requirements.

## Experimental Evaluation

The planned experiments include:

- Water-quality forecasting using conventional and machine-learning baselines.
- Fish-behaviour feature extraction from underwater video.
- Comparison of unimodal and multimodal predictive models.
- Robustness testing under missing or corrupted observations.
- Risk-aware decision evaluation against rule-based and unconstrained approaches.
- Independent safety-verification analysis.

Evaluation metrics include MAE, RMSE, precision, recall, F1-score, uncertainty calibration, and safety-constraint violation rate.

## Research Status

This repository is under active research development.

The initial software structure, baseline pipeline, and safety-verification components are available. Full multimodal integration and real-data experimental validation remain ongoing.

No claims of improved fish welfare, operational efficiency, or intervention effectiveness are made without corresponding experimental evidence.

## Publication

**Working paper title:**

*A Risk-Aware Multimodal Digital Twin for Aquaculture: Agentic AI for Safe Decision Support*

**Target venue:** ACM Symposium on Applied Computing (SAC 2027)

The manuscript and experimental framework are being developed together to support transparent and reproducible research.

## Reproducibility

The project aims to provide:

- Documented experimental configurations.
- Chronological data partitioning.
- Reproducible preprocessing.
- Clearly identified synthetic and real datasets.
- Baseline implementations.
- Automated software tests.
- Traceable experimental results.

## Safety Disclaimer

AquaSafeTwin is a research prototype, not a certified aquaculture control system.

AI-generated recommendations must not be used to control physical aquaculture equipment or make animal-welfare-critical decisions without appropriate validation and qualified human supervision.

## License

The original software is intended to be distributed under the MIT License. Third-party datasets, publications, and external components retain their respective licenses.

## Citation

Citation information will be updated following publication of the research paper.
