## File Formats

### BED
designed to store information on _genomic intervals_

0-based versus 1-based

![link image here](/files/0vs1based.png)

simple (minimum) file: 3 columns 
- chromosome name, start position of entity, end position of entity
- columns are separated by tabs

there are longer BED formats (BED6, BED12)
- [BedTools documentation](https://bedtools.readthedocs.io/en/latest/content/general-usage.html)

### WIG
designed to store _continuous_ information at _each genomic location_

**BigWig**: compressed version of a WIG file

[WIG](http://genome.ucsc.edu/goldenpath/help/wiggle.html) and [BigWig](https://genome.ucsc.edu/goldenpath/help/bigWig.html) documentation

### FASTA
