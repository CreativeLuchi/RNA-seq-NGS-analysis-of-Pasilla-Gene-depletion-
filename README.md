# RNA-seq-NGS-analysis-of-Pasilla-Gene-depletion-
🧬 RNA-Seq Based Gene Expression Profiling of Pasilla gene, the Drosophila ortholog of mammalian NOVA1 and NOVA2

🧬 RNA sequencing is widely used for gene expression profiling to identify genes or molecular pathways
that are differentially expressed between two different biological condition.​

In this project, I used a computational workflow to investigate the impact of depleting the Pasilla
(ps) gene in Drosophila melanogaster cells. RNA-Seq data from both Pasilla-depleted (treated) and
control (untreated) samples were analyzed to determine how the loss of ps affects gene expression and
associated biological pathways ​

The Pasilla gene in Drosophila melanogaster (fruit fly) encodes an RNA-binding protein that is the
functional equivalent (ortholog) of the mammalian NOVA1 and NOVA2 proteins. It plays a crucial role
in the regulation of alternative splicing, developmental and regulatory mechanisms. The Pasilla gene and
NOVA1/2 (in insects and mammals respectively) are orthologues and their regulatory map/mechanism
are highly conserved, however their target genes are distinctly different.This points to a conserved “RNA
regulatory map” for splicing factors across evolution.​

The analysis followed three main stages: data processing and quality control, read alignment, and downstream analysis for differential expression and pathway enrichment.​

I began by uploading the paired-end raw FASTQ files for both treated and untreated samples from the Galaxy data library. Quality control was performed with FastQC, and Trimmomatic was used to trim low-quality bases, ensuring the data was clean and ready for analysis. The processed reads were then mapped to the Drosophila melanogaster reference genome (dm6) using HISAT2, which produced BAM files for each sample.​

For quantifying gene expression, I used FeatureCounts to assign the aligned reads to genes, generating raw count data. Differential expression analysis was carried out with DESeq2, which provided statistical results, normalized counts, and visualizations. Since the initial DESeq2 output didn't provide gene annotations, I used AnnotateDESeq2 to add gene information, making the results easier to interpret.​

To sort and filter the differentially expressed genes, I worked with the annotated results in Excel, selecting genes with an adjusted p-value below 0.05 and a log2 fold change of ≤ -1 for downregulated or ≥ 1 for upregulated genes. Finally, I used DAVID to perform Gene Ontology (GO) and KEGG pathway enrichment analysis, which helped identify the biological processes and pathways most affected by the loss of Pasilla.

![workflow](https://github.com/user-attachments/assets/11b84b09-c5a8-44b3-95fa-a84225e1dea6)
