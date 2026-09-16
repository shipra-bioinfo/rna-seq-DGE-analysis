# DESeq2 RNA-seq Differential Expression Pipeline

My first full differential gene expression (DGE) pipeline, built in R from raw counts to actual biological insight.

Using the `airway` dataset (steroid-treated vs. untreated lung tissue, 8 samples), this covers:
- Loading and filtering count data (`SummarizedExperiment`, `DESeqDataSet`)
- Normalization, dispersion estimation, and significance testing with DESeq2
- Filtering to genes that actually matter (`padj < 0.05`)
- Making sense of results visually:
  - A row-scaled **heatmap** of top significant genes, with samples automatically clustering into their correct treatment groups based purely on expression patterns.
  - A **volcano plot** highlighting which genes are both statistically significant and biologically meaningful.

## What's next
Adding GO/KEGG enrichment analysis to figure out *what these genes are actually doing* biologically, not just that they changed.
