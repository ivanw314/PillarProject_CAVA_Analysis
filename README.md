# PillarProject CAVA Analysis

## Directory structure

```
PillarProject_CAVA_Analysis/
├── Notebooks/
│   ├── PP_ClinVarPrecisionRecall.ipynb
│   ├── PP_Fig2_Heatmaps.ipynb
│   ├── PP_ProcessBigDataFrame.ipynb
│   ├── PP_ResolutionOverview.ipynb
│   ├── PP_SGE_qc_overview.ipynb
│   ├── PP_SeqFunctionMap.ipynb
│   ├── PP_SpliceAI_ClinVar_benchmark.ipynb
│   ├── PP_SpliceAI_CuratedSplicing_benchmarking.ipynb
│   ├── PP_SpliceAI_Joint_benchmarking.ipynb
│   ├── PP_SpliceAI_SGE_Benchmarking.ipynb
│   ├── PP_StackedHistograms.ipynb
│   ├── PP_VAMPseq_qc_overview.ipynb
│   └── deprecated/
│       ├── BARD1_stuff/        ← earlier single-gene BARD1 notebooks
│       ├── BCDX2_RAD51D_XRCC2Heatmap.ipynb
│       ├── PP_ClinVar.ipynb
│       ├── PP_ClinVarLayerdHisto.ipynb
│       ├── PP_SASAvsAssays.ipynb
│       ├── PP_SASAvsSGE.ipynb
│       ├── PP_SASAvsVAMPseq.ipynb
│       ├── PP_ThermoMPNNvsSGE.ipynb
│       ├── PP_ThermoMPNNvsVAMPseq.ipynb
│       └── PP_VAMPseq_HeatMap.ipynb
└── Data/
    ├── pillar_project_data_inputs.xlsx
    ├── 20260101_CAVAseqsubset.xlsx
    ├── 20260101_SGEsubset.xlsx
    ├── 20260101_VAMPseqsubset_wDups.xlsx
    ├── sge_data_for_qc/
    │   ├── BARD1.delcounts.tsv
    │   ├── BARD1.editrates.tsv
    │   ├── BARD1.snvcounts.tsv
    │   ├── RAD51D.delcounts.tsv
    │   ├── RAD51D.editrates.tsv
    │   ├── RAD51D.snvcounts.tsv
    │   ├── gene_cartoon_data/
    │   │   ├── 20260414_SGE_protein_domains.xlsx
    │   │   └── targets_tsvs/
    │   │       ├── BARD1.targets.tsv
    │   │       └── RAD51D.targets.tsv
    │   ├── orthogonal_sge_data/
    │   │   ├── BARD1_Various.xlsx
    │   │   ├── PALB2_Boonen2025.xlsx
    │   │   └── RAD51D_Darrah2026.xlsx
    │   ├── spliceai_benchmarking/
    │   │   ├── 20260506_CuratedSplicingTruthset.xlsx
    │   │   ├── 20260507_CuratedSplicing_VEPAnnotations_firstpass.txt
    │   │   ├── 20260511_CuratedSplicing_CleanedVCF.vcf
    │   │   ├── 20260511_CuratedSplicing_UpdatedVEP.txt
    │   │   ├── 20260512_ClinVarSplicingSet.xlsx
    │   │   ├── 20260512_CuratedSplicingSet.xlsx
    │   │   └── 20260512_SGESplicingSet.xlsx
    │   └── sge_thermompnn/
    │       ├── BARD1_ARD.csv
    │       ├── BARD1_BRCT.csv
    │       ├── BARD1_RING.csv
    │       ├── PALB2_WD40.csv
    │       ├── RAD51D_All.csv
    │       └── XRCC2_All.csv
    └── vampseq_data_for_qc/
        ├── 20260410_FIX_HeavyChainAb_scores.csv
        ├── 20260410_G6PD_scores.csv
        ├── 20260410_TSC2_lib1_scores.csv
        ├── 20260410_TSC2_lib2_scores.csv
        ├── 20260413_VAMPseq_protein_domains.xlsx
        └── vampseq_thermompnn/
            ├── FIX_AF.csv
            ├── G6PD_7UAG.csv
            └── TSC2_7DL2.csv
```

---

## Notebooks

### PP_ClinVarPrecisionRecall.ipynb
Bulk precision recall analysis for VAMP-seq and SGE.

### PP_Fig2_Heatmaps.ipynb
Heatmaps generated for G6PD and RAD51D as used in figure 2. Includes nucleotide-level heatmap generated for SGE data.

### PP_ProcessBigDataFrame.ipynb
Processes the Pillar Project dataframe and outputs:
1. Whole CAVA center subset (includes SGE and VAMP-seq data)
2. SGE subset
3. VAMP-seq subset

### PP_ResolutionOverview.ipynb
Outputs figure highlighting number of bases and amino acid positions covered by each assay

