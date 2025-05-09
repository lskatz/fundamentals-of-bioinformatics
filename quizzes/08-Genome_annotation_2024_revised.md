# Annotation

## Background

### Question 1

What is the causative agent of anthrax?

- _Salmonella enterica_
- _Bacillus subtilis_
- _Bacillus anthracis_
- _Salmonella anthracis_

### Question 2

What is one gene involved in causing anthrax?

- Lethal factor (_lef_)
- Lag factor (_lef_)
- Lethal function (_lef_)
- Lag function (_lef_)

### Question 3

What is one disease that _Salmonella_ is known to cause?

- COVID-19
- Cholera
- Typhoid fever
- Pneumonia

### Question 4

Many genes that contribute to antimicrobial resistance are located in the Salmonella genome on what?

- Origin of replication (_oriC_)
- Telomeres
- Salmonella Pathogenicity Islands (SPIs)
- Salmonella Progress Indicators (SPIs)

### Question 5

When we identify and describe antimicrobial resistance genes in _Salmonella_ using solely bioinformatics, we are describing which of the following?

- Serotype
- Genotype
- Phenotype
- Serovar

### Question 6

When we identify and describe antimicrobial resistance genes in Salmonella using solely bioinformatics, we are predicting which of the following?

- Genotype
- Serotype
- Serovar
- Phenotype

### Question 7

The national surveillance system for antimicrobial resistance tracking in foodborne bacteria is called what?

- NARMS
- INNUENDO
- PulseNet
- GenomeTrakr

## Annotation

Download the genome LT2, a reference genome for Salmonella enterica, and save it to a file `LT2.fasta`. The accession is `NC_003197.2`. This is an example command that allows you to download it on the command line:

```bash
esearch -query NC_003197.2 -db nuccore | efetch -format fasta > LT2.fasta
```

## Annotation

---

### Question 8

How large is the fasta file? Round to the nearest megabyte. For example, if the file size is 1.8 megabytes, answer with "2".

`_____`

### Question 9

Annotate the genome with Bakta, using settings specific to _Salmonella enterica_. What is an example command that annotates the genome with those settings?

- `bakta --genus Salmonella --species enterica --output LT2 LT2.fasta`
- `bakta --sciname Salmonella enterica --output LT2 --input LT2.fasta`
- `bakta --genus Salmonella --species enterica --output LT2 --input LT2.fasta`
- `bakta --sciname Salmonella enterica --output LT2 LT2.fasta`

### Question 10

How many genes were predicted after annotation with Bakta? Round to the nearest 100. For example, if there were 1182 genes, answer with "1200". Hint: you can run `grep` on `"  gene  "`.

`_____`

### Question 11

What are the start and stop positions for the gene `fhlA`, the first gene in SPI-I, in LT2, in your Bakta results? You might see it labeled as "Formate hydrogenlyase".

- `complement(3003709..3005787)`
- `3003696..3005787`
- `complement(3003696..3005787)`
- `3003709..3005787`

### Question 12

What are the start and stop positions for the gene `mutS`, the last gene in SPI-I, in LT2? According to Bakta. (If it doesn't say `mutS`, it might say "DNA mismatch repair protein").

- `3050286..3052853`
- `3050283..3052853`
- `complement(3050286..3052853)`
- `complement(3050283..3052853)`

### Question 13

About how large is the SPI-I region in this genome?

- 4.7Mb
- 41kb
- 45kb
- 39kb
- 49kb

### Question 14

Run StarAMR on the LT2 genome assembly. How many AMR genes in the StarAMR results overlap with SPI-I?

Hint: This is how the slides show the example command:

```bash
staramr search --pointfinder-organism salmonella --pid-threshold 90 --percent-length-overlap-resfinder 50 --output-dir staramr/$SRR asm/SRR2485281/contigs.fa
```

`_____`

### Question 15

Download the Bakta database with a command we have not learned in class: `bakta_db`. Run `bakta_db --help` to get usage. How would you download the database into a database folder `bakta-light.db`?

- `bakta_db download --type light --output bakta-light.db`
- `bakta_db get --type light --outdir bakta-light.db`
- `bakta_db get --type light --outdir bakta-light.db`
- `bakta_db download --type light --output bakta-light.db`

### Question 16

Load the LT2 genome into the IGV program. If you can show a screenshot of IGV with genome annotations loaded, you will get full credit. If annotations are not shown, zoom in until at least some annotations are visible.
