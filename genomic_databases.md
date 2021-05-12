## Genomic Databases
### NCBI Genome & Variation Viewer
_via Entrez Genome database - genomes of 306,892 prokaryotes, 42,119 viruses, and 15,544 eukaryotes_

The [NCBI Genome Data Viewer (GDV)](https://www.ncbi.nlm.nih.gov/genome/gdv/) mostly supports eukaryotic RefSeq genomes, plus other tracks including RNA-seq exon coverage, dbSNP, and more. More information is available on the [help page](https://www.ncbi.nlm.nih.gov/genome/gdv/browser/help/). The [NCBI Variation Viewer](https://www.ncbi.nlm.nih.gov/variation/view/) focuses on the human genome, and is connected to dbSNP, dbVar, and ClinVar. More information can be found via the [help page](https://www.ncbi.nlm.nih.gov/variation/view/help/) and this [video tutorial](https://www.youtube.com/watch?v=rnWZ9MFBwUM&ab_channel=TheNationalLibraryofMedicine).

### Ensembl
_genome browser for chordates and non-chordate model organisms_

The [Ensembl Homepage](http://uswest.ensembl.org/index.html) allows you to pick a species and search for a chromosomal region, gene, or transcript. The [Chromosome View](http://uswest.ensembl.org/Homo_sapiens/Location/Chromosome?r=11) link within the location tab has data on protein coding genes, short & long non-coding genes, pseudogenes, %GC Repeats and variations on each chromosome. The [Region in Detail](http://uswest.ensembl.org/Homo_sapiens/Location/View?db=core;g=ENSG00000244734;r=11:5225386-5229473) link has information on transcripts, proteins, orthologs, paralogs, gene variation data, splice variants, %GC, and comparative genomes in that region. The location tab is specific to a chromosomal region and includes links for [Alignment](http://uswest.ensembl.org/Homo_sapiens/Location/Compara_Alignments?align=1944;db=core;g=ENSG00000244734;r=11:5225386-5229473;t=ENST00000485743), [Synteny Maps](http://uswest.ensembl.org/Homo_sapiens/Location/Synteny?align=1944;db=core;g=ENSG00000244734;r=11:5225386-5229473;t=ENST00000485743), and [Genetic Variation](http://uswest.ensembl.org/Homo_sapiens/Location/Variant/Table?align=1944;db=core;g=ENSG00000244734;r=11:5225386-5229473;t=ENST00000485743).

The [Gene Tab](http://uswest.ensembl.org/Homo_sapiens/Gene/Summary?db=core;g=ENSG00000244734;r=11:5225386-5229473;t=ENST00000485743) summary lists all transcripts and their associated protein products. The [Splice Variants](http://uswest.ensembl.org/Homo_sapiens/Gene/Splice?db=core;g=ENSG00000244734;r=11:5225386-5229473;t=ENST00000485743) link lists the transcripts and associated domains. Other links in the gene tab include [Orthologs](http://uswest.ensembl.org/Homo_sapiens/Gene/Compara_Ortholog?db=core;g=ENSG00000244734;r=11:5225386-5229473;t=ENST00000485743), [Paralogs](http://uswest.ensembl.org/Homo_sapiens/Gene/Compara_Paralog?db=core;g=ENSG00000244734;r=11:5225386-5229473;t=ENST00000485743), [Genetic Variation](http://uswest.ensembl.org/Homo_sapiens/Gene/Variation_Gene/Table?db=core;g=ENSG00000244734;r=11:5225386-5229473;t=ENST00000485743) data, [Gene Expression](http://uswest.ensembl.org/Homo_sapiens/Gene/ExpressionAtlas?db=core;g=ENSG00000244734;r=11:5225386-5229473;t=ENST00000485743), [Pathways](http://uswest.ensembl.org/Homo_sapiens/Gene/Pathway?db=core;g=ENSG00000244734;r=11:5225386-5229473;t=ENST00000485743), and more. The [Transcript Tab](http://uswest.ensembl.org/Homo_sapiens/Transcript/Summary?db=core;g=ENSG00000244734;r=11:5225386-5229473;t=ENST00000485743) is similar to the gene tab except for a specific transcript. It has links to [Exons](http://uswest.ensembl.org/Homo_sapiens/Transcript/Exons?db=core;g=ENSG00000244734;r=11:5225386-5229473;t=ENST00000485743), [Protein Details](http://uswest.ensembl.org/Homo_sapiens/Transcript/ProteinSummary?db=core;g=ENSG00000244734;r=11:5225386-5229473;t=ENST00000485743) including domains, SNPs, and COSMIC data, plus much more. The [Ensembl YouTube Page](https://www.youtube.com/channel/UCKGzTZIXfs2HX44X3HqBtDA) has some great demos.

[Ensembl Genomes](http://ensemblgenomes.org/) is the Ensembl browser for non-vertebrates including bacteria, protists, fungi, plants, and invertebrate metazoa.

### BioMart
_download data sets from Ensembl_

[BioMart](http://uswest.ensembl.org/biomart/martview/c92977310e04989e7c0a23d938ed684b) is a great tool for mining data from Ensembl. This [video tutorial](https://www.youtube.com/watch?v=DXPaBdPM2vs&list=PLA5333E28D1193B6B&index=5&ab_channel=EnsemblTraining) gives a basic overview of BioMart. Choose **_Filters_** to limit your data and select **_Attributes_** to display in the output dataset (tsv). 

The [Bioconductor Project](https://www.bioconductor.org/) is a collection of R packages created to mine data from genomic datasources. [BiomaRt](https://bioconductor.org/packages/release/bioc/vignettes/biomaRt/inst/doc/biomaRt.html) is a bioconductor package to access data from BioMart. The [user guide](https://bioconductor.org/packages/release/bioc/vignettes/biomaRt/inst/doc/biomaRt.html) is a useful resource for biomaRt.

```
- getBM command problems
-   specify attributes, filters, values, and mart 
-   to do x
-   to do y
```

### UCSC
_data from 97 eukaryotic genomes including 49 mammals_

The [UCSC Genome Browser](http://genome.ucsc.edu/) database holds assembly data, precomputed comparative genomic data, mRNA, EST, and RefSeq gene alignments, ENCODE data, and links to NCBI Map Viewer and Ensembl. Each assembly has a number of tracks that can be displayed or hidden for a region. The track display options are: **_Hide_** - don't display; **_Dense_** - features are displayed but collapse into a single line; **_Full_** - each annotation feature is displayed on a separate line; **_Squish_** - each annotation is displayed at 50% height and unlabeled; **_Pack_** - similar to squish mode except labeled.

Some **_Tracks_** worth mentioning include UCSC Genes - gene prediction set from RefSeq, GenBank, and UniProt; Conservation - conservation data for up to 100 other species; SNPs - variation data; GTEx - gene expression; ENCODE - regulation data including histones. 

### UCSC Table Browser
_method for downloading data from UCSC_

[Table Browser](http://genome.ucsc.edu/cgi-bin/hgTables)

### Galaxy
_interface designed to analyze genomic data both from publicly available databases (Ensembl, UCSC) and user-derived data_

Galaxy can be accessed via the [Web Interface](https://usegalaxy.org/), [locally](https://galaxyproject.org/admin/get-galaxy/), [on the cloud](https://galaxyproject.org/cloudman/). It is a great tool for small-scale DNA, RNA, ChIP, and single-cell RNA-seq analysis.

```
Galaxy Workflows
- list here
```

Galaxy [bioinformatics tutorials](https://training.galaxyproject.org/training-material/) for scientists are great to work through.

### IGV
_a local data visualization application designed to handle large data sets - browse at high resolution for small regions and lower resolution for larger regions_

loading data
- supports many data types - BED, BigWig
- accessing genomes 
- load data from server, a file or a URL

viewing data


### ENCODE
