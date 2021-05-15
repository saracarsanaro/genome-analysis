## Analysis from GLIMMER and FGENESB on a Halanaerobium contig

### Inputs
[Halanaerobium](/halan.fasta) contig and [Halanaerobium praevalens](/hprev_genome.fasta) complete circular reference genome

### Glimmer Code
```
long-orfs -n -t 1.15 hprev_genome.fasta hprev.longorfs
extract -t hprev_genome.fasta hprev.longorfs > hprev.train
build-icm -r hprev.icm < hprev.train
glimmer3 -o50 -g110 -t30 halan.fasta hprev.icm halan_results
extract -t halan.fasta halan_results.predict > halan_results.glimmer
```
### Glimmer Output
![output](/Glimmer_predict.png)

### FGENESB Output
![output](/FGENESB.png)
