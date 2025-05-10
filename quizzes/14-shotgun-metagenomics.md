# Metagenomics - Shotgun Metagenomics

## Download the Data

The following BioSamples were collected from a real wastewater facility in Georgia on the following dates:

- SRR22043554 - 2022-10-10
- SRR22128800 - 2022-10-17
- SRR22292200 - 2022-10-31

Download these raw reads and compress them using `gzip`.

### Question 1

What are the BioSample accessions for these SRA run accessions? Use the NCBI interface to help find your answer. They start with "SAMN." To help with automated grading, please sort the BioSample accessions numerically. For example, "SAMN1234" comes before "SAMN1235." Your answers should include "SAMN" and not just the numerical part of the answer.

`_____`

### Question 2

What is the command to compress `file.fastq` into `file.fastq.gz` using the gzip algorithm?

- `gzip file.fastq`
- `gzip file.fastq.gz`
- `gzip file.fastq > file.fastq.gz`
- `gzip file.fastq file.fastq.gz`

### Question 3

Each of these three SRA runs are paired end. How many fastq files did you download in total from these three accessions?

`_____`

## The Database

Make a new directory `k2_viral_20220908` and move into that directory using `cd`.

Download the database from [https://benlangmead.github.io/aws-indexes/k2](https://benlangmead.github.io/aws-indexes/k2). Choose the viral database from 9/8/2022 whose archive size is 0.4GB to download. Uncompress the file using the command `tar zxvf k2_viral_20220908.tar.gz`. Delete the tar.gz file after it has been uncompressed. Then, go up one level with `cd ..`.

If all goes well, you should have the following files in your directory like so:

```bash
$ ls k2_viral_20220908/
database100mers.kmer_distrib  database300mers.kmer_distrib  inspect.txt
database150mers.kmer_distrib  database50mers.kmer_distrib   opts.k2d
database200mers.kmer_distrib  database75mers.kmer_distrib   seqid2taxid.map
database250mers.kmer_distrib  hash.k2d                      taxo.k2d
```

### Question 4

What was the command to delete the tar.gz file if it were named `$FILE`?

- `tar zxvf $FILE`
- `rm $FILE`
- `delete $FILE`
- `cd ..`

### Question 5

Kraken2 is kmer-based. Let's say one of the genomes in a database is very simple, just 8 nucleotides long:

```
AACCGGTT
```

What are all the kmers of this genome if k is 7? In other words, what are all the 7-mers for this genome? There are two answers. To help with automated grading, the first answer contains 'AA' and the second answer contains 'TT.'

`_____`  
`_____`

### Question 6

What was the command to download the database? Pretend that you set the variable `URL` like so:

```bash
URL=https://genome-idx.s3.amazonaws.com/kraken/k2_viral_20240904.tar.gz
```

- `wget $URL`
- `wdownload $URL`
- `download $URL`
- `get $URL`

## NCBI

For this section, use the NCBI interface on each SRA run accession.

### Question 7

What percent of the reads have been identified for SRR22292200?

- `31.21`
- `57.11`
- `11.37`
- `42.89`

### Question 8

What is the dominant top level taxon for SRR22292200?

- `Cellular organisms`
- `Lentisphaerae`
- `Viruses`
- `Chlamydiae`

### Question 9

Of the cellular organisms and the viral organisms, what are the top level organisms found?

- `Identified reads and unidentified reads`
- `Listeria and SARS-CoV-2`
- `Archaea and Lentisphaerae`
- `Archaea and Riboviria`
- `Bacteria and Lentisphaerae`
- `Bacteria and Riboviria`

### Question 10

When viewing SRR22292200, what percentage of reads are Severe acute respiratory syndrome coronavirus 2 (SARS-CoV-2)?

- `<0.01`
- `11.17`
- `11.26`
- `6.55`
- `31.53`
- `4.46`

### Question 11

What are the percent reads of SARS-CoV-2 going from October 17 to October 31 at this location? Does this show an increase or decrease in the percentage of SARS-CoV-2 reads over this short period of time?

Reminder:

```text
SRR22043554 - 2022-10-10
SRR22128800 - 2022-10-17
SRR22292200 - 2022-10-31
```

- 2.00 to 6.55; increase
- 6.55 to 2.00; decrease
- 4.46 to 1.18; decrease
- 1.18 to 4.46; increase

## Kraken2

Run Kraken2 against the viral database that you downloaded.

### Question 12

What is the command to analyze the reads for accession SRR22128800 against the viral database you downloaded, using Kraken2? Use `$DB` for the path to the database folder.

- `kraken --db $DB --threads 2 --report SRR22128800.kraken.report --gzip-compressed SRR22128800_1.fastq.gz SRR22128800_2.fastq.gz`
- `kraken2 --db $DB --threads 2 --report SRR22128800.kraken.report --gzip-compressed SRR22128800_1.fastq.gz SRR22128800_2.fastq.gz`
- `kraken -db $DB -threads 2 -report SRR22128800.kraken.report -gzip-compressed SRR22128800_1.fastq.gz SRR22128800_2.fastq.gz`
- `kraken2 -db $DB -threads 2 -report SRR22128800.kraken.report -gzip-compressed SRR22128800_1.fastq.gz SRR22128800_2.fastq.gz`

### Question 13

What are the percent reads of SARS-CoV-2 going from October 17 to October 31 at this location? Does this show an increase or decrease in the percentage of SARS-CoV-2 reads over this short period of time?

Reminder:

```text
SRR22043554 - 2022-10-10
SRR22128800 - 2022-10-17
SRR22292200 - 2022-10-31
```

- 2.47 to 7.76; increase
- 7.76 to 2.47; decrease
- 1 to 0; decrease
- 0 to 1; increase

### Question 14

What are the percent reads of SARS-CoV-2 going from October 10 to October 17 at this location? Does this show an increase or decrease in the percentage of SARS-CoV-2 reads over this short period of time?

Reminder:

```text
SRR22043554 - 2022-10-10
SRR22128800 - 2022-10-17
SRR22292200 - 2022-10-31
```

- 2.47 to 0.58; decrease
- 0.58 to 2.47; increase
- 0 to 1; increase
- 1 to 0; decrease

## Visualization with Krona

Download Dr. Katz's script and run it on the report for accession SRR22292200.

Reminder, this was the text from the slides:

```bash
wget https://raw.githubusercontent.com/lskatz/lskScripts/master/scripts/kraken2-translate.pl
perl kraken2-translate.pl kraken2.report > kraken2.tsv
```

### Question 15

Show an image of your Krona plot for SRR22292200. Do not upload the HTML file. This is a homework question to test your skills in visualization and therefore automated grading is not possible here. Do your best to convey the percentage of unclassified reads vs viruses. Pretend you are showing this to your professor or boss. This question is worth 5 points.

`_____`
