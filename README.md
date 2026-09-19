# DESeq2 RNA-seq Differential Expression Pipeline

My first full differential gene expression (DGE) pipeline, built in R from raw counts to actual biological insight.

Using the `airway` dataset (steroid-treated vs. untreated lung tissue, 8 samples), this covers:
- Loading and filtering count data (`SummarizedExperiment`, `DESeqDataSet`)
- Normalization, dispersion estimation, and significance testing with DESeq2
- Filtering to genes that actually matter (`padj < 0.05`)
- Making sense of results visually:
  - A row-scaled **heatmap** of top significant genes, with samples automatically clustering into their correct treatment groups based purely on expression patterns.
  - A **volcano plot** highlighting which genes are both statistically significant and biologically meaningful.

## Gene Set Enrichment Analysis
Ran KEGG pathway enrichment (`clusterProfiler`) on the significant gene list. The top-30 gene list showed no significant pathways because of small sample. The full significant gene list (2,694 genes) showed strong enrichment, with **Focal adhesion** as the top hit (69 genes, adjusted p-value ≈ 8.3 × 10⁻¹³), consistent with steroid treatment's known effects on cell structure and inflammation signaling.

