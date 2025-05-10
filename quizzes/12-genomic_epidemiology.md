# Genomic Epidemiology

## NCBI Pathogens

Go to [https://peerj.com/articles/3893](https://peerj.com/articles/3893) and navigate to supplementary table 1. There is a column `genBankAssembly` which has assembly identifiers that start with "GCA". In this homework, remove the ".1" from the assembly accession such that they appear like this:

```
GCA_001257675
GCA_001257525
GCA_001257505
GCA_001257515
GCA_001257635
GCA_001257595
GCA_001257585
GCA_001047715
GCA_001257575
GCA_001257495
```

Remove one specific sample `GCA_001257635.1` so that you are down to just nine.

```
GCA_001257675
GCA_001257525
GCA_001257505
GCA_001257515
GCA_001257595
GCA_001257585
GCA_001047715
GCA_001257575
GCA_001257495
```

We will focus on the nine samples that have assembly accessions associated with them for this entire quiz. Ignore samples without an assembly accession.

Search the NCBI Pathogen Detection page at [https://ncbi.nlm.nih.gov/pathogens](https://ncbi.nlm.nih.gov/pathogens) using one of the strain names. One example strain name is `CFSAN002349`.

### Question 1

After searching NCBI Pathogens, you will get at least one row of information about your strain. What is the SNP cluster accession? It starts with `PDS` and ends with a decimal. For example, this would be a validly formatted SNP cluster accession: `PDS001234.87`.

Second blank: what is the genus of the strain?

Third blank: what is the species of the strain?

`_____`  
`_____`  
`_____`

### Question 2

Click into the SNP cluster accession. It should be the same, no matter which of the nine you searched with. This was a real stone fruit recall that had a bacterial pathogen. What is one five-letter word for a fruit that you see in the metadata for some of these isolates? Hint: not nectarine; starts with a "p".


`_____`

### Question 3

Frequently, PulseNet assigns outbreak codes to events such as the stone fruit recall event. This particular outbreak started with "1408" to indicate that the year was 2014 and the month was August. Using what you can see in the NCBI Pathogens tree or what you can see in supplementary figure 1, what is the outbreak code?

`_____`

### Question 4

An event happened three months later, genetically related to the stone fruit recall. The outbreak code starts with "1411". What is the related but distinct outbreak starting with "1411"?

`_____`

## Data Download and MLST

Download the genome assemblies for these 9 accessions. One command looks like this:

```bash
esearch -db assembly -query GCA_001257675 | elink -target nuccore | efilter -source refseq | efetch -format fasta > GCA_001257675.fasta
```

Remember to remove the ".1" from the accessions to stay consistent with the format of the quiz (and to help keep this quiz from going out of date!).

### Question 5

After downloading the nine genome assemblies, what is the average file size of the fasta files? Find this information with `ls -lh`. Use a suffix "M" to help with automated grading. For example, if the file size is 1.1 megabytes, the answer is `1.1M`.

`_____`

### Question 6

Run 7-gene MLST on the assemblies. What is the name of the scheme? This starts with "listeria".

Second blank: what is the sequence type (ST)? This is an integer.

`_____`  
`_____`

### Question 7

If you needed more help running MLST, what command would you give?

- `mamba help mlst`
- `which mlst`
- `conda help mlst`
- `mlst --help`

## Mashtree

Run mashtree on all 9 assemblies like so:

```bash
mashtree *.fasta > mashtree.nwk
```

### Question 8

If you needed more help running mashtree, what command would you run?

- `mashtree --help`
- `mamba help mashtree`
- `conda help mashtree`
- `which mashtree`

### Question 9

What is the command for showing the contents of `mashtree.nwk`?

- `awk ">" mashtree.nwk`
- `dog mashtree.nwk`
- `grep ">" mashtree.nwk`
- `cat mashtree.nwk`

### Question 10

Copy and paste the results of mashtree into the text box here. It should look like a newick format with parentheses indicating groupings. E.g., `(GCA_001047715:0.00001,((( ...`

`_____`

### Question 11

What is one example program that you could visualize the mashtree newick file in? You would want to get a screenshot of a visualization and not just the text of the tree.

- `MEGA`
- `cat`
- `less`
- `firefox`
- `figtree`

### Question 12

Attach an image of your tree from mashtree.

`_____`