### PP_SGE_qc_overview.ipynb
Notebook to generate QC plots for all SGE experiments. 

### PP_SeqFunctionMap.ipynb
Standalone notebook to build nucleotide-level heatmap

### PP_SpliceAI_ClinVar_benchmark.ipynb
Benchmarks SpliceAI predictions against ClinVar variants with potential splice effects. Output dataset is used as input to `PP_SpliceAI_Joint_benchmarking.ipynb`.

### PP_SpliceAI_CuratedSplicing_benchmarking.ipynb
Benchmarks SpliceAI predictions against a curated splicing truth set. Output dataset is used as input to `PP_SpliceAI_Joint_benchmarking.ipynb`.

### PP_SpliceAI_Joint_benchmarking.ipynb
Joint sensitivity/specificity analysis of SpliceAI across SGE, ClinVar, and curated splicing datasets by variant consequence type. Requires output files from the three individual SpliceAI benchmarking notebooks.

### PP_SpliceAI_SGE_Benchmarking.ipynb
Benchmarks SpliceAI predictions against SGE splicing functional data. Output dataset is used as input to `PP_SpliceAI_Joint_benchmarking.ipynb`.

### PP_StackedHistograms.ipynb
Builds histograms for VAMP-seq data and histograms and insets for SGE data.

### PP_VAMPseq_qc_overview.ipynb
Notebook to generate QC plots for all VAMP-seq experiments. 

---

## Data

### Top-level data files

- **pillar_project_data_inputs.xlsx** — Excel file containing paths to data files

- **20260101_CAVAseqsubset.xlsx** — Full CAVA subset file

- **20260101_SGEsubset.xlsx** — SGE data subset

- **20260101_VAMPseqsubset_wDups.xlsx** — VAMP-seq data subset

### sge_data_for_qc/

Per-gene raw count and edit-rate files used by `PP_SGE_qc_overview.ipynb`. Files are named in format of `{GENE}.editrates.tsv` or `{GENE}.delcounts.tsv`

- **BARD1.delcounts.tsv** 

- **BARD1.editrates.tsv** 

- **BARD1.snvcounts.tsv** 

- **RAD51D.delcounts.tsv** 

- **RAD51D.editrates.tsv** 

- **RAD51D.snvcounts.tsv** 

#### gene_cartoon_data/

Data required to generate SGE library cartoons

- **20260414_SGE_protein_domains.xlsx** — SGE gene protein domains

Targets files contain coordinates for the SGE libraries and are in format of `{GENE}.targets.tsv`

- **targets_tsvs/BARD1.targets.tsv**
- **targets_tsvs/RAD51D.targets.tsv**

#### orthogonal_sge_data/

Miscellaneous orthogonal SGE data used for QC

- **BARD1_Various.xlsx**
- **PALB2_Boonen2025.xlsx**
- **RAD51D_Darrah2026.xlsx**

#### spliceai_benchmarking/

Input and processed data for SpliceAI benchmarking analyses.

- **20260506_CuratedSplicingTruthset.xlsx** — Raw curated splicing truth set
- **20260507_CuratedSplicing_VEPAnnotations_firstpass.txt** — First-pass VEP annotations for curated variants
- **20260511_CuratedSplicing_CleanedVCF.vcf** — Cleaned VCF used for VEP re-annotation
- **20260511_CuratedSplicing_UpdatedVEP.txt** — Updated VEP annotations after cleaning
- **20260512_ClinVarSplicingSet.xlsx** — Processed ClinVar splicing dataset for benchmarking
- **20260512_CuratedSplicingSet.xlsx** — Processed curated splicing dataset for benchmarking
- **20260512_SGESplicingSet.xlsx** — Processed SGE splicing dataset for benchmarking

#### sge_thermompnn/

Data generated from ThermoMPNN for QC

- **BARD1_ARD.csv**
- **BARD1_BRCT.csv**
- **BARD1_RING.csv**
- **PALB2_WD40.csv**
- **RAD51D_All.csv**
- **XRCC2_All.csv**

### vampseq_data_for_qc/

VAMP-seq data (with replicates) for QC used by `PP_VAMPseq_qc_overview.ipynb`

- **20260410_FIX_HeavyChainAb_scores.csv** 

- **20260410_G6PD_scores.csv**

- **20260410_TSC2_lib1_scores.csv**

- **20260410_TSC2_lib2_scores.csv** 

- **20260413_VAMPseq_protein_domains.xlsx** — Contains information regarding start/stop for protein domains for proteins assayed by VAMP-seq

#### vampseq_thermompnn/

Data generated from ThermoMPNN for VAMP-seq proteins

- **FIX_AF.csv** 

- **G6PD_7UAG.csv** 

- **TSC2_7DL2.csv** 
