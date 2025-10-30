# Coordinate_GSEA_Project

This project performs **Gene Set Enrichment Analysis (GSEA)** on results generated from a **Coordinate-Aware CLAM model** applied to spatial transcriptomics data.

---

## Project Overview

This repository represents the downstream bioinformatics workflow from my capstone project at **Weill Cornell Medicine**, focusing on interpretable spatial transcriptomics.

---

## Experiment Overview

<p align="center">
  <img src="https://raw.githubusercontent.com/Fanxi-Wang/Coordinate_GSEA_Project/main/images/Experiment_Overview.png" width="750">
</p>

*Figure 1. Overview of the full experimental workflow integrating the Coordinate-Aware CLAM model (Phase 1), differential expression analysis (Phase 2), and gene set enrichment (Phase 3).*

**Phase 1 — Model (Coordinate-Aware CLAM):**  
- Developed a Multiple Instance Learning (MIL) model incorporating spatial coordinates.  
- Input: Spatial transcriptomics data  
- Output: Attention weight matrix (`weights.csv`) representing the spatial importance of tissue regions.

**Phase 2 — Differential Expression (PyDESeq2):**  
- Grouped samples into *high-* and *low-attention* regions using model-derived weights.  
- Performed differential expression analysis with **PyDESeq2** to identify significantly up- and down-regulated genes.  
- Output: `deseq_with_attention_simulated_new_coordinate.csv`

**Phase 3 — Gene Set Enrichment (this repository):**  
- Conducted both *non-directional* and *directional* GSEA using R.  
- Highlighted the top 35 most significant GO terms.  
- Visualized enriched biological processes in high- and low-attention regions.

### Downstream Analysis Workflow

<p align="center">
  <img src="https://raw.githubusercontent.com/Fanxi-Wang/Coordinate_GSEA_Project/main/images/Downstream_Analysis_Workflow.png" width="750">
</p>

*Figure 2. Downstream analysis workflow illustrating how attention scores are used to aggregate spatial data into pseudo-bulk profiles, followed by differential expression and gene set enrichment analyses.*

---

## Files
- **Coordinate_GSEA_analysis.R** — main R script containing the full analysis pipeline
- *(No data files are included due to privacy restrictions.)*

---

## Tools and Packages

R packages used:
```r
data.table, dplyr, clusterProfiler, org.Hs.eg.db,
GO.db, fgsea, ggplot2, tibble, reshape2, gsEasy, AnnotationDbi
```


## Summary

This workflow connects a spatially aware deep learning model with downstream biological interpretation.
By linking attention weights to differential expression and pathway-level enrichment, it demonstrates how spatial models can uncover biologically meaningful tissue-level patterns.

Author: Fanxi Wang | Institution: Weill Cornell Medicine | Date: October 2025

