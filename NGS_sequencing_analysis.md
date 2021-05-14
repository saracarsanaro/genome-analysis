## NGS Sequencing and Analysis: DNA
### Genome Sequence Assembly

### Variant Calling

### Galaxy (move here)

### BEDtools and SAMtools
[BEDtools](https://bedtools.readthedocs.io/en/latest/) is described as a swiss army knife of tools for genomic analyses. The [BEDtools suite](https://bedtools.readthedocs.io/en/latest/content/bedtools-suite.html) allows one to [intersect](https://bedtools.readthedocs.io/en/latest/content/tools/intersect.html), [subtract](https://bedtools.readthedocs.io/en/latest/content/tools/subtract.html), [merge](https://bedtools.readthedocs.io/en/latest/content/tools/merge.html), count, complement, and shuffle genomic intervals from multiple files in widely-used genomic file formats such as BAM, BED, GFF/GTF, VCF. 

[SAMtools](http://www.htslib.org/) is useful for reading, writing, editing, indexing, and viewing SAM, BAM, and CRAM format files. [SAMtools suite](http://www.htslib.org/doc/samtools.html) include [view](http://www.htslib.org/doc/samtools-view.html) to convert file formats, [sort](http://www.htslib.org/doc/samtools-sort.html), and [index](http://www.htslib.org/doc/samtools-index.html) to create a BAM/SAM/CRAM index file.

BEDtools and SAMtools are also available via Galaxy.

### SNPs
A polymorphism involves one of two or more variants of a particular DNA sequence, with some definitions requiring the least common allele to have a frequency of about 1% or greater. A SNP is a substitution of a single nucleotide at a specific position in the genome. 

The functional consequences of a SNP include _coding_ - protein variation; _silent_ - doesn't impact protein coding but may impact splicing; _promoter or regulatory_ - may impact expression; and _other_ - no known impact, useful as a chromosomal marker. 

The three categories of SNPs are _synonymous_ - coding region, amino acid doesn't change; _non-synonymous_ - coding region, amino acid changes; and _noncoding_ - in a noncoding region.

A number of SNP databases exist. [dbSNP](https://www.ncbi.nlm.nih.gov/snp/) via NCBI is the largest database of SNPs, MNPs, and short indels. [SNPEffect](https://snpeffect.switchlab.org/) focuses on predicting the impact of SNPs on the structural phenotype of proteins. [SNPedia](https://www.snpedia.com/index.php/SNPedia) is a wiki that collects information from publications on known SNPs and their clinical effects. The [1000 Genomes Browser](https://www.ncbi.nlm.nih.gov/variation/tools/1000genomes/) and [Variation Viewer](https://www.ncbi.nlm.nih.gov/variation/view/) are good resources for visualizing SNPs. [ClinVar](https://www.ncbi.nlm.nih.gov/clinvar/) is a curated database of variants and their phenotypic or clinical relevance.

### CNVs
Copy number variation and other structural variations have been identified in human, chimp, fly, and mouse genomes. The microhomology-mediated break induced replication ([MMBIR](https://pubmed.ncbi.nlm.nih.gov/19597530/)) method may explain where there seem to be hotspots in genomes for CNVs. Non-allelic homologous recombination ([NAHR](https://genomebiology.biomedcentral.com/articles/10.1186/s13059-015-0633-1)) is also linked to copy number variations, deletions, and inversions. CNVs can be neutral or linked to disease.

The [Database of Genomic Variants](http://dgv.tcag.ca/dgv/app/home) has a DGV Structural Variants track to visualize CNVs, which is also found on UCSC. Other CNV databases include [DECIPHER](https://www.deciphergenomics.org/) - the DatabasE of Chromosomal Imbalance and Phenotype in Humans, [Variation Viewer](https://www.ncbi.nlm.nih.gov/variation/view/) - exon pattern track and dbVar ClinVar Large Variations track, [gnomAD SVs](https://gnomad.broadinstitute.org/region/1-55505221-55530525?dataset=gnomad_sv_r2_1) - visualize structural variants in the population, and NCBI's [dbVAR](https://www.ncbi.nlm.nih.gov/dbvar/). 



