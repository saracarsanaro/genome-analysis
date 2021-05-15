# Gene Annotation and Structure
## Prokaryotic
### Gene Structure
Prokaryotic mRNA is often **polycistronic**, with multiple coding regions in one piece of mRNA. An **operon** is a cluster of genes that are controlled by the same promoter, while a **transcription unit** denotes any segment of DNA that codes for an RNA molecule. An operon can encompass multiple transcriptional units.
**GC content** tends to be higher in genes. Organisms can vary significantly in base composition, largely determined by codon usage (many amino acids are coded by multiple codons, some organisms prefer some codons over others).

### Gene Prediction
**Open Reading Frame** (ORF) finders are often used since prokaryotes generally don't have introns. An extension of OFR finding then predicts the most likely CDS region, and accuracy can be enhanced with comparative genomics like BLAST. Gene predictors are good at finding CDS but not great at finding mRNA sequences (including non-coding regions). RNA-seq data can provide information on transcription start and stop sites, helping to complete gene annotations. Some **Prokaryotic Gene Prediction Algorithms** include [OFR finder](https://www.ncbi.nlm.nih.gov/orffinder/): identifies all ORFs, usually the longest ORFs that don't overlap are real genes; [FGENESB](http://www.softberry.com/berry.phtml?topic=fgenesb&group=programs&subgroup=gfindb): includes a program for automatic GenBank annotation, finds coding regions, promoters, operons, translation and termination sites; [GLIMMER](http://ccb.jhu.edu/software/glimmer/index.shtml): uses interpolated Markov models to identify the coding regions and distinguish them from noncoding DNA - see [GLIMMER release notes](https://ccb.jhu.edu/software/glimmer/glim302notes.pdf); [Prodigal](https://bmcbioinformatics.biomedcentral.com/articles/10.1186/1471-2105-11-119): for CDS prediction; [GeneMark](http://exon.gatech.edu/GeneMark/gmhmmp.cgi); and [Easy Gene](http://www.cbs.dtu.dk/services/EasyGene/).

### [Analysis](/files/Glimmer.md) from GLIMMER and FGENESB on a Halanaerobium contig

### Bacterial Promoters
Two important elements of bacterial promoters are the sigma factor and UP element. The **Sigma (σ) Factor** is the subunit of RNA polymerase that binds the promoter. The sigma factor binding area sequences are at -10 and -35 (relative to the TSS, not the start codon). Normally σ70 is used, in heat shock conditions σ32 is used. The **UP element** is alpha-subunit binding region, and AT-rich region near -40 to -60 that is found in strong promoters.  

**Bacterial Promoter Prediction Methods** include comparative genomics, identifying unique promoter sequences, and incorporating microarray and RNA-seq data. _Comparative genomics_ compares intergenic regions of related species. The appropriate evolutionary distance is important - too closely related species will lead to false positives, too far apart only well-conserved promoters are detected. _Identifying unique promoter sequences_ works by identifying consensus sequences in the intergenic regions. The pros: good at finding promoters similar to those in the training set; the cons: false positives, may miss unusual promoters. _Incorporating microarray and RNA-seq data_ can be used to identify co-expressed genes that may share common regulators. 

The [CTSP tool](http://cstp.molgen.mpg.de/) and [BioProspector](http://ai.stanford.edu/~xsliu/BioProspector/) are promoter predictors that incorporate microarray and RNA-seq data. Other **Bacterial Promoter Predictors** include [BPROM](http://www.softberry.com/berry.phtml?topic=bprom&group=programs&subgroup=gfindb) to identify σ70 promoters, and the [Neural Network Promoter Prediction](https://www.fruitfly.org/seq_tools/promoter.html) tool. 

![NNPP](/files/NNPP_output.png)

output from NNPP algorithm on a Lactococcus DNA sequence

### Prokaryotic Resources
Some E. coli resources include [EcoCyc](https://ecocyc.org/); [Regulon](http://regulondb.ccg.unam.mx/); [E. coli Genome Project](https://www.genome.wisc.edu/); and [Porteco](http://porteco.org/). Other bacterial and archaeal databases and programs include [seqinr](https://a-little-book-of-r-for-bioinformatics.readthedocs.io/en/latest/src/chapter1.html), an R package that allows simple analysis of FASTA-formatted sequences (base count, sequence length, GC content, and more); [PATRIC](https://patricbrc.org/), a database of over 10,000 microbial genomes; [HaloWeb](https://halo.umbc.edu/), a database of 52 haloarchaeal species (archaeal species that grow in high salt concentrations); the [UCSC Archaeal Genome Browser](http://archaea.ucsc.edu/); and [Greengenes](https://greengenes.lbl.gov/Download/) a repository for 16S rRNA sequences and tools.

## Eukaryotic 
### De Novo versus Expression Based Gene Prediction
**Expression** based prediction aligns cDNA and protein to genomic sequences to predict the coding region of gene. The primary limitation is lack of cDNA or EST data in a sample (genomic data). **De Novo** based prediction is used when expression-based fails. It relies on content or signal sensors (or both). The primary limitation is false positives. Gene predictors are good with coding regions, but usually struggle with 5' and 3' UTRs. RNA-seq has uncovered many new transcripts, some which differ in UTR regions only.

Some **Expression Based Prediction** methods include: [Splign](https://www.ncbi.nlm.nih.gov/sutils/splign/splign.cgi?textpage=online&level=form): aligns cDNA to genomic DNA; [genomic BLAST](https://blast.ncbi.nlm.nih.gov/Blast.cgi?PAGE_TYPE=BlastSearch&BLAST_SPEC=MicrobialGenomes): aligns DNA to NCBI genomic sequences, RefSEq, and EST sequences; and [BLAT](http://genome.ucsc.edu/cgi-bin/hgBlat?command=start): aligns cDNA to genomic DNA. Some **De Novo Gene Prediction** methods include: [GENESCAN](http://hollywood.mit.edu/GENSCAN.html): predicts exons, CDS, start, stop, splice donor and acceptor sites, polyA signal, and promoter; [HMMGene](http://www.cbs.dtu.dk/services/HMMgene/): uses Hidden Markov Model to predict exons, CDS, start, stop, splice donor and acceptor sites; [GGENESH](http://www.softberry.com/berry.phtml?topic=fgenesh&group=programs&subgroup=gfind); and [Augustus](http://bioinf.uni-greifswald.de/augustus/).

![Splign](/files/Splign.png)

output from Splign on mouse cDNA aligned to genomic DNA

**Content Sensors** are prediction algorithms that depend on features inherent to the coding sequence. For example, the third base (nucleotide) composition is often used in bacteria. Hexamer (codon bias and dicodon combinations) frequency is the most reliable content sensor. **Signal Sensors** are clues that programs use to find genes based on a particular sequence that is associated with a gene. Some examples include a promoter, splice site, or poly(A) signal. A position-specific scoring matrix (PSSM) can give more weigh to more conserved positions.

### Eukaryotic Genome Features

mRNA is processed after transcription, most notably via splicing. The splicing process is independent of CDS location. Gene expression depends on transcription factor binding and access, and chromatin plays a major role in transcription factor access. 

Genomic regions with 50% GC content or more tend to have high **Gene Density**. The overall CG content of the human genome is 41%, however some regions differ severely from this average. 

**CpG Islands** are regions with high concentraions of CpG (C followed by G on the same strand). CpG should occur at 4.41% frequency in the genome, however it actually occurs at less than 1% frequency. CpG Islands are believed to be associated with promoters and transcription start sites. The CpG Track is available via UCSC. 

Approximately 10% of the human genome consists of **Repeats**. Repeat DNA likely plays a role in eukaryotic life, however the specific nature is unclear. The broad categories of repeats are _Interspersed repeats_: long-terminal repeat (LTR)-containing long interspersed elements (LINEs) and short elements (SINEs). These are transposon-derived repeats, include Alu repeats, and can be visualized via the RepeatMasker track at UCSC; _Pseudogenes_: derived from genes, but no longer functional. Can be visualized on the pseudogene track at UCSC; _Simple Repeats_: short repetitive sequences or low complexity regions, such as (A)10, a string of 10 As, or (CG)20, CG repeated 20 times; _Segmental Duplications_: large duplications, usually a kilobase or more, which can occur on the same or a different chromosome from the original; and _Tandem repeats_: associated with telomeres, centromeres, and rDNA.

**Aneuploidy** is the presence of an abnormal number of chromosomes in a cell, and is usually caused by nondisjunction in meiosis. It is common for two closely related species to have one region of a chromosome inverted. **Inversions** can also occur within populations, and are sometimes associated with disease. **Synteny Maps** are designed to map related regions of genomes, and show related regions between species on different chromosomes. Fusion or splitting of chromosomes often occur in speciation. 

**Sequence tagged sites** are short regions of a very unique DNA sequence. They are suggested locations for a PCR primer, as there shouldn't be a similar sequence elsewhere in the genome. Ideally these sites shouldn't have any SNPs, and every individual in the population should have that sequence. An STS also found in a different species can be useful for cross-genome comparisons.

### Noncoding RNAs and Functional RNAs
Noncoding RNAs (ncRNA) are any RNA not translated into a protein, and include tRNA, rRNA, lncRNA, small nucleolar RNAs(snoRNA), small nuclear RNAs(snRNA), microRNAs(miRNA), short interfering RNAs(siRNA), and guide RNAs(gRNA). The [Rfam](http://rfam.xfam.org/) database is a repository for ncRNA families. **Functional RNA** (fRNA) is a broader class than ncRNA, and includes functional secondary structures in mRNA, riboswitches and the SECIS element. [PPfold](https://pubmed.ncbi.nlm.nih.gov/22877864/) is an algorithm for RNA secondary structure prediction.

There exist many algorithms and databases for miRNA and their targets. The [miRanda](http://cbio.mskcc.org/miRNA2003/miranda.html) algorithm is specialized to find miRNA and mRNAs that are miRNA targets. [PicTar](https://pictar.mdc-berlin.de/) and [DIANA-TarBase v.8](http://carolina.imis.athena-innovation.gr/diana_tools/web/index.php?r=tarbasev8%2Findex) are other miRNA-target algorithms. miRNA databases include [TargetScan](http://www.targetscan.org/), [miRNEST 2.0](http://rhesus.amu.edu.pl/mirnest/copy/) holds plant and animal miRNAs, [PolymiRTS](https://compbio.uthsc.edu/miRSNP/) holds SNPs in miRNA target sites, [miRDB](http://mirdb.org/), and [miRBase](http://www.mirbase.org/), a repository for known miRNA sequences. [NONCODE](http://www.noncode.org/) is a database for lncRNA transcripts from 16 species. 

![miRNA prediction](/files/TargetScan.png)

miRNA prediction from TargetScan for human NOTCH1 gene

### Conserved Noncoding Elements and Ultraconserved Elements
Ultraconserved Elements are highly conserved regions of organismal genomes shared among evolutionary distant taxa. In vertebrates, UCEs are more constrained than exons, and UCEs are rarely deceted outside of chordates. 

Some Conserved Noncoding Element databases include [ANCORA](http://ancora.genereg.net/), a browser for 11 species with conservation tracks, [cneViewer](http://bioinformatics.bc.edu/chuanglab/cneViewer/) displays conserved regions between human and zebrafish, [UCNEBase](https://ccg.epfl.ch//UCNEbase/) is very comprehensive and catalogs Ultraconserved Noncodng Elements across 18 species, and [CEGA](https://cega.ezlab.org/).

![CNE_UCSC](/files/CNE_UCSC.png)
human CNE ID 34477 viewed on UCSC with the conservation track displayed
