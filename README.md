# CMS Open Data Project: H → WW Analysis (Publication-Ready Code)

> **Publication-ready analysis code** from the [H-to-WW-nanoaod-analysis](https://github.com/anujraghav252/H-to-WW-nanoaod-analysis) repository.

This repository contains the finalized, publication-ready codes for the analysis of Higgs boson decays to **W boson pairs (H → WW → 2ℓ2ν)** using CMS Open Data in the NanoAOD format. This is part of the **HSF-India project** and focuses on the **gluon-gluon fusion (ggH)** production mode with **2016 Ultra-Legacy Monte Carlo** samples at **√s = 13 TeV**.

---

## Repository Contents

This repository includes the essential components required to reproduce the published H → WW analysis:

### 📊 Main Analysis
- **`HWW_analysis.ipynb`** — Complete end-to-end analysis notebook containing:
  - Sample loading and preprocessing
  - Object and event selection
  - Kinematic distributions
  - Data/MC scale factors application
  - Signal-background comparisons

### 🐍 Analysis Tools (`hww_tools/`)
Production-ready Python package with modular analysis components:
- **`processor.py`** — Main Coffea processor for event processing
- **`Physics_selection.py`** — Physics object and event selection criteria
- **`Efficiency_data.py`** — Efficiency and scale factor handling
- **`plotting.py`** — Standardized plotting utilities with CMS styling
- **`cross_section.py`** — Cross-section and normalization calculations
- **`helper.py`** — Utility functions for data handling
- **`Config.py`** — Configuration management
- **`calculations.py`** — Physics calculations and computations
- **`cuts.py`** — Cut definitions and utilities
- **`cutflow_utils.py`** — Cutflow table generation
- **`json_validation.py`** — Data certification validation
- **`dask_utils.py`** — Distributed computing utilities

### 📁 Supporting Data (`Auxillary_files/`)
Critical input files for the analysis:

#### Efficiencies (`Auxillary_files/Efficiencies/`)
- **`Eff_note.txt`** — Trigger efficiency documentation (91.29 ± 0.08%)
- **`Muon_tight_Eff.txt`** — Muon tight-ID efficiency & scale factors
- **`Muon_ISO_Eff.txt`** — Muon isolation efficiency & scale factors
- **`egammaEffi_TightHWW_2016.txt`** — Electron TightHWW ID efficiency & scale factors

#### Additional Files
- **`Cert_271036-284044_13TeV_Legacy2016_Collisions16_JSON.txt`** — Golden JSON for 2016 data
- **`NUM_TightHWW_DEN_TrackerMuons_eta_pt.root`** — Muon ID scale factor ROOT file
- **`NUM_TightHWW_ISO_DEN_TightHWW_eta_pt.root`** — Muon ISO scale factor ROOT file

### 📚 Dataset Information (`Datasets/`)
- **`README_MC_Samples_2016UL.md`** — Complete listing of MC samples with cross-sections
- **`Summer20UL16_106x_noHIPM_nAODv9.py`** — NanoAOD sample paths and metadata

### 📖 Documentation
- **`Higgs.md`** — Extended physics notes on Higgs boson properties and analysis strategy

---

## Physics Overview

The **Higgs boson**, discovered in 2012 at the LHC, is responsible for giving mass to elementary particles through electroweak symmetry breaking. This analysis focuses on:

- **Production mode:** Gluon-gluon fusion (ggH)
- **Decay channel:** H → WW* → eμ + 2ν (opposite-flavor dilepton final state)
- **Data:** CMS 2016 Ultra-Legacy Monte Carlo (√s = 13 TeV)

This channel provides a clean leptonic signature with a sizeable branching fraction, making it crucial for Higgs property measurements.

---

## Quick Start

### 1. Clone the Repository

```bash
git clone https://github.com/anujraghav252/CMS-Open-Data-Project-HWW.git
cd CMS-Open-Data-Project-HWW
```

### 2. Set Up the Environment

**Option A — pip (virtual environment):**

```bash
python3 -m venv .venv
source .venv/bin/activate        # Linux / macOS
# .venv\Scripts\activate         # Windows
pip install -r requirements.txt
```

**Option B — Conda:**

```bash
conda env create -f environment.yml
conda activate hww-analysis
```

### 3. Run the Analysis

Open the main analysis notebook:

```bash
jupyter lab HWW_analysis.ipynb
```

---

## Dependencies

The analysis is built on the modern Python HEP ecosystem:

- **Data I/O:** `uproot`, `awkward`, `fsspec-xrootd`
- **Analysis:** `coffea`, `hist`, `vector`, `scipy`
- **Computing:** `numpy`, `pandas`, `dask`
- **Visualization:** `matplotlib` (with `mplhep` CMS styling)
- **Environment:** `jupyterlab`, `ipywidgets`

See [`requirements.txt`](requirements.txt) for the complete dependency list.

---

## Repository Structure

```
CMS-Open-Data-Project-HWW/
│
├── HWW_analysis.ipynb              # Main analysis notebook
│
├── hww_tools/                      # Analysis Python package
│   ├── processor.py                # Coffea event processor
│   ├── Physics_selection.py        # Object & event selection
│   ├── Efficiency_data.py          # Efficiency handling
│   ├── plotting.py                 # Plotting utilities
│   ├── cross_section.py            # Cross-section calculations
│   ├── helper.py                   # Helper functions
│   ├── Config.py                   # Configuration
│   ├── calculations.py             # Physics calculations
│   ├── cuts.py                     # Cut definitions
│   ├── cutflow_utils.py            # Cutflow utilities
│   ├── json_validation.py          # Data validation
│   ├── dask_utils.py               # Dask utilities
│   ├── Plots_config.py             # Plot configuration
│   └── __init__.py                 # Package initialization
│
├── Auxillary_files/                # Supporting input files
│   ├── Efficiencies/               # Efficiency scale factors
│   │   ├── Eff_note.txt
│   │   ├── Muon_tight_Eff.txt
│   │   ├── Muon_ISO_Eff.txt
│   │   └── egammaEffi_TightHWW_2016.txt
│   ├── Cert_271036-284044_13TeV_Legacy2016_Collisions16_JSON.txt
│   ├── Muon_ISO_Eff.txt
│   ├── Muon_tight_Eff.txt
│   ├── egammaEffi_TightHWW_2016.txt
│   ├── NUM_TightHWW_DEN_TrackerMuons_eta_pt.root
│   └── NUM_TightHWW_ISO_DEN_TightHWW_eta_pt.root
│
├── Datasets/                       # MC sample information
│   ├── README_MC_Samples_2016UL.md
│   └── Summer20UL16_106x_noHIPM_nAODv9.py
│
├── requirements.txt                # Python dependencies
├── environment.yml                 # Conda environment
├── Higgs.md                        # Extended physics notes
└── README.md                       # This file
```

---

## Citation and Acknowledgements

This analysis is developed as part of the **HSF-India project**, fostering research software collaborations between India and the international High Energy Physics community.

If you use this code, please cite:
- The original analysis repository: [H-to-WW-nanoaod-analysis](https://github.com/anujraghav252/H-to-WW-nanoaod-analysis)
- CMS Open Data: [CERN Open Data Portal](http://opendata.cern.ch/)

---

## Source Repository

For development history and additional notebooks, see the source repository:
- **Source:** [H-to-WW-nanoaod-analysis](https://github.com/anujraghav252/H-to-WW-nanoaod-analysis)
- **This repo:** Publication-ready code extracted from the source repository

---

## License

This project uses CMS Open Data, which is released under the Creative Commons CC0 waiver.