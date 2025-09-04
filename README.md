# GENCODE v46 Genome Annotation Analysis

**Author:** Nisha MadhavaPrasad  
**Project Type:** R Markdown Analysis  
**Objective:** Analyze human genome annotation data from **GENCODE v46** to explore genes and transcripts, and generate summary statistics and visualizations.

---

## Data Source

The input data for this analysis is the **GENCODE v46 primary assembly GTF file**, available at the official FTP site:  
[https://ftp.ebi.ac.uk/pub/databases/gencode/Gencode_human/release_46/gencode.v46.primary_assembly.annotation.gtf.gz](https://ftp.ebi.ac.uk/pub/databases/gencode/Gencode_human/release_46/gencode.v46.primary_assembly.annotation.gtf.gz)

---

## Project Structure

```
GENCODEAnalysis_Project/
├── data/           # Raw and processed data files (GTF, CSV)
│   └──gencode.v46.annotation.gtf
├── gencode.Rmd    # Analysis notebooks (R Markdown)
└── README.md       # Project documentation
```

---

## Task Overview

This project follows a clear and reproducible workflow in **R**:

### 1. Package Management
- Automatically checks and installs required **CRAN** and **Bioconductor** packages.
- Ensures the analysis runs smoothly on any machine.

### 2. Data Download & Preprocessing
- Downloads the **GENCODE v46 primary assembly GTF file** from the official source.
- Decompresses the file to prepare for analysis.

### 3. Data Analysis
- Loads the GTF file and creates a `TxDb` object using **GenomicFeatures**.
- Extracts **genes** and **transcripts** to compute:
  - Total number of genes  
  - Total number of transcripts  
  - Number of genes with more than 1 transcript
- Creates a **data frame** with transcript counts per gene.
- Categorizes genes into:
  - 1 transcript  
  - 2–5 transcripts  
  - More than 5 transcripts  
- Saves the table as a CSV file in `results/`.

### 4. Data Visualization
- Generates a **stacked bar plot** showing gene distribution across transcript categories.
- Saves the plot as `transcript_category_distribution.png`.

---

## Outputs

- `transcript_counts_by_gene.csv` – Gene IDs with transcript counts and category
- `transcript_category_distribution.png` – Stacked bar plot of transcript categories

---

## How to Run

1. Open the R Markdown notebook:
   ```R
   gencode.Rmd
   ```
2. Knit the file in **RStudio** or run it chunk by chunk.
3. The workflow automatically:
   - Downloads the data  
   - Processes and analyzes transcripts  
   - Saves results 

---

## Dependencies

Required R packages (auto-installed by the script):

- **CRAN:** `dplyr`, `readr`, `ggplot2`, `stringr`, `tools`, `R.utils`
- **Bioconductor:** `GenomicFeatures`, `AnnotationDbi`, `BiocManager`

---

