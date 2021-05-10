# Gene Annotation and Structure
## Prokaryotic
### Structure
- mRNA is often **polycistronic**: multiple coding regions in one piece of mRNA
- an **operon** is a cluster of genes that are controlled by the same promoter
- a **transcription unit** denotes any segment of DNA that codes for an RNA molecule
  - an operon can encompass multiple transcriptional units
- _transcription start site_ versus _translation start site_

### Gene Prediction
- **open reading frame** (ORF) finders were originally used since prokaryotes generally don't have introns
- extension of OFR finding to predict the most likely CDS region, accuracy can be enhanced with comparative genomics like BLAST
- gene predictors are good at finding CDS but not great at finding mRNA sequences (including non-coding DNA)
  -  RNA-seq data can provide information on transcription start and stop sites, helping to complete gene annotations

### Prokaryotic Gene Prediction Algorithms
- [OFR finder](https://www.ncbi.nlm.nih.gov/orffinder/): identifies all ORFs, usually the longest ORFs that don't overlap are real genes
- [FGENESB](http://www.softberry.com/berry.phtml?topic=fgenesb&group=programs&subgroup=gfindb): includes a program for automatic GenBank annotation, finds coding regions, promoters, operons, translation and termination sites
- [GLIMMER](http://ccb.jhu.edu/software/glimmer/index.shtml): uses interpolated Markov models to identify the coding regions and distinguish them from noncoding DNA
-   [release notes](https://ccb.jhu.edu/software/glimmer/glim302notes.pdf)
- [Prodigal](https://bmcbioinformatics.biomedcentral.com/articles/10.1186/1471-2105-11-119): for CDS prediction
- [GeneMark](http://exon.gatech.edu/GeneMark/gmhmmp.cgi)
- [Easy Gene](http://www.cbs.dtu.dk/services/EasyGene/)

### E. coli Resources
- [EcoCyc](https://ecocyc.org/)
- [Regulon](http://regulondb.ccg.unam.mx/)
- [E. coli Genome Project](https://www.genome.wisc.edu/)
- [Porteco](http://porteco.org/)

### GC Content
- GC content tends to be higher in genes
- organisms can vary significantly in base composition, largely determined by codon usage (many amino acids are coded by multiple codons, some organisms prefer some codons over others)

### Some Useful Bacterial and Archaeal Databases and Programs
- [seqinr](https://a-little-book-of-r-for-bioinformatics.readthedocs.io/en/latest/src/chapter1.html): R package, allows simple analysis of FASTA-formatted sequences (base count, sequence length, GC content, and more)
- [PATRIC](https://patricbrc.org/): database of over 10,000 microbial genomes
- [HaloWeb](https://halo.umbc.edu/): 52 haloarchaeal species (archaeal species that grow in high salt concentrations)
- [UCSC Archaeal Genome Browser](http://archaea.ucsc.edu/)
- [Greengenes](https://greengenes.lbl.gov/Download/): repository for 16S rRNA sequences and tools

### Bacterial Promoters
- **Sigma (σ) Factor**: subunit of RNA polymerase that binds the promoter
  - binding area: sequences at -10 and -35 (relative to the TSS, not the start codon)
  - usually σ70 is used, in heat shock conditions σ32 is used
- **UP element**: alpha-subunit binding region, AT-rich region near -40 to -60
  - found in strong promoters 

### Bacterial Promoter Prediction Methods
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

## Eukaryotic 
