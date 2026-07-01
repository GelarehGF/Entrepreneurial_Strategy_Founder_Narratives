# Outputs

This directory is populated by running the analysis notebooks. It is empty in the repository (see `.gitignore`).

## Expected Output Files

### Figures (PNG, 300 DPI)

| File | Description |
|------|-------------|
| `fig1_null_result.png` | Strategy network density and isolation across thresholds (Figure 1) |
| `fig2_cluster_profile_heatmap.png` | Cluster × strategy profile heatmap (Figure 2) |
| `fig3_episode_network_named.png` | Episode similarity network with named clusters (Figure 3) |
| `fig4_persistence_and_transitions.png` | Persistence rates and transition matrix (Figure 4) |
| `fig5_constraint_strategy_heatmap.png` | Constraint-to-strategy conditional probability matrix (Figure 5) |
| `fig6_cluster_constraint_heatmap.png` | Cluster × constraint profile heatmap (Figure 6) |

### Tables (Excel)

| File | Description |
|------|-------------|
| `paper4_tables.xlsx` | All 8 manuscript tables in a single workbook |
| `kappa_results.xlsx` | Cohen's kappa results from validation |

### Data Files (CSV)

| File | Description |
|------|-------------|
| `sentences.csv` | 38,508 sentences with metadata |
| `labels.csv` | 666 strategy label instances |
| `episode_strategy_counts.csv` | Raw strategy counts per episode |
| `episode_strategy_share.csv` | Normalized strategy share vectors |
| `episode_clusters.csv` | Cluster assignments for 124 episodes |
| `transition_counts.csv` | 10×10 transition count matrix |
| `transition_matrix.csv` | 10×10 row-normalized transition matrix |
| `top_3step_paths.csv` | Top 3-step strategy path sequences |
| `co_matrix.csv` | 10×10 co-occurrence matrix |
| `episode_similarity.csv` | Pairwise cosine similarity (121×121) |
| `validation_metrics.csv` | Robustness analysis ARI values |

### Summary

| File | Description |
|------|-------------|
| `results_summary.json` | Key statistics and pipeline metadata |

---

## Regenerating Outputs

All output files are deterministic functions of the input corpus and code. To regenerate:

```
Open notebooks/Paper4_Network_Unified.ipynb in Google Colab
→ Set BASE_OUT and EPISODES paths
→ Run all cells (≈ 8 minutes)
```
