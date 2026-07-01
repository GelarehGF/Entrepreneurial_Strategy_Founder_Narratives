# Notebooks

## Paper4_Network_Unified.ipynb — Main Analysis Pipeline

**Runtime:** ≈ 8 minutes on Google Colab standard CPU  
**Platform:** Google Colab (recommended) or local Jupyter

### Setup

1. Mount Google Drive
2. Set paths at the top of Cell 1:
   ```python
   BASE_OUT = '/content/drive/MyDrive/Colab Notebooks/IFResearch/Strategy'
   EPISODES = '/content/drive/MyDrive/Colab Notebooks/IFResearch/episodes'
   ```
3. Place your episode transcripts in the `EPISODES` folder as `.docx` or `.txt` files
4. Run all cells

### Output

All outputs are saved to `BASE_OUT/`:

| Output | Description |
|--------|-------------|
| Figures 1–6 | PNG files at 300 DPI |
| Tables 1–8 | Included in `paper4_tables.xlsx` |
| `sentences.csv` | Sentence-level labeled data |
| `labels.csv` | Strategy label instances |
| `episode_clusters.csv` | Cluster assignments |
| `results_summary.json` | Key statistics |

### Pipeline Sections

| Section | Content |
|---------|---------|
| Cell 0 | Package installation |
| Cell 1 | Imports and path configuration |
| Cell 2 | Strategy dictionary (10 categories) |
| Cell 3–4 | Corpus loading and sentence labeling |
| Cell 5 | Sentence-level co-occurrence network (H1) |
| Cell 6–9 | Network construction and visualization |
| Cell 10 | Transition matrix and persistence analysis |
| Cell 11 | Episode-level network (H2) |
| Cell 12–15 | Louvain clustering and profiles |
| Cell 16 | Episode network visualization |
| Cell 17 | Constraint linkage analysis |
| Cell 18–19 | Robustness analysis and summary export |

---

## paper4_validation.ipynb — Single-Coder Validation

**Purpose:** Generate the 200-sentence validation sample and compute Cohen's kappa after coding.

### Workflow

**Section A (run once — before coding):**
1. Set `SENTENCES_CSV` path in Cell A1
2. Run Cells A1–A4 to generate `validation_sample.xlsx`
3. Send `validation_sample.xlsx` to the human coder with `Paper4_Coder_Instructions_v3.docx`

**Coding break (offline):**
- Coder completes Pass A (strict) and Pass B (permissive) for all 200 sentences
- Coder returns `validation_sample_coded.xlsx`

**Section B (run after coding):**
1. Place `validation_sample_coded.xlsx` in the validation output folder
2. Run Cells B1–B4 to compute kappa metrics
3. Results saved to `kappa_results.xlsx`

### Alternative: Local terminal computation

```bash
python scripts/compute_kappa.py --coded /path/to/validation_sample_coded.xlsx
```

---

## Important Notes

- **Never save API keys in notebooks.** Use environment variables or Colab secrets.
- **Random seeds** are fixed at `random_state = 42` throughout for reproducibility.
- **Drive paths** are relative to the user's Google Drive structure; adapt as needed.
