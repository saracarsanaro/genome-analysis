# NGS Tools and Technologies

### Galaxy
Galaxy is an interface designed to analyze genomic data both from publicly available databases (Ensembl, UCSC) and user-derived data. It can be accessed via the [Web Interface](https://usegalaxy.org/), [locally](https://galaxyproject.org/admin/get-galaxy/), [on the cloud](https://galaxyproject.org/cloudman/). It is a great tool for small-scale DNA, RNA, ChIP, and single-cell RNA-seq analysis.

Galaxy [bioinformatics tutorials](https://training.galaxyproject.org/training-material/) for scientists are great to work through. There are tutorials for:
- questions like [which exon on chr22 has the most SNPs](https://galaxyproject.org/tutorials/g101/)
- determining [which genes are differentially expressed in these RNA-seq datasets](https://usegalaxy.org/u/jeremy/p/galaxy-rna-seq-analysis-exercise)
- performing [NGS data quality control](https://www.youtube.com/watch?v=NH18hN9PdC8&ab_channel=UofMMSI)
- [variant calling](https://training.galaxyproject.org/training-material/topics/variant-analysis/tutorials/dip/tutorial.html)
- [metagenomics analyses](https://galaxyproject.github.io/training-material/topics/metagenomics/)

### Galaxy Workflows
- [intersect with SNPs and exons](/files/galaxy_cow_workflow.md)
- [CHiP-seq analysis](/files/mouse_ChIP.md)
- [produce a VCF of SNPs from FASTQ](/files/SNP_calling.md)

### BEDtools and SAMtools
[BEDtools](https://bedtools.readthedocs.io/en/latest/) is described as a swiss army knife of tools for genomic analyses. The [BEDtools suite](https://bedtools.readthedocs.io/en/latest/content/bedtools-suite.html) allows one to [intersect](https://bedtools.readthedocs.io/en/latest/content/tools/intersect.html), [subtract](https://bedtools.readthedocs.io/en/latest/content/tools/subtract.html), [merge](https://bedtools.readthedocs.io/en/latest/content/tools/merge.html), count, complement, and shuffle genomic intervals from multiple files in widely-used genomic file formats such as BAM, BED, GFF/GTF, VCF. 

[SAMtools](http://www.htslib.org/) is useful for reading, writing, editing, indexing, and viewing SAM, BAM, and CRAM format files. [SAMtools suite](http://www.htslib.org/doc/samtools.html) include [view](http://www.htslib.org/doc/samtools-view.html) to convert file formats, [sort](http://www.htslib.org/doc/samtools-sort.html), and [index](http://www.htslib.org/doc/samtools-index.html) to create a BAM/SAM/CRAM index file.

BEDtools and SAMtools are also available via Galaxy.

### t-SNE
t-distributed Stochastic Neighboring Embedding (t-SNE) is a dimensionality reduction technique that calculates conditional probabilities and similarity. 
```R
training_data ← iris[,1:4] #prepare a training dataset
real_data ← training_data + matrix(rnorm(nrow(training_data)*4,0,0.1), ncol=4) #real data (training dataset with some fluctuations)
view(real_data)
#t-SNE#
library(Rtsne), library(ggplot2)
tSNE_results ← Rtsne(perturbed.embedding, header=T)
X_values_tsne ← tSNE_results$Y[,1]
Y_values_tsne ← tSNE_results$Y[,2]
XY_values_tsne_as_dataframe ← data.frame(X_values_tsne, Y_values_tsne)
ggplot(data = XY_values_tsne_as_dataframe, aes(x=X_values_tsne, y = Y_values_tsne)) + geom_point() 
```
### UMAP
A Uniform Manifold Approximation and Projection (UMAP) is a dimensionality reduction technique based in Riemannian geometry and algebraic topology. It constructs a fuzzy topological plot of data and optimizes low dimensional representation. It is useful for cluster visualization, particularly with RNA-seq. 
```R
install.packages("umap")
library("umap")
training_data ← iris[,1:4] #prepare a training dataset
real_data ← training_data + matrix(rnorm(nrow(training_data)*4,0,0.1), ncol=4) #real data (training dataset with some fluctuations)
view(real_data)
training_data_umap_results ← umap(training_data) #umap on training data
real_data_umap_results ← predict(training_data_umap_results, real_data) #predict the clustering of real_data based on training data's umap results
#ggplot for visualization
X_values_umap ← real_data_umap_results[,1]
Y_values_umap ← real_data_umap_results[,2]
XY_values_umap_as_dataframe ← data.frame(X_values_umap, Y_values_umap)
library(ggplot2)
ggplot(data = XY_values_umap_as_dataframe, aes(x=X_values_umap, y=Y_values_umap)) + geom_point()
```
### PCA
Principal component analysis (PCA) is the process of computing the principal components and using them to perform a change of basis on the data. PC1 is the most varying axis of data points, PC2 is the second most varying axis of data point that is independent from PC1, etc. 
```R
training_data ← iris[,1:4] #prepare a training dataset
real_data ← training_data + matrix(rnorm(nrow(training_data)*4,0,0.1), ncol=4) #real data (training dataset with some fluctuations)
view(real_data)
library(ggplot2)
PCA_results ← prcomp(perturbed.embedding)
X_values_PCA ← PCA_results$x[,1]
Y_values_PCA ← PCA_results$x[,2]
XY_values_PCA_as_dataframe ← data.frame(X_values_PCA, Y_values_PCA)
ggplot(data = XY_values_PCA_as_dataframe, aes(x=X_values_PCA, y=Y_values_PCA)) + geom_point()
```
### Common Workflow Language
The [Common Workflow Language](https://www.commonwl.org/v1.2/index.html) (CWL) is a standard for describing computational data-analysis workflows. It is essentially a paradigm for implementing a series of connected command line tools to create reproducible and modular workflows. The set of tools, dependencies, and inputs that make up a CWL workflow are flexible and portable across any platform that supports the CWL standard. See the [CWL User Guide](https://www.commonwl.org/user_guide/) for more information. 

