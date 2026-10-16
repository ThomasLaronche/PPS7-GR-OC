# 🧬 Mapping Metabolic Plasticity and TME Crosstalk in HGSOC
CentraleSupélec - Pôle Projet 

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/TON_PSEUDO/HGSOC_Metabolic_Landscape/blob/main/Pipeline_Locasale_Final.ipynb)

* Client: Dr. Géraldine Gentric (MetaboCare lab, Institut Gustave Roussy - IGR)
* Team: Octave Bloquel, Hugo Dujardin, Ellinor Hagstrom Comard, Thomas Laronche, Ali Trabelsi
* Academic Supervisor: Christophe Antoine

## 📌 Project Overview
This repository contains the bioinformatics pipeline adapted from the Duke University/Locasale Lab framework. Our goal is to map the single-cell metabolic landscape of High-Grade Serous Ovarian Cancer (HGSOC) to understand tumor heterogeneity, metabolic plasticity, and interactions with the Tumor Microenvironment (TME).

We processed a large-scale single-cell RNA-seq cohort (New York dataset, ~390,000 cells) and scored 85 canonical metabolic pathways using MSigDB (C2:CP).

## 🚀 Key Technical Achievements
1. **RAM-Safe Chunking:** Overcame memory limitations (ArrayMemoryError) by processing the 390k-cell sparse matrix in manageable chunks (10,000 cells/block).
2. **Gene Alignment:** Correctly mapped MSigDB human gene symbols against the dataset's `feature_name` annotations (bypassing Ensembl ID mismatches).
3. **Interactive Visualization:** Injected continuous metabolic scores (e.g., Glycolysis, OXPHOS) into a lightweight AnnData object for real-time spatial exploration using **Cellxgene**.

## 📂 Repository Structure
```text
📦 HGSOC_Metabolic_Landscape
 ┣ 📂 Archives/           # Old scripts, R trials, and legacy matrix exports
 ┣ 📂 data/
 ┃ ┗ 📂 raw/              # Raw data (dataset_newyork.rds) - Not uploaded to GitHub (too large)
 ┣ 📂 docs/               # Presentations, objective sheets, and final reports
 ┣ 📂 results/
 ┃ ┗ 📂 cellxgene/        # Final lightweight .h5ad dataset injected with metabolic metadata
 ┣ 📜 Pipeline_Locasale_Final.ipynb  # 👑 THE CORE NOTEBOOK (Data extraction & Scoring)
 ┗ 📜 README.md