# Computational Analysis Scripts for Exploratory data analysis of proteins frequencies

A Python script for comprehensive exploratory data analysis of protein frequency matrices.
The script was written and developed by Leonardo Broetto (leonardo.broetto@arapiraca.ufal.br, Lbroetto@gmail.com)

# Contact
**Authors:** Leonardo Broetto
**Correspondence:** Lbroetto@gmail.com, leonardo.broetto@arapiraca.ufal.br
**Affiliation:** Núcleo de Pesquisa em Bioinformática e Filogenômica (NPBF), Universidade Federal de Alagoas, Brasil

## Repository Structure

| Directory/File | Description |
|----------------|-------------|
| `Protein_frequency_Exploratory_Data_Analysis_script.py` | Main analysis script |
| `LICENSE` | GNU GPLv3 license |
| `README.md` | This documentation |

## Analysis Pipeline

Three sequential analyses in `Protein_frequency_Exploratory_Data_Analysis_script.py`:

| Step | Analysis | Output File |
|------|----------|-------------|
| 1 | Heatmap | `heatmap.png` |
| 2 | Hierarchical Clustermap | `clustermap.png` |
| 3 | Correlation Matrix | `correlation_heatmap.png` |

## Scripts Overview

**Purpose:** Exploratory data analysis of proteins frequencies. The Python-based analyses (heatmaps, hierarchical clustering and correlation) are primarily descriptive and exploratory in nature. They serve to visualize patterns, relationships, and structures within the dataset rather than to test specific statistical hypotheses.

**Analyses performed:**
- Simple heatmap visualization of raw data
- Hierarchical clustering using Dice dissimilarity metric and complete linkage
- Pearson correlation matrix with triangular mask
- All figures are automatically saved as PNG files. Note: Close each figure window to proceed to the next analysis.

**Heatmap:**
- This visualization represents the raw data matrix, providing an immediate overview of data intensity across samples and features. No inferential statistics are applied here; its purpose is pattern recognition.

**Hierarchical Clustermap:**
- This analysis employs a distance-based algorithm with inherent statistical measures: a) Distance Metric: use the Dice dissimilarity metric (equivalent to 1 – Dice coefficient), a statistical measure for binary or binarized data that quantifies dissimilarity between two sets. b) Linkage Method: The complete linkage method was used, which determines cluster similarity based on the maximum distance between members of each cluster. c) Standardization: The parameter standard_scale=1 scales the data per row (z-score normalization), ensuring that clustering is based on relative patterns rather than absolute magnitudes. While hierarchical clustering itself does not produce a p-value, it is a well-established multivariate statistical method for uncovering natural groupings within data, and the choice of metric and linkage method constitutes its statistical foundation.

**Correlation Matrix (heatmap of Pearson correlation coefficient):**
- The .corr() method in Pandas computes the Pearson correlation coefficient by default, which is a parametric statistical measure of linear dependence between variables. The resulting matrix and its visualization (with a mask for the upper triangle) provide a direct quantitative assessment of pairwise relationships. While it did not perform additional tests (e.g., calculating p-values for each correlation), the correlation coefficient itself is a fundamental statistic, and its magnitude (displayed in the heatmap) is the primary descriptor of association strength in this exploratory context.

**Note:**
- This suite of analyses constituted the exploratory data analysis (EDA) phase. Its goal was to inform hypotheses and select targets for deeper experimental and computational validation.

**Key statistical elements:**
- **Dice dissimilarity:** Distance metric for binary/binarized data
- **Pearson correlation:** Measure of linear association between variables
- **Z-score normalization:** Applied via `standard_scale=1` parameter

| Script | Purpose | Required CSV Columns | Output Figure |
|--------|---------|----------------------|---------------|
| `Protein_frequency_Exploratory_Data_Analysis_script.py` | Exploratory heatmaps & clustering | Matrix format (rows=features, cols=samples) | `heatmap.png`, `clustermap.png`, `correlation_matrix.png` |

----
# Quick Start: Using the Scripts
Before running the script:

