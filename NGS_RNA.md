## NGS Sequencing and Analysis: RNA and Beyond

### ChIP-seq

### RNA-seq
RNA-seq is the term for massively parallel cDNA sequencing. The benefits of RNA-seq include defining transcription start sites, revealing small noncoding RNAs and long noncoding RNAs, identifying alternative splice products and splice sites, and quantitatively estimating transcript levels.

Alignment of RNA-seq data to a reference genome presents some unique challenges, specifiically with aligning spliced RNA to genomic DNA and accounting for gaps (introns) appropriately. Specialized software like [TopHat](http://ccb.jhu.edu/software/tophat/manual.shtml) is required for RNA-seq analysis. TopHat consists of [Cufflinks](http://cole-trapnell-lab.github.io/cufflinks/cufflinks/index.html#cufflinks-output-files) - uses a probabilistic model to take assembled reads and output complete transcripts; [Cuffcompare](http://cole-trapnell-lab.github.io/cufflinks/cuffcompare/) - compares two or more GFT files from Cufflinks, and [Cuffdiff](http://cole-trapnell-lab.github.io/cufflinks/cuffdiff/index.html#cuffdiff-output-files) - does the statistical analysis of differential expression between the two datasets. [Cuffmerge](http://cole-trapnell-lab.github.io/cufflinks/cuffmerge/index.html#cuffmerge-output-files) is also useful for producing a merged transcript dataset that includes all transcripts in both datasets, and [CummeRbund](http://compbio.mit.edu/cummeRbund/index.html) is an R package that is designed to aid and simplify the task of analyzing Cuffdiff RNA-Seq output. 

Other RNA-seq analysis tools inlcude: [MATS](https://pubmed.ncbi.nlm.nih.gov/22266656/) designed for hypothesis testing of alternative splice patterns detected by RNA-seq; [DiffSplice](https://pubmed.ncbi.nlm.nih.gov/23155066/) compares transcriptomes assembled from multiple RNA-seq datasets; [DESeq2](https://genomebiology.biomedcentral.com/articles/10.1186/s13059-014-0550-8) performs differential expression testing of genes from RNA-seq data; [edgR](https://academic.oup.com/bioinformatics/article/26/1/139/182458), [EBSeq](https://www.bioconductor.org/packages/devel/bioc/vignettes/EBSeq/inst/doc/EBSeq_Vignette.pdf), and [baySeq](https://bmcbioinformatics.biomedcentral.com/articles/10.1186/1471-2105-11-422) rely on first aligning RNA-seq reads to a reference genome before transcript abundances can be estimated; and [StringTie](https://ccb.jhu.edu/software/stringtie/) performs transcript assembly and expression estimates in one step.

There are also de novo RNA-seq analysis tools which are useful in organisms that do not have a well-annotated genome. They work by aligning RNA-seq reads to each other based on overlapping segments to recapitulate a full RNA molecule. [Trinity](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3571712/), [Salmon](https://salmon.readthedocs.io/en/latest/), [Sailfish](https://www.nature.com/articles/nbt.2862), [RSEM](https://github.com/deweylab/RSEM), and [Kallisto](https://www.nature.com/articles/nbt.3519) are de novo assembly tools or pseudo-mappers. 

An example RNA-seq analysis might be: *FastQC* to check data quality -> *Trimmomatic* to trim reads -> *TopHat* to map reads to reference -> *Cufflinks* to assemble reads into transcripts -> *Cuffmerge* to merge multiple datasets with reference annotation -> *Cuffdiff* to perform differential expression analysis.

### Single-Cell RNA-seq

### Gene Editing

## Model Organisms
### Yeast
**Saccharomyces cerevisiae**

**Fission Yeast**, **Aspergillus**, **Candida**, and **Fungi** data-mining interface [FungiDB]()

### Non-Metazoan
**Giardia**, **Trypanosomes**, **Leishmania**, and general **Protozoan** [genome project]()

**Plasmodium**, **Tetrahymena**, **Toxoplasma gondii**

**Thalassiosira pseudonana** and **Phytophthora**

### Plants
**Phytophthora**

**Dictyostelium discoideum**

### Metazoan Genomes
**Caenorhabditis elegans** oh my sweet friend the roundworm. you still haunt me in my dreams sometimes.

**Drosophila melanogaster** the good old fly buzz buzz

**Mouse**, **Chimpanzee**, also Ensembl, UCSC, and IGV are options for higher organisms. 

### Eukaryotic Features

**Repeats**

**Aneuploidy**, **Inversions**, **Chromosome number and synteny**

**Sequence tagged sites**
