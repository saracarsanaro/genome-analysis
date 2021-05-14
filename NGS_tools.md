# NGS Tools and Technologies

### Galaxy
Galaxy is an interface designed to analyze genomic data both from publicly available databases (Ensembl, UCSC) and user-derived data. It can be accessed via the [Web Interface](https://usegalaxy.org/), [locally](https://galaxyproject.org/admin/get-galaxy/), [on the cloud](https://galaxyproject.org/cloudman/). It is a great tool for small-scale DNA, RNA, ChIP, and single-cell RNA-seq analysis.

```
[Galaxy Workflows]()
- intersect SNPs with exons
- CHiP-seq
```

Galaxy [bioinformatics tutorials](https://training.galaxyproject.org/training-material/) for scientists are great to work through. Answer questions like [which exon on chr22 has the most SNPs](https://galaxyproject.org/tutorials/g101/), [which genes are differentially expressed in these RNA-seq datasets](https://usegalaxy.org/u/jeremy/p/galaxy-rna-seq-analysis-exercise), [NGS data quality control](https://www.youtube.com/watch?v=NH18hN9PdC8&ab_channel=UofMMSI), [how to call variants](https://training.galaxyproject.org/training-material/topics/variant-analysis/tutorials/dip/tutorial.html), [Metagenomics](https://galaxyproject.github.io/training-material/topics/metagenomics/).


### BEDtools and SAMtools
[BEDtools](https://bedtools.readthedocs.io/en/latest/) is described as a swiss army knife of tools for genomic analyses. The [BEDtools suite](https://bedtools.readthedocs.io/en/latest/content/bedtools-suite.html) allows one to [intersect](https://bedtools.readthedocs.io/en/latest/content/tools/intersect.html), [subtract](https://bedtools.readthedocs.io/en/latest/content/tools/subtract.html), [merge](https://bedtools.readthedocs.io/en/latest/content/tools/merge.html), count, complement, and shuffle genomic intervals from multiple files in widely-used genomic file formats such as BAM, BED, GFF/GTF, VCF. 

[SAMtools](http://www.htslib.org/) is useful for reading, writing, editing, indexing, and viewing SAM, BAM, and CRAM format files. [SAMtools suite](http://www.htslib.org/doc/samtools.html) include [view](http://www.htslib.org/doc/samtools-view.html) to convert file formats, [sort](http://www.htslib.org/doc/samtools-sort.html), and [index](http://www.htslib.org/doc/samtools-index.html) to create a BAM/SAM/CRAM index file.

BEDtools and SAMtools are also available via Galaxy.

### t-SNE
t-distributed Stochastic Neighboring Embedding (t-SNE) is a dimensionality reduction technique that calculates conditional probabilities and similarity. 
[t-SNE in R](./files/t-SNE.md)

### UMAP
A Uniform Manifold Approximation and Projection (UMAP) is a dimensionality reduction technique based in Riemannian geometry and algebraic topology. It constructs a fuzzy topological plot of data and optimizes low dimensional representation. It is useful for cluster visualization, particularly with RNA-seq. 
[UMAP in R](./files/UMAP.md)

### PCA
Principal component analysis (PCA) is the process of computing the principal components and using them to perform a change of basis on the data. PC1 is the most varying axis of data points, PC2 is the second most varying axis of data point that is independent from PC1, etc. 
[PCA in R](./files/PCA.md)

### Common Workflow Language
The [Common Workflow Language](https://www.commonwl.org/v1.2/index.html) (CWL) is a standard for describing computational data-analysis workflows. It is essentially a paradigm for implementing a series of connected command line tools to create reproducible and modular workflows. The set of tools, dependencies, and inputs that make up a CWL workflow are flexible and portable across any platform that supports the CWL standard. See the [CWL User Guide](https://www.commonwl.org/user_guide/) for more information. 