Prepare your data: Requires a matrix-style CSV file structured as follows: Rows: Protein families or protein identifiers. Columns: Genomes or sample names. Cell values: Numerical frequencies representing the count or presence of each protein identified in each genome via pHMM (profile Hidden Markov Model for each differente protein family) prediction.

Configure the script: Open the script file and locate the INPUT_FILE variable at the top. Change its value to match your CSV filename.

Install dependencies: Ensure you have the required Python packages installed (see Requirements).

Run the script: Execute it from your terminal or IDE: python script_name.py

Data Privacy Note: The original research data is not included in this repository. The scripts are configured to work with generic filenames (input_data_table.csv). Replace this with your own data filename.

Expected Data Location: By default, scripts look for the CSV file in the same directory as the script. You can modify the path in the INPUT_FILE variable if needed (e.g., 'data/my_file.csv').

---

## Data Availability Note

**Important:** The original input data files (`*.csv`) used in this study are **not included** in this repository. This protects the primary research data.

### For Reproducibility and Reuse:
1.  **Code Execution:** To run these scripts with your own data, simply place your CSV file in the `data/` directory and update the filename in the script (or rename your file to match the expected name in the script).
2.  **Data Format:** script includes a comment at the top describing the **required input** and **configuration** for the input CSV. Please ensure your data follows this format.

### Expected Input Format:
- Requires a matrix-style CSV file structured as follows: Rows: Protein families or protein identifiers. Columns: Genomes or sample names. Cell values: Numerical frequencies representing the count or presence of each protein identified in each genome via pHMM (profile Hidden Markov Model for each differente protein family) prediction.


## Requirements & Installation

### Python Dependencies
Create a conda environment or install directly:
``bash
pip install pandas numpy matplotlib seaborn

## Versions Tested
Python 3.8+
pandas >= 1.3.0
seaborn >= 0.11.0
matplotlib >= 3.3.0
numpy >= 1.19.0

# License and Citation

### If you use this analysis script in your research, please cite:

```bibtex
@software{broetto_data_analysis_of_protein_frequencies_2026,
  author       = {Leonardo Broetto},
  title        = {{Python script for comprehensive exploratory data analysis of protein frequency matrices}},
  month        = jan,
  year         = 2026,
  publisher    = {Zenodo},
  version      = {v1.0.0},
  doi          = {10.5281/zenodo.??????},
  url          = {https://doi.org/10.5281/zenodo.???????}
}
```

This project is licensed under the **GNU General Public License v3.0**.

### Terms for Academic/Research Use:
- Free to use, study, and modify
- Must distribute derivatives under GPLv3
- Must provide source code when distributing binaries
- Must preserve copyright notices and license text

### Terms for Commercial Use:
For commercial applications or proprietary integration, please contact the author (Lbroetto@gmail.com, leonardo.broetto@arapiraca.ufal.br) to discuss alternative licensing options.

**Full license text:** [LICENSE](LICENSE)

## Intellectual Property Notice

The computational methods, algorithms, and models implemented in this software are research outcomes from Universidade Federal de Alagoas. While the source code is licensed under GPLv3 for academic and open-source use, commercial licensing options are available.

This software is available under two licenses:
1. GNU GPLv3 for open source/academic use
2. Commercial license for proprietary use (contact author)
For commercial licensing, technology transfer, or collaboration inquiries:
Contact: Lbroetto@gmail.com, leonardo.broetto@arapiraca.ufal.br


### Copyright and Licensing
- **Copyright Holder:** Leonardo Broetto 
- **License:** GNU General Public License v3.0
- **Year:** 2026

### Research Attribution
The computational methodologies implemented in this software were developed as part of research activities conducted by Leonardo Broetto. Associated research work is linked to Universidade Federal de Alagoas.

### Usage Terms
- **Academic/Research Use:** Permitted under GPLv3 with mandatory citation
- **Commercial Use:** Requires alternative licensing (contact author)
- **Derivative Works:** Must be released under GPLv3

### Contact for Licensing
Leonardo Broetto
Lbroetto@gmail.com, leonardo.broetto@arapiraca.ufal.br
(Associated with Universidade Federal de Alagoas)
