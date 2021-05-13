## File Formats

### SAM
_contains information about how sequences align to a reference_

A [SAM](https://samtools.github.io/hts-specs/SAMv1.pdf) file is produced by an alignment program like HISAT or BWA. SAM files are tab delimited and include header lines which begin with the @ symbol. Each line represents a single alignment event and contains 11 mandatory fields (see below).

![SAM format](/files/SAM.png) | Each line represents a single alignment event and contains 11 mandatory fields. 
<img src="/files/SAM.png" width="200" height="150">
### CIGAR String

### BAM
_a binary equivalent of a SAM file_



### BED
_designed to store information on genomic intervals_

A simple (minimum) BED file has 3 columns - chromosome name, start position of entity, end position of entity - separated by tabs. There are longer BED formats (BED6, BED12). See [BedTools documentation](https://bedtools.readthedocs.io/en/latest/content/general-usage.html) for more information.

0-based versus 1-based
![0-based versus 1-based](/files/0vs1based.png)

### WIG
_designed to store continuous information at each genomic location_

**BigWig** is a compressed version of a WIG file. See [WIG](http://genome.ucsc.edu/goldenpath/help/wiggle.html) and [BigWig](https://genome.ucsc.edu/goldenpath/help/bigWig.html) documentation for more information.

### FASTA
