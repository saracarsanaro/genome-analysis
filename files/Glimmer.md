
```
long-orfs -n -t 1.15 hprev_genome.fasta hprev.longorfs
extract -t hprev_genome.fasta hprev.longorfs > hprev.train
build-icm -r hprev.icm < hprev.train
glimmer3 -o50 -g110 -t30 halan.fasta hprev.icm halan_results
extract -t halan.fasta halan_results.predict > halan_results.glimmer
```

![output](/files/Glimmer_predict.png)
