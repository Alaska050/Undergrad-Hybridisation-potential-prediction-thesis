# Genome-Wide Sequence Divergence Pipeline for Predicting Hybridisation Potential in Lepidoptera

## Overview
This repository contains the code and Jupyter notebooks for my BSc Biomedical Sciences dissertation (2025), which investigates whether genome-wide sequence divergence can predict hybridisation potential in butterflies.

The project presents a scalable bioinformatics pipeline that:

- Performs pairwise genome alignments using Minimap2  
- Extracts gap-compressed per-base sequence divergence ("de"/"def" metric)  
- Compares divergence across hybridising, possibly hybridising, and non-hybridising species pairs  
- Conducts statistical analysis (ANOVA + Tukey HSD)  
- Produces visualisations of divergence and genome alignments  

The study focuses on *Heliconius* and *Pieris* butterflies.

---

## Research Question
Does genome-wide sequence divergence significantly correlate with hybridisation potential?

---

## Key Findings
- Hybridising species pairs exhibit significantly lower divergence  
- Non-hybridising pairs show higher divergence  
- ANOVA results show strong statistical significance (p ≤ 0.0001)  
- Divergence metric is a useful predictor of hybridisation potential  

---

## Methods Summary

### Genome Alignment

minimap2 -cx asm20 -t 4 --cs --secondary=no ref.fa query.fa | sort -k6,6 -k8,8 > output.paf


### Divergence Extraction
- Extracted from PAF "de" tag  
- Averaged per species pair  

### Statistical Analysis
- One-way ANOVA  
- Tukey HSD post-hoc tests  
- Implemented in Python  

### Visualisation
- Boxplots of divergence distributions  
- Pairwise alignment visualisations  

---

## Data Sources
Genome assemblies obtained from NCBI Genome database.

Species classification based on published hybridisation literature.

---

Install dependencies:
pip install -r requirements.txt

## Acknowledgements
Supervised by Dr Max Carter-Brown.

