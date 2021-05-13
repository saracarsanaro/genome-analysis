# Gene Annotation and Structure
## Eukaryotic 
### De Novo versus Expression Based Gene Prediction
**Expression** based prediction aligns cDNA and protein to genomic sequences to predict the coding region of gene. The primary limitation is lack of cDNA or EST data in a sample (genomic data). **De Novo** based prediction is used when expression-based fails. It relies on content or signal sensors (or both). The primary limitation is false positives. Gene predictors are good with coding regions, but usually struggle with 5' and 3' UTRs. RNA-seq has uncovered many new transcripts, some which different in UTR regions only.

Some **Expression Based Prediction** methods include: [Splign](https://www.ncbi.nlm.nih.gov/sutils/splign/splign.cgi?textpage=online&level=form): aligns cDNA to genomic DNA; [genomic BLAST](https://blast.ncbi.nlm.nih.gov/Blast.cgi?PAGE_TYPE=BlastSearch&BLAST_SPEC=MicrobialGenomes): aligns DNA to NCBI genomic sequences, RefSEq, and EST sequences; and [BLAT](http://genome.ucsc.edu/cgi-bin/hgBlat?command=start): aligns cDNA to genomic DNA. Some **De Novo Gene Prediction** methods include: [GENESCAN](http://hollywood.mit.edu/GENSCAN.html): predicts exons, CDS, start, stop, splice donor and acceptor sites, polyA signal, and promoter; [HMMGene](http://www.cbs.dtu.dk/services/HMMgene/): uses Hidden Markov Model to predict exons, CDS, start, stop, splice donor and acceptor sites; [GGENESH](http://www.softberry.com/berry.phtml?topic=fgenesh&group=programs&subgroup=gfind); and [Augustus](http://bioinf.uni-greifswald.de/augustus/).

**Content Sensors** are prediction algorithms that depend on features inherent to the coding sequence. For example, the third base (nucleotide) composition is often used in bacteria. Hexamer (codon bias and dicodon combinations) frequency is the most reliable content sensor. **Signal Sensors** are clues that programs use to find genes based on a particular sequence that is associated with a gene. Some examples include a promoter, splice site, or poly(A) signal. A position-specific scoring matrix (PSSM) can give more weigh to more conserved positions.

### Eukaryotic Genome Features

mRNA is processed after transcription, most notably via splicing. The splicing process is independent of CDS location.

Genomic regions with 50% GC content or more tend to have high **Gene Density**. The overall CG content of the human genome is 41%, however some regions differ severely from this average. 

**CpG Islands** are regions with high concentraions of CpG (C followed by G on the same strand). CpG should occur at 4.41% frequency in the genome, however it actually occurs at less than 1% frequency. CpG Islands are believed to be associated with promoters and transcription start sites. The CpG Track is available via UCSC. 

Approximately 10% of the human genome consists of **Repeats**. Repeat DNA likely plays a role in eukaryotic life, however the specific nature is unclear.  

**Aneuploidy**, **Inversions**, **Chromosome number and synteny**

**Sequence tagged sites**

### Functional RNAs


### Conserved Noncoding Elements
[ANCORA](), [cneViewer](), [UCNEBase](), and [CEGA]()

## Prokaryotic
### Gene Structure
mRNA is often **polycistronic**, with multiple coding regions in one piece of mRNA. An **operon** is a cluster of genes that are controlled by the same promoter, while a **transcription unit** denotes any segment of DNA that codes for an RNA molecule. An operon can encompass multiple transcriptional units.
**GC content** tends to be higher in genes. Organisms can vary significantly in base composition, largely determined by codon usage (many amino acids are coded by multiple codons, some organisms prefer some codons over others).

### Gene Prediction
**Open Reading Frame** (ORF) finders are originally used since prokaryotes generally don't have introns. An extension of OFR finding then predicts the most likely CDS region, and accuracy can be enhanced with comparative genomics like BLAST. Gene predictors are good at finding CDS but not great at finding mRNA sequences (including non-coding DNA). RNA-seq data can provide information on transcription start and stop sites, helping to complete gene annotations. Some **Prokaryotic Gene Prediction Algorithms** include [OFR finder](https://www.ncbi.nlm.nih.gov/orffinder/): identifies all ORFs, usually the longest ORFs that don't overlap are real genes; [FGENESB](http://www.softberry.com/berry.phtml?topic=fgenesb&group=programs&subgroup=gfindb): includes a program for automatic GenBank annotation, finds coding regions, promoters, operons, translation and termination sites; [GLIMMER](http://ccb.jhu.edu/software/glimmer/index.shtml): uses interpolated Markov models to identify the coding regions and distinguish them from noncoding DNA - see [GLIMMER release notes](https://ccb.jhu.edu/software/glimmer/glim302notes.pdf); [Prodigal](https://bmcbioinformatics.biomedcentral.com/articles/10.1186/1471-2105-11-119): for CDS prediction; [GeneMark](http://exon.gatech.edu/GeneMark/gmhmmp.cgi); and [Easy Gene](http://www.cbs.dtu.dk/services/EasyGene/).

### Bacterial Promoters
Two important elements of bacterial promoters are the sigma factor and UP element. The **Sigma (σ) Factor** is the subunit of RNA polymerase that binds the promoter. The sigma factor binding area sequences are at -10 and -35 (relative to the TSS, not the start codon). Usually σ70 is used, in heat shock conditions σ32 is used. The **UP element** is alpha-subunit binding region, and AT-rich region near -40 to -60 that is found in strong promoters.  

**Bacterial Promoter Prediction Methods** include comparative genomics, identifying unique promoter sequences, and incorporating microarray and RNA-seq data.
- comparative genomics: compare intergenic regions of related species
  - appropriate evolutionary distance is important - too closely related species will lead to false positives, too far apart only well-conserved promoters are detected
- identifying unique promoter sequences: identify consensus sequences in the intergenic regions
  - pros: good at finding promoters similar to those in the training set
  - cons: false positives, may miss unusual promoters
- incorporating microarray and RNA-seq data
  - identify co-expressed genes that may share common regulators 
  - [CTSP tool](http://cstp.molgen.mpg.de/) and [BioProspector](http://ai.stanford.edu/~xsliu/BioProspector/)

### Bacterial Promoter Predictors
- [BPROM](http://www.softberry.com/berry.phtml?topic=bprom&group=programs&subgroup=gfindb): to identify σ70 promoters
- [Neural Network Promoter Prediction](https://www.fruitfly.org/seq_tools/promoter.html)

### Prokaryotic Resources
Some E. coli resources include [EcoCyc](https://ecocyc.org/); [Regulon](http://regulondb.ccg.unam.mx/); [E. coli Genome Project](https://www.genome.wisc.edu/); and [Porteco](http://porteco.org/). Other bacterial and archaeal databases and programs include [seqinr](https://a-little-book-of-r-for-bioinformatics.readthedocs.io/en/latest/src/chapter1.html) an R package that allows simple analysis of FASTA-formatted sequences (base count, sequence length, GC content, and more); [PATRIC](https://patricbrc.org/) a database of over 10,000 microbial genomes; [HaloWeb](https://halo.umbc.edu/) a database of 52 haloarchaeal species (archaeal species that grow in high salt concentrations); the [UCSC Archaeal Genome Browser](http://archaea.ucsc.edu/); and [Greengenes](https://greengenes.lbl.gov/Download/) a repository for 16S rRNA sequences and tools.


## Model Organisms
### Yeast
**Saccharomyces cerevisiae** is a well-studied eukaryote that grows like a prokaryote. Only 4% of the genes have introns and there is very little intergenic space. ORF finding works well to identify genes in s. cerevisiae. [NCBI Genome Data Viewer](https://www.ncbi.nlm.nih.gov/genome/gdv/?org=saccharomyces-cerevisiae) and [UCSC]() are good general resources for s. cerevisiae. [SDG](http://genome.ucsc.edu/cgi-bin/hgGateway?hgsid=155744526&clade=other&org=0&db=0) is an extensive resource for budding yeast genomes, including genome browsing, info on ORFs and protein domains, 3D structures, BLAST, ontology terms, and gene expression data. [ScerTF](http://stormo.wustl.edu/ScerTF) is a database of s. cerevisiae transcription factors. 

**Gene Duplication** occurs often in eukaryotes, with 4 broad fates after gene duplication: both copies remain w/ little mutation providing extra source for transcription/gene expression; one copy is deleted or permanently damaged; one copy accumulates mutations & becomes a pseudogene; and paralogous - one or both copies evolve to have different functions. The deletion fate is most common. The [Yeast Gene Order Browser](http://ygob.ucd.ie/) is a tool for visualising the syntenic context of any gene from several yeast genomes.

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
