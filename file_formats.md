## File Formats

### SAM
_contains information about how sequences align to a reference_

A [SAM](https://samtools.github.io/hts-specs/SAMv1.pdf) file is produced by an alignment program like HISAT or BWA. SAM files are tab delimited and include header lines which begin with the @ symbol. Each line represents a single alignment event and contains 11 mandatory fields. 
![SAM image](/files/SAM.png)
### CIGAR String
_variations between sequence and reference genome in SAM files are encoded using CIGAR strings_

[CIGAR](https://www.drive5.com/usearch/manual/cigar.html) stands for Concise Idiosyncratic Gapped Alignment Report. It is a compressed representation of an alignment that is used in the SAM file format. The symbols used are: M = alignment match, I = insertion to the reference, and D = deletion from the reference.

### BAM
_the binary equivalent of a SAM file_

BAM files are compressed SAM files. They are most useful when sorted, as this allows for quick retrieval or display. A BAM file must be indexed (an associated .bai file) to be visualized. 

### BED
_designed to store information on genomic intervals_

A simple (minimum) BED file has 3 columns - chromosome name, start position of entity, end position of entity - separated by tabs. There are longer BED formats (BED6, BED12). See [BedTools documentation](https://bedtools.readthedocs.io/en/latest/content/general-usage.html) for more information.
![BED image](/files/0vs1based.png)
### WIG
_designed to store continuous information at each genomic location_

**BigWig** is a compressed version of a WIG file. See [WIG](http://genome.ucsc.edu/goldenpath/help/wiggle.html) and [BigWig](https://genome.ucsc.edu/goldenpath/help/bigWig.html) documentation for more information.

### FASTA
_a format for specifying or representing DNA sequences_

[FASTA](https://blast.ncbi.nlm.nih.gov/Blast.cgi?CMD=Web&PAGE_TYPE=BlastDocs&DOC_TYPE=BlastHelp) file format is a DNA sequence format for specifying or representing DNA sequences. A FASTA file begins the header with the  > symbol. FASTA is often used to store a reference genome, or any sequence.

### FASTQ
_an extention of the FASTA format with sequence quality_

[FASTQ](https://support.illumina.com/bulletins/2016/04/fastq-files-explained.html) is a format for representing DNA sequences with sequence quality, usually represented in ASCII characters which correspond to a phred score. A FASTQ file contains 4 lines: (1) header line starting with @, (2) DNA sequence line, (3) another header line starting with +, and (4) the quality line. FASTQ is typically used to store the sequence fragments before mapping.

### VCF
