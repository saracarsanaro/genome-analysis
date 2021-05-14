## Genomic Databases
### NCBI Genome & Variation Viewer
_via Entrez Genome database - genomes of 306,892 prokaryotes, 42,119 viruses, and 15,544 eukaryotes_

The [NCBI Genome Data Viewer (GDV)](https://www.ncbi.nlm.nih.gov/genome/gdv/) mostly supports eukaryotic RefSeq genomes, plus other tracks including RNA-seq exon coverage, dbSNP, and more. More information is available on the [help page](https://www.ncbi.nlm.nih.gov/genome/gdv/browser/help/). The [NCBI Variation Viewer](https://www.ncbi.nlm.nih.gov/variation/view/) focuses on the human genome, and is connected to dbSNP, dbVar, and ClinVar. More information can be found via the [help page](https://www.ncbi.nlm.nih.gov/variation/view/help/) and this [video tutorial](https://www.youtube.com/watch?v=rnWZ9MFBwUM&ab_channel=TheNationalLibraryofMedicine). The [NCBI 1000 Genomes Browser](https://www.ncbi.nlm.nih.gov/variation/tools/1000genomes/) is a portal to data from the 10000 genomes project.

### Ensembl
_genome browser for chordates and non-chordate model organisms_

The [Ensembl Homepage](http://uswest.ensembl.org/index.html) allows you to pick a species and search for a chromosomal region, gene, or transcript. The [Chromosome View](http://uswest.ensembl.org/Homo_sapiens/Location/Chromosome?r=11) link within the location tab has data on protein coding genes, short & long non-coding genes, pseudogenes, %GC Repeats and variations on each chromosome. The [Region in Detail](http://uswest.ensembl.org/Homo_sapiens/Location/View?db=core;g=ENSG00000244734;r=11:5225386-5229473) link has information on transcripts, proteins, orthologs, paralogs, gene variation data, splice variants, %GC, and comparative genomes in that region. The location tab is specific to a chromosomal region and includes links for [Alignment](http://uswest.ensembl.org/Homo_sapiens/Location/Compara_Alignments?align=1944;db=core;g=ENSG00000244734;r=11:5225386-5229473;t=ENST00000485743), [Synteny Maps](http://uswest.ensembl.org/Homo_sapiens/Location/Synteny?align=1944;db=core;g=ENSG00000244734;r=11:5225386-5229473;t=ENST00000485743), and [Genetic Variation](http://uswest.ensembl.org/Homo_sapiens/Location/Variant/Table?align=1944;db=core;g=ENSG00000244734;r=11:5225386-5229473;t=ENST00000485743).

The [Gene Tab](http://uswest.ensembl.org/Homo_sapiens/Gene/Summary?db=core;g=ENSG00000244734;r=11:5225386-5229473;t=ENST00000485743) summary lists all transcripts and their associated protein products. The [Splice Variants](http://uswest.ensembl.org/Homo_sapiens/Gene/Splice?db=core;g=ENSG00000244734;r=11:5225386-5229473;t=ENST00000485743) link lists the transcripts and associated domains. Other links in the gene tab include [Orthologs](http://uswest.ensembl.org/Homo_sapiens/Gene/Compara_Ortholog?db=core;g=ENSG00000244734;r=11:5225386-5229473;t=ENST00000485743), [Paralogs](http://uswest.ensembl.org/Homo_sapiens/Gene/Compara_Paralog?db=core;g=ENSG00000244734;r=11:5225386-5229473;t=ENST00000485743), [Genetic Variation](http://uswest.ensembl.org/Homo_sapiens/Gene/Variation_Gene/Table?db=core;g=ENSG00000244734;r=11:5225386-5229473;t=ENST00000485743) data (including [PROVEAN](http://provean.jcvi.org/index.php), [PolyPhen](http://genetics.bwh.harvard.edu/pph2/), and ClinVar data), [Gene Expression](http://uswest.ensembl.org/Homo_sapiens/Gene/ExpressionAtlas?db=core;g=ENSG00000244734;r=11:5225386-5229473;t=ENST00000485743), [Pathways](http://uswest.ensembl.org/Homo_sapiens/Gene/Pathway?db=core;g=ENSG00000244734;r=11:5225386-5229473;t=ENST00000485743), and more. The [Transcript Tab](http://uswest.ensembl.org/Homo_sapiens/Transcript/Summary?db=core;g=ENSG00000244734;r=11:5225386-5229473;t=ENST00000485743) is similar to the gene tab except for a specific transcript. It has links to [Exons](http://uswest.ensembl.org/Homo_sapiens/Transcript/Exons?db=core;g=ENSG00000244734;r=11:5225386-5229473;t=ENST00000485743), [Protein Details](http://uswest.ensembl.org/Homo_sapiens/Transcript/ProteinSummary?db=core;g=ENSG00000244734;r=11:5225386-5229473;t=ENST00000485743) including domains, SNPs, and COSMIC data, plus much more. The [Ensembl YouTube Page](https://www.youtube.com/channel/UCKGzTZIXfs2HX44X3HqBtDA) has some great demos.

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

Some **_Tracks_** worth mentioning include UCSC Genes - gene prediction set from RefSeq, GenBank, and UniProt; Conservation - conservation data for up to 100 other species; SNPs - variation data; GTEx - gene expression; ENCODE - regulation data including histone modifications, ClinVar and ClinGen, and dbSNP. 

### UCSC Table Browser
_method for downloading data from UCSC_

The [Table Browser](http://genome.ucsc.edu/cgi-bin/hgTables) is incredibly useful for downloading data from UCSC. This [user guide](https://genome.ucsc.edu/goldenPath/help/hgTablesHelp.html#Filter) details how to use the table browser. You must choose the genome, assembly, track, and table to pull from. You can limit to a specific region in the genome and add other filters. You can specify the output file type, and there is an option to export directly to Galaxy. 

### Galaxy
_interface designed to analyze genomic data both from publicly available databases (Ensembl, UCSC) and user-derived data_

Galaxy can be accessed via the [Web Interface](https://usegalaxy.org/), [locally](https://galaxyproject.org/admin/get-galaxy/), [on the cloud](https://galaxyproject.org/cloudman/). It is a great tool for small-scale DNA, RNA, ChIP, and single-cell RNA-seq analysis.

```
Galaxy Workflows
- list here
```

Galaxy [bioinformatics tutorials](https://training.galaxyproject.org/training-material/) for scientists are great to work through. Answer questions like [which exon on chr22 has the most SNPs](https://galaxyproject.org/tutorials/g101/), [which genes are differentially expressed in these RNA-seq datasets](https://usegalaxy.org/u/jeremy/p/galaxy-rna-seq-analysis-exercise), [NGS data quality control](https://www.youtube.com/watch?v=NH18hN9PdC8&ab_channel=UofMMSI), [how to call variants](https://training.galaxyproject.org/training-material/topics/variant-analysis/tutorials/dip/tutorial.html).

### IGV
_a local data visualization application designed to efficiently handle large genomic data sets at high and low resolutions_

IGV is a local application for visualizing various types of genomic data. IGV supports many data types, includinig BAM, BED, BigWig, GTF, and VCF. To load data, first select a reference genome. Then load data from a file, a URL, or from the server (dbSNP, TCGA, ENCODE, 1000 genomes). To view data, select/search for a chromosomal region or a gene. Depending on the datatype, additional features may be available (like Sashimi plot  or BLAT). See the [IGV User Guide](https://software.broadinstitute.org/software/igv/UserGuide) for more details. 

### ClinVar
_curated database of genomic variation and its relationship to human health_ 

[ClinVar](https://www.ncbi.nlm.nih.gov/clinvar/) is a useful database of variation and phenotypiic or clinical relevance. Search ClinVar by **gene symbol** - BRCA1[gene], **disease** - "breast cancer"[dis], and/or other terms. ClinVar filters include _clinical significance_, _review status_, _molecular consequence_, and _variation type_. Click on the variant for the supporting evidence and citations for the variant classification. 

### ENCODE
_a catalog functional elements in the human genome_

The Encyclopedia of DNA Elements ([ENCODE](https://www.encodeproject.org/)) Project is a catalog functional elements in the human genome. UCSC has many ENCODE tracks, which are distinguishable by the ENCODE symbol. 
Some ENCODE tracks include: 
- **_Transcription_**: transcription levels assayed by RNA-seq on 9 cell lines
- **_Layered H3K4Me1_**:  H3K4Me1 Mark (Often Found Near _Regulatory Elements_) on 7 cell lines
- **_Layered H3K4Me3_**: H3K4Me3 Mark (Often Found Near _Promoters_) on 7 cell lines 
- **_DNase Clusters_**: H3K27Ac Mark (Often Found Near _Regulatory Elements_) on 7 cell lines
- **_DNase Clusters_**: DNase I Hypersensitivity Peak Clusters (95 cell types)
- **_DNase Signal_**:  DNase I Hypersensitivity Signal Colored by Similarity
- **_DNase HS_**: DNase I Hypersensitivity in 95 cell types
- **_BU ORChID_**: shows DNA cleavage sites.

There is also a [Mouse ENCODE](https://www.nature.com/articles/nature13992) project, with the goal of applying comparative genomics to the human ENCODE project.
