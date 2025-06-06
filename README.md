# Contrastive Multiple Correspondence Analysis (cMCA)

This repository contains the implementation of **Contrastive Multiple Correspondence Analysis (cMCA)**, a replication study based on the research paper:  
**"Contrastive Multiple Correspondence Analysis: Applying the Contrastive Learning Method to Identify Political Subgroups"**  
by **Takanori Fujiwara** and **Tzu-Ping Liu**.

## 📘 Overview

The goal of this project is to apply and evaluate cMCA and compare it against other dimensionality reduction techniques to uncover political subgroups in survey data. The study uses the **2015 Cooperative Congressional Election Study (CCES)** dataset to replicate the core findings of the original paper.

## 📂 Dataset

- **Dataset used**: `issuevalue_short`
- **Source**: [CCES 2015 Dataset on Harvard Dataverse](https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi%3A10.7910/DVN/SWMWX8)
- **Records**: 1000 respondents  
- **Features**: 53 categorical political and ideological survey questions  
- **Target Variable**: `partyid` (7-point party affiliation scale)

## 🧪 Methods Applied

The following techniques were implemented for comparative analysis:

- **Ordered Optimal Classification (OOC)**  
- **Multiple Correspondence Analysis (MCA)**  
- **Basic Space (BS)**  
- **Bayesian Mixed Factor Analysis (BMFA)**  
- **Contrastive Multiple Correspondence Analysis (cMCA)**  

These methods were used to perform dimensionality reduction and subgroup identification within political affiliation categories (Democrats vs Republicans).

## ⚙️ Methodology

1. **Data Cleaning and Preprocessing**
   - Recoded categorical variables into numeric form
   - Imputed missing values using mode stratified by `partyid`
   - Dropped columns with >50% missing values

2. **Baseline Dimensionality Reduction**
   - Applied OOC, MCA, BS, and BMFA
   - Visualized ideological distributions and clusters

3. **Applying cMCA**
   - Defined target and background groups (Democrats vs Republicans)
   - Applied PCA to background and projected target to contrast
   - Calculated contrastive components and visualized results

4. **Subgroup Analysis**
   - Democrats: split into **Dem_Lib** and **Dem_Oth**
   - Republicans: split into **Rep_Con** and **Rep_Oth**

## 🔍 Key Findings

- Traditional methods identified general ideological separation but lacked subgroup insight.
- cMCA effectively revealed ideological subclusters within major political parties.
- Clear polarization between Democrat and Republican groups was captured along the first contrastive principal component (cPC1).
- Subgroups like **Dem_Lib**, **Rep_Con** illustrated overlaps and internal variation within the larger party identities.

## 📈 Visualization

Visual outputs demonstrate:
- Contrastive projection of Democrats vs Republicans
- Internal subgroup distinctions without background
- Centrist overlap and ideological divergence captured in cPC1

## 📦 Repository Structure

├── data/
│ └── issuevalue_short.csv
├── requirements/
│ └── requirements_BMFA.txt
│ └── requirements_cMCA.txt
│ └── requirements_MCA.txt
│ └── requirements_OOC.txt
│ └── Requirements.docx
├── CES15_BMFA.ipynb
├── CES15_BS.ipynb
├── CES15_MCA.ipynb
├── CES15_OOC.ipynb
├── cMCA_TargetBackground.ipynb
├── README.md

## 🛠 Tools & Libraries

- Python (NumPy, pandas, matplotlib, scikit-learn, PyMC)
- R (for Basic Space)
- Jupyter Notebook
- Data Imputation (SVM, Mode-based)
- Visualization (scatter plots, PCA projections)

## 📖 Reference

Fujiwara, T., & Liu, T. (2020). *Contrastive Multiple Correspondence Analysis: Applying the Contrastive Learning Method to Identify Political Subgroups.* University of California, Davis.

## 👥 Authors

- Mario Palomino Viero  
- Sandaru Welikala

