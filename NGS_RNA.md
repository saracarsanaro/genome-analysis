## NGS Sequencing and Analysis: RNA and Beyond

### ChIP-seq

### RNA-seq
RNA-seq is the term for massively parallel cDNA sequencing. The benefits of RNA-seq include defining transcription start sites, revealing small noncoding RNAs and long noncoding RNAs, identifying alternative splice products and splice sites, and quantitatively estimating transcript levels.

Alignment of RNA-seq data to a reference genome presents some unique challenges, specifiically with aligning spliced RNA to genomic DNA and accounting for gaps (introns) appropriately. Specialized software like [TopHat](http://ccb.jhu.edu/software/tophat/manual.shtml) is required for RNA-seq analysis. TopHat consists of [Cufflinks](http://cole-trapnell-lab.github.io/cufflinks/cufflinks/index.html#cufflinks-output-files) - uses a probabilistic model to take assembled reads and output complete transcripts; [Cuffcompare](http://cole-trapnell-lab.github.io/cufflinks/cuffcompare/) - compares two or more GFT files from Cufflinks, and [Cuffdiff](http://cole-trapnell-lab.github.io/cufflinks/cuffdiff/index.html#cuffdiff-output-files) - does the statistical analysis of differential expression between the two datasets. [Cuffmerge](http://cole-trapnell-lab.github.io/cufflinks/cuffmerge/index.html#cuffmerge-output-files) is also useful for producing a merged transcript dataset that includes all transcripts in both datasets, and [CummeRbund](http://compbio.mit.edu/cummeRbund/index.html) is an R package that is designed to aid and simplify the task of analyzing Cuffdiff RNA-Seq output. 

An example RNA-seq analysis might be: FastQC (data quality) -> Trimmomatic (trim reads) -> TopHat (map reads to reference) -> Cufflinks (assemble reads into transcripts) -> Cuffmerge (merge multiple datasets with reference annotation) -> Cuffdiff (perform differential expression analysis).

Other RNA-seq analysis tools inlcude [MATS]() ; [DiffSplice]() ; [DESeq2]() ; [edgR](), [EBSeq](), and [baySeq]() ; [StringTie]()
There are also de novo RNA-seq analysis tools which are useful in organisms that do not have a well-annotated genome. They work by aligning RNA-seq reads to each other based on overlapping segments to recapitulate a full RNA molecule. [Trinity](), [Salmon](), [Sailfish](), [RSEM](), and [Kallisto]() are de novo assembly tools. 

### Single-Cell RNA-seq

### Gene Editing

### Model Organisms
