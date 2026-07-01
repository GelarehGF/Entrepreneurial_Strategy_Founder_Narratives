# Entrepreneurial Strategy as Configuration: A Network Analysis of Founder Narratives

[![Python 3.10+](https://img.shields.io/badge/python-3.10+-blue.svg)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Google Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/)

**Authors:** Gelareh Farhadian · Faezeh S. Aarabi  
**Affiliations:** Fairleigh Dickinson University Vancouver · University Canada West  
**Contact:** farhadiangelareh@gmail.com

---

## Overview

This repository contains the complete computational pipeline, codebooks, validation materials, and analysis notebooks for the paper:

> **Entrepreneurial Strategy as Configuration: A Network Analysis of Founder Narratives**

The study analyzes 124 founder podcast episodes (38,508 sentences) from the Innovation Fuel dataset using dictionary-based labeling, network analysis, and Louvain community detection to test whether entrepreneurial strategies form systematic configurations.

### Key Findings

| Result | Value |
|--------|-------|
| Corpus size | 124 episodes · 38,508 sentences |
| Strategy-labeled sentences | 658 (1.71%) |
| Constraint-labeled sentences | 5,450 (14.15%) |
| Episode network modularity | 0.191 |
| Cluster robustness (ARI) | ≥ 0.90 across thresholds 0.4–0.6 |
| Constraint linkage χ² | 96.08, df = 54, p = .0004 |
| Within-coder kappa (validation) | 0.764 (substantial) |

### Four Founder Configurations Identified

| Configuration | n | Dominant Strategy | Shannon Diversity |
|---------------|---|-------------------|-------------------|
| Coalitional founders | 51 (42.1%) | Partnering (0.747) | 0.491 |
| Operational scalers | 35 (28.9%) | Scaling (0.407) | 0.789 |
| Iterative builders | 14 (11.6%) | Experimentation (0.507) | 0.941 |
| Adaptive repositioners | 21 (17.4%) | Pivot (0.445) | 1.074 |

---

## Repository Structure

```
Entrepreneurial_Strategy_Founder_Narratives/
│
├── README.md                          ← This file
├── LICENSE                            ← MIT License
├── requirements.txt                   ← Python dependencies
├── .gitignore
│
├── notebooks/
│   ├── Paper4_Network_Unified.ipynb   ← Main analysis pipeline (Google Colab)
│   ├── paper4_validation.ipynb        ← Single-coder two-pass validation
│   └── README.md
│
├── scripts/
│   └── compute_kappa.py               ← Local terminal kappa computation
│
├── codebook/
│   ├── strategy_codebook.md           ← 10-category strategy codebook
│   ├── constraint_codebook.md         ← 7-category constraint codebook
│   └── README.md
│
├── data/
│   └── README.md                      ← Data availability statement
│
└── outputs/
    └── README.md                      ← Output file descriptions
```

---

## Quick Start

### 1. Clone the repository

```bash
git clone https://github.com/GelarehGF/Entrepreneurial_Strategy_Founder_Narratives.git
cd Entrepreneurial_Strategy_Founder_Narratives
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Run the main analysis

Open `notebooks/Paper4_Network_Unified.ipynb` in Google Colab:

1. Mount your Google Drive
2. Set `BASE_OUT` and `EPISODES` paths to your corpus location
3. Run all cells (≈ 8 minutes on standard CPU runtime)

The notebook reproduces all tables and figures from the manuscript.

### 4. Run validation (after coding)

```bash
# Generate the 200-sentence validation sample
# Open notebooks/paper4_validation.ipynb in Colab and run Cells A1–A4

# After the coder returns validation_sample_coded.xlsx:
python scripts/compute_kappa.py --coded /path/to/validation_sample_coded.xlsx
```

---

## Data

### Innovation Fuel Podcast Dataset

The Innovation Fuel podcast is publicly available at:  
🎙️ [www.ucanwest.ca/innovation-fuel](https://www.ucanwest.ca/innovation-fuel)

The dataset used in this study comprises **124 episodes** with founder transcripts. Transcripts were obtained from the publicly available podcast feed and preprocessed for sentence-level analysis.

### Corpus Statistics

| Metric | Value |
|--------|-------|
| Total episodes | 124 |
| Episodes with strategy labels | 121 (3 excluded, zero labels) |
| Total sentences | 38,508 |
| Mean sentences per episode | 310 (SD = 142; range 78–982) |
| Strategy label instances | 666 across 658 sentences |
| Constraint label instances | 5,450 across 5,450 sentences |

See `data/README.md` for full data availability statement and intermediate file descriptions.

---

## Codebooks

### Strategy Codebook (10 categories · 251 phrases)

| Category | Core concept | Example phrases |
|----------|-------------|-----------------|
| `pivot` | Fundamental business-model redirection | "pivoted," "changed direction," "scrapped the idea" |
| `experimentation` | Small-scale trial before commitment | "tested," "prototype," "minimum viable product" |
| `customer_discovery` | Direct engagement with buyers to validate demand | "talked to customers," "user research," "validated demand" |
| `resource_substitution` | Using at-hand resources unconventionally | "made do," "bootstrapped," "improvised" |
| `sequencing` | Deliberate ordering of strategic moves | "phase one," "step by step," "we waited until" |
| `scaling` | Growing volume, geography, or team | "scaled up," "expanded," "hired more" |
| `optimization` | Improving efficiency without changing the model | "streamlined," "reduced cost," "repeatable process" |
| `capability_building` | Developing new skills or organizational capacity | "learned how to," "built expertise in," "trained the team" |
| `partnering` | Collaborative external relationships | "partnered with," "joint venture," "teamed up" |
| `legitimation` | Establishing credibility with external audiences | "built credibility," "recognized as," "certification" |

Full codebook with all 251 phrases: see `codebook/strategy_codebook.md`

### Constraint Codebook (7 categories · 130 phrases)

| Category | Definition |
|----------|-----------|
| `financial` | Credit, funding, capital, affordability |
| `market` | Customer demand, competition, adoption |
| `institutional` | Regulation, law, policy, compliance |
| `capability` | Internal knowledge, expertise, learning |
| `talent` | Hiring, recruiting, retaining people |
| `network` | Connections, partnerships, ecosystem access |
| `self_imposed` | Voluntary limits from values, ethics, mission |

Full codebook: see `codebook/constraint_codebook.md`

---

## Methods

### Pipeline Architecture

```
Raw transcripts (124 episodes)
        │
        ▼
Sentence boundary detection (38,508 sentences)
        │
        ├── Strategy labeling (regex, 10 categories)
        │       └── 658 labeled sentences (1.71%)
        │
        ├── Constraint labeling (regex, 7 categories)
        │       └── 5,450 labeled sentences (14.15%)
        │
        ├── H1: Sentence-level co-occurrence network
        │       └── Result: REJECTED (sparse, disconnected at all thresholds)
        │
        └── H2: Episode-level similarity network
                ├── Cosine similarity matrix (121 × 121)
                ├── Louvain clustering (modularity = 0.191)
                ├── 4 clusters identified (ARI ≥ 0.90 across thresholds)
                ├── Persistence analysis (convergent validation)
                └── Constraint linkage (χ² = 96.08, p = .0004)
```

### Software Stack

| Library | Version | Purpose |
|---------|---------|---------|
| pandas | 2.0+ | Data manipulation |
| numpy | 1.24+ | Numerical computation |
| networkx | 3.1+ | Network construction |
| python-louvain | 0.16+ | Community detection |
| scikit-learn | 1.3+ | Cosine similarity, ARI |
| scipy | 1.11+ | Chi-square tests |
| matplotlib | 3.7+ | Visualization |
| seaborn | 0.12+ | Heatmaps |
| python-docx | 0.8+ | Document handling |
| openpyxl | 3.1+ | Excel output |

---

## Validation

### Single-Coder Two-Pass Methodology

Following Farhadian (2025), codebook validation uses a single coder who reviews full episode audio and transcripts before completing two coding passes:

- **Pass A (strict):** Label only when strategy is explicit and unambiguous
- **Pass B (permissive):** Label when discourse plausibly points to the strategy

| Comparison | κ | n | Interpretation |
|------------|---|---|----------------|
| Pass A vs. Pass B | 0.764 | 200 | Substantial |
| Pass A vs. Regex | 0.244 | 200 | Fair |
| Pass B vs. Regex | 0.286 | 200 | Fair |

**Per-category kappa (Pass A vs. Pass B):** range 0.650–0.939; all categories at substantial or near-perfect agreement.

---

## Reproducibility

The full pipeline is deterministic given the input corpus:

- All random seeds are fixed at `random_state = 42`
- All threshold choices are reported and swept in the robustness analysis
- The notebook runs end-to-end in ≈ 8 minutes on Google Colab standard CPU

### JNDI Statement

All intermediate analysis outputs are deterministic functions of the input corpus and published code. Intermediate files (≈ 15 MB) are not separately deposited to avoid redundancy; they are regenerated in seconds by running the notebook. Researchers requiring specific intermediate outputs may contact the corresponding author.

---

## Citation

If you use this code or methodology in your research, please cite:

```bibtex
@article{farhadian2025entrepreneurial,
  title     = {Entrepreneurial Strategy as Configuration: A Network Analysis of Founder Narratives},
  author    = {Farhadian, Gelareh and Aarabi, Faezeh S.},
  journal   = {[Journal]},
  year      = {2025},
  note      = {Under review}
}
```

---

## License

This project is licensed under the MIT License — see [LICENSE](LICENSE) for details.

---

## Acknowledgements

The authors thank the Innovation Fuel team at University Canada West for making the podcast corpus publicly available, and the human coder who contributed to the validation study.
