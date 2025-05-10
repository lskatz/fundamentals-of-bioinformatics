# Final Exam

## Data Download

Cholera is caused by the bacterial pathogen *Vibrio cholerae* and was last seen clinically in Haiti in 2019. Between 2019 and 2022, it was not seen clinically. Before that, there was an outbreak in 2010, and before that, it had not been seen in Haiti for at least a century.

In January 2010, Haiti experienced a large earthquake that, among other disastrous effects, damaged water infrastructure. Thankfully, many countries invested in helping Haiti rebuild. Across the world, in August 2010, an outbreak of cholera occurred in Nepal. Then, a possibly unrelated cholera outbreak occurred in Haiti in October 2010 where Nepalese peacekeepers were stationed.

Some people speculated that the outbreak was introduced by Nepalese peacekeepers; others speculated that the outbreak came from the surrounding environment. I would like to know whether you see more genetic similarities between the clinical *V. cholerae* in Haiti and the surrounding waters, or more genetic similarities with the Nepalese outbreak. 

For more, but optional, information you can read Frerichs et al 2012: [https://www.sciencedirect.com/science/article/pii/S1198743X14641343](https://www.sciencedirect.com/science/article/pii/S1198743X14641343)

Some of you might also be aware of the incredibly unfortunate reemergence of cholera in Haiti in 2022 but again this is optional, and not a part of this exam. For more optional information see here: [https://www.nejm.org/doi/full/10.1056/NEJMc2213908](https://www.nejm.org/doi/full/10.1056/NEJMc2213908)

Note the results you find here are not the entirety of what we would use to make conclusions on a real-world outbreak; there are many more facts and lines of evidence to consider. This is just one aspect of many and one subset of data of many from a real investigation.

To begin, take the time to download these data which include the strain name and either an assembly accession or an SRA accession. Downloading these data will take a while.

- 2010EL-1786 - GCA_009665515.2 - this is the completed reference genome for the 2010 Haiti outbreak
- Five more clinical 2010 Haiti cholera outbreak genomes:
  - 2010EL-1801 - SRR772254 
  - 2010EL-2026 - SRR772256 
  - 2011EL-1300 - SRR772892 
  - HC-17A1 - SRR346409 
  - HC-77A1 - SRR346410 
- Two clinical genomes from the 2010 Nepalese outbreak:
  - vc-14 - SRR308715 
  - vc-25 - SRR308726
- Two environmental genomes from Haiti in 2010, from the surrounding waters:
  - HE39 - SRR135547 
  - HE46 - SRR346405  

### Question 1

What is the command to download accession `SRR191384` into fastq files into the `reads` directory?

- `wget SRR191384 --threads 1`
- `fasterq-dump SRR191384 --threads 1`
- `wget SRR191384 --threads 1 --outdir reads --split-files --skip-technical`
- `fasterq-dump SRR191384 --threads 1 --outdir reads --split-files --skip-technical`

### Question 2

What is the command to download the assembly accession `GCA_009665515.2` into a fasta file `2010EL-1786.fasta`?

- `fasterq-dump GCA_009665515.2 --threads 1 > 2010EL-1786.fasta`
- `esearch -db assembly -query GCA_009665515.2 | elink -target nuccore | efetch -format fasta > 2010EL-1786.fasta`
- `esearch -db assembly -query 2010EL-1786.fasta | elink -target nuccore | efetch -format fasta > GCA_009665515.2.fasta`
- `esearch -db nuccore -query GCA_009665515.2 | elink -target assembly | efetch -format fasta > 2010EL-1786.fasta`
- `esearch -db nuccore -query 2010EL-1786 | elink -target assembly | efetch -format fasta > GCA_009665515.2.fasta`
- `fasterq-dump 2010EL-1786 --threads 1 > GCA_009665515.2.fasta`

### Question 3

Three of the genomes that you downloaded are single end reads. That is to say, they were not sequenced as paired end reads with two fastq files each. Which accessions are single end reads and only have one fastq file each? 

To help with automated grading, enter the accessions in numerical order. Include "SRR" in the name. For example, SRR123 would come before SRR124. 

`_____`  
`_____`  
`_____`

### Question 4

Compress all fastq files that you downloaded with gzip. What is the command to compress all fastq files with gzip?

- `gzip -v *.fastq`
- `zip -v *.fastq.gz`
- `gzip -v *.fastq.gz`
- `zip -v *.fastq`

### Question 5

Why do we compress fastq files with gzip?

- The teacher told me to.
- It reduces the file size and saves disk space.
- It converts them into the right format, fastq.gz, for genome assembly.
- Gzip removes unnecessary quality scores.

### Question 6

Fastq format is a four-line-per-entry format. What is the first character of any fastq file?

Second question: what is the first character of any fasta file?

`_____`  
`_____`

### Question 7

2010EL-1786 is considered the representative genome of *V. cholerae* for the Haiti cholera outbreak. Therefore, it was sequenced multiple times with multiple sequencing platforms. What are two examples of 3rd generation sequencing?

- Nanopore
- Illumina
- PacBio
- 454
- Sanger

### Question 8

What does assembling a genome do?

- Assigns a taxonomic profile
- It completes the Smith-Waterman algorithm
- Calls together The Hulk, Thor, Black Widow, Captain America, Iron Man, and Hawkeye
- Compiles all the raw reads into a set of consensus sequences representing the genome
- Determines the multilocus sequence typing profile

### Question 9

Which is one way to install SPAdes?

- `spades install $HOME/bin/spades`
- `spades --help`
- `conda create -n spades`
- `spades create from conda`
- `conda create -n spades spades`

### Question 10

Assemble all seven genomes. This takes hours to finish. Would you like a few free points because of all the frustration and time this takes?

- Yes
- This did not take me a long time (this is an incorrect answer).

### Question 11

What is a valid SPAdes command to assemble `SRR135547`, a genome with paired end reads into a folder `SRR135547.spades`? If you are unsure, you can run `spades.py --help`.

- `spades.py --threads 4 -1 reads/SRR135547_1.fastq.gz -2 reads/SRR135547_2.fastq.gz -o SRR135547.spades --isolate`
- `spades.py --threads 4 -1 reads/SRR135547_1.fasta -2 reads/SRR135547_2.fasta -o SRR135547.spades --isolate`
- `spades.py --threads 4 -s reads/SRR135547.fasta -o SRR135547.spades --isolate`
- `spades.py --threads 4 -s reads/SRR135547.fastq.gz -o SRR135547.spades --isolate`

### Question 12

What is a valid SPAdes command to assemble `SRR772254`, a genome with single end reads into a folder `SRR772254.spades`? If you are unsure, you can run `spades.py --help`.

- `spades.py --threads 4 -1 reads/SRR772254_1.fasta -2 reads/SRR772254_2.fasta -o SRR772254.spades --isolate`
- `spades.py --threads 4 -1 reads/SRR772254_1.fastq.gz -2 reads/SRR772254_2.fastq.gz -o SRR772254.spades --isolate`
- `spades.py --threads 4 -s reads/SRR772254.fastq.gz -o SRR772254.spades --isolate`
- `spades.py --threads 4 -s reads/SRR772254.fasta -o SRR772254.spades --isolate`

### Question 13

Most of these genome assemblies are a certain file size. What is that file size? Round to the nearest megabyte. For example, if the file sizes of `scaffolds.fasta` are 2.9M, 3.1M, 3.1M, 3.1M, and 8M, then the answer is "3M". Please include only the integer and "M" for help in automatic grading.

`_____`

### Question 14

I would like to know the sequence type (ST) of these isolates. What is the ST?

- The virulence profile of the bacterial pathogen.
- The profile of the isolate when you bring together several loci.
- The resistance susceptibility pattern of the pathogen.
- A locus. Plural: loci.

### Question 15

Install the `mlst` tool with conda and then run it on all the assemblies. These assemblies are under each `.spades` directory in the file `scaffolds.fasta` (`*.spades/scaffolds.fasta`).

What is the command to run `mlst` on all `scaffold.fasta` files at once while specifying the `vcholerae` scheme? Run `mlst --help` for additional help.

- `mlst *.spades/scaffolds.fasta --scheme vcholerae`
- `st *.spades/scaffolds.fasta --scheme vcholerae`
- `st *.spades/scaffolds.fasta`
- `mlst *.spades/scaffolds.fasta`

### Question 16

What is the sequence type for most of the genome assemblies? It is a positive integer.

`_____`

### Question 17

Why do we care about MLST?

- This is a prerequisite step for de Bruijn assembly.
- It helps us with everyday language: communicating which subpopulation of a species is doing what. For example, if one population is growing or shrinking.
- It looks flashy and gives us another talking point on slides.
- It gives us an idea of whether any two isolates are related.
- It allows us to completely describe a genome. Because it is totally redundant with the information in the genome assembly, we can throw it out and just talk about the MLST results.

## Metagenomics

### Question 18

Download the 8G minikraken database as listed at https://benlangmead.github.io/aws-indexes/k2. It is named 'Standard-8'.

Uncompress it with `tar zxvf filename`.

These were my commands in 2022, for example:

```
mkdir kraken8GB
cd kraken8GB
wget https://genome-idx.s3.amazonaws.com/kraken/k2_standard_08gb_20220926.tar.gz
tar zxvf k2_standard_08gb_20220926.tar.gz
cd ..
```

What is one filename that gets decompressed from this tgz file?

- `hash.k2d.tar.gz`
- `scaffolds.fasta`
- `scaffolds.fastq.gz`
- `hash.k2d`

### Question 19

After having installed kraken2, what is a valid command to run it on SRR135547 and get a report into SRR135547.kraken.report? We assume the database was decompressed into a directory `$DB`.

- `kraken2 --db $DB --threads 4 --report SRR135547.kraken.report --gzip-compressed reads/SRR135547_1.fastq.gz reads/SRR135547_2.fastq.gz`
- `kraken2 reads/SRR135547_1.fastq.gz reads/SRR135547_2.fastq.gz > SRR135547.kraken.report`
- `kraken2 --db $DB --threads 4 --gzip-compressed reads/SRR135547_1.fastq.gz reads/SRR135547_2.fastq.gz > SRR135547.kraken.report`
- `kraken2 reads/SRR135547_1.fastq.gz reads/SRR135547_2.fastq.gz`

#### Question 20 (1 point)

The algorithm behind Kraken2 is based on kmer analysis. What does the k in kmer mean?

- The length of the DNA sequence slices, measured in number of nucleotides
- The average read length, measured in number of nucleotides
- Kraken2
- Kraken

### Question 21

If k is 7 and the DNA sequence is the following, what are the two kmers you would see? The first answer will have AA in it and the second answer will have GG.

**DNA Sequence:** AACCTTGG

- Blank #1: `_____`
- Blank #2: `_____`

### Question 22

All of these genomes are supposed to be *Vibrio cholerae*. But Kraken2 will give us a nuanced answer. Which two genomes have contamination greater than 5% at the genus level? Use the SRR accession in numerical order for your answer. Include the "SRR" in the answer.

You can get these answers directly using the `*.kraken.report` files. However, you can visually inspect these results using the following tutorial: https://telatin.github.io/microbiome-bioinformatics/Kraken-to-Krona/

In short, to create the visualization, run `ktImportTaxonomy -t 5 -m 3 -o multi-krona.html *.kraken.report`. Then, load the file `multi-krona.html` into your web browser.

`_____`  
`_____`

## Genomic Epidemiology

### Question 23

We will see how the genomes cluster by running Mashtree. What does Mashtree do?

- Runs MLST to cluster genomes
- Creates a phylogeny to cluster genomes
- Creates a dendrogram to cluster genomes
- Runs assembly to cluster genomes

### Question 24

What is a valid mashtree command for us to run on our assembly and reads and to get a tree into `mashtree.dnd`? Usually you only run Mashtree on R1 and not R2 if paired end.

- `mashtree 2010EL-1786.fasta --indir reads > mashtree.dnd`
- `mashtree 2010EL-1786.fasta --R1 *_1.fastq.gz --s SRR772254.fastq.gz SRR772256.fastq.gz SRR772892.fastq.gz --numcpus 4 > mashtree.dnd`
- `mashtree 2010EL-1786.fasta -c config > mashtree.dnd`
- `mashtree 2010EL-1786.fasta *_1.fastq.gz SRR772254.fastq.gz SRR772256.fastq.gz SRR772892.fastq.gz --numcpus 4 > mashtree.dnd`

### Question 25

Name a visualization program we have discussed, that would help you see the mashtree output, a newick file.

- MEGA
- Firefox
- IGV
- Krona

### Question 26

Which genome clusters more closely with 2010EL-1786?

- K12 (*E. coli*)
- HE39 (Environmental genome)
- VC-14 (Nepalese outbreak)

### Question 27

Which genome has the same ST as 2010EL-1786?

- K12
- HE39
- VC-14
