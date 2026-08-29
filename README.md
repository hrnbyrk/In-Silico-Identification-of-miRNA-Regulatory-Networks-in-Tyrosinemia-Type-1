# In-Silico-Identification-of-miRNA-Regulatory-Networks-in-Tyrosinemia-Type-1
In Silico Identification of Novel Therapeutic Candidates and Dual-Targeting miRNA Regulatory Networks in Tyrosinemia Type 1
# Integrated Transcriptomic and miRNA Regulatory Network Analysis of Tyrosinemia Type 1

![R](https://img.shields.io/badge/Language-R-4.5.0-blue)
![Status](https://img.shields.io/badge/Status-Completed-success)
![License](https://img.shields.io/badge/License-MIT-green)

## 🧬 Project Overview
This repository contains the comprehensive bioinformatic analysis source code and datasets for **Tyrosinemia Type 1 (HT1)**. The study aims to elucidate the molecular pathogenesis of HT1 by integrating multiple transcriptomic datasets and constructing a robust **miRNA-TF-Gene regulatory network**.

Special focus is given to the **FAH** gene (the primary pathogenic cause) and the **HPD** gene (the therapeutic target of Nitisinone) to identify "Dual-Hit" miRNA regulators and potential drug-gene interactions for therapeutic repurposing.

## 📂 Datasets
The analysis integrates three independent microarray datasets retrieved from the NCBI GEO database, focusing on *Mus musculus* models of Tyrosinemia Type 1:
1. **GSE225001** (Platform: MoGene-1.0-st)
2. **GSE161478** (Platform: Mouse430_2)
3. **GSE205434** (Platform: MoGene-2_0-st)

## 🛠️ Methodology & Workflow

### 1. Data Preprocessing & Core DEG Identification
- **Tool:** `Limma` (R package).
- **Strategy:** A strict consensus approach was applied. Genes were identified as "Core DEGs" only if they were significantly differentially expressed across all three datasets with high expression similarity (within 10% variation).
- **Output:** Robust biomarkers including *HPD, TAT, GCLC, AFP, and FAH*.

### 2. Functional Enrichment Analysis
- **Tool:** `clusterProfiler`.
- **Analysis:** GO (Biological Process) and KEGG Pathway enrichment.
- **Visualization:** Rich Factor Bubble Plots and Gene-Concept Networks (cnetplots).
- **Key Findings:** Significant downregulation in amino acid metabolism and upregulation in inflammatory/oncogenic pathways.

### 3. Master Regulator miRNA Prediction
- **Tool:** `multiMiR`.
- **Strategy:** Prediction of upstream miRNA regulators targeting the core DEGs. 
- **Result:** Identification of Top 20 Master Regulator miRNAs (e.g., *mmu-miR-17-5p, -20b-5p, -34a-5p, -19b-3p, and -26b-5p*).

### 4. Targeted Analysis: FAH & HPD Regulation
- **Dual-Hit Hypothesis:** Identification of miRNAs targeting **both** *FAH* and *HPD* genes simultaneously.
- **Binding Site Visualization:** Mapping of miRNA seed regions onto the 3'UTR of *FAH* and *HPD* genes using `Biostrings`.

### 5. Integrative Network Analysis
- **Tools:** `igraph`, `ggraph`.
- **Construction:** A holistic regulatory network integrating:
    - Core Biomarker Genes
    - Validated Master miRNAs
    - Drug-Gene Interactions (e.g., Nitisinone, Sorafenib)

## 📊 Key Figures

| Figure | Description |
| :--- | :--- |
| **Fig 1** | Expression profiling of critical biomarkers across 3 datasets. |
| **Fig 2** | Potential Drug-Gene interactions based on DGIdb and literature. |
| **Fig 3** | HPD Gene Regulatory Network (miRNA & Drug targets). |
| **Fig 4** | Holistic Tyrosinemia Signaling and Regulation Network. |

*(High-resolution figures are available in the `results/` directory)*

## 💻 Installation & Usage

To reproduce the analysis, clone this repository and run the R scripts sequentially.

```r
# Prerequisite: Install required R packages
install.packages(c("tidyverse", "ggplot2", "igraph", "ggraph", "pheatmap"))

if (!require("BiocManager", quietly = TRUE))
    install.packages("BiocManager")

BiocManager::install(c("limma", "clusterProfiler", "org.Mm.eg.db", "multiMiR", "biomaRt", "Biostrings"))


📞 Contact
Harun Bayrak, MD, PhD
•	Affiliation: Sincan Training and Research Hospital, Ankara, Türkiye
•	Dept: Pediatric Metabolic Disorders
•	Email: hrnbyrk@gmail.com
•	ORCID: 0000-0002-5728-3895
