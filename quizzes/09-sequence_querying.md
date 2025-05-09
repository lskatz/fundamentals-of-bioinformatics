# Homework - Sequence Querying

## BLAST

Download and assemble the *Salmonella* genome SRR2485281. Use the shovill with spades method. For the purposes of this homework, the assembly will be called "contigs.fa".

### Question 1

Which is a valid command to run shovill on this genome? Assume R1 is in variable `$R1`, R2 is in `$R2`, and the SRR accession is in `$SRR`.

- `shovill --R1 $R1 --R2 $R2 --cpus 2 $SRR.shovill`
- `shovill --R1 $R1 --R2 $R2 --cpus 2 --outdir $SRR.shovill`
- `shovill -1 $R1 -2 $R2 --cpus 2 > $SRR.shovill`
- `shovill -1 $R1 -2 $R2 --cpus 2 --outdir > $SRR.shovill`

### Question 2

To find a nucleotide match against your nucleotide assembly, which flavor of BLAST do you use?

- `blastn`
- `blastp`
- `blastx`
- `tblastx`
- `tblastn`

### Question 3

What is the algorithm behind BLAST?

- Smith-Waterman
- Lander-Waterman
- Needleman-Wunsch
- Min-hash

### Question 4

Before querying your assembly vs a nucleotide database, what do you have to do first?

- Edit the identifiers in the fasta file
- Format the database
- Pray
- Copy both the query and database to the exact same folder

### Question 5

Download the resfinder database from [https://bitbucket.org/genomicepidemiology/resfinder_db.git](https://bitbucket.org/genomicepidemiology/resfinder_db.git).  
For each `.fsa` file, format it as a database. What is the command to format the database assuming that the fasta file is `$i.fsa`?

- `makeblastdb -db $i.fsa -dbtype prot`
- `makeblastdb -in $i.fsa -dbtype nucl`
- `makeblastdb -db $i.fsa -dbtype nucl`
- `makeblastdb -in $i.fsa -dbtype prot`

### Question 6

What is a valid command to query your genome against a database `resfinder.fasta`?

- `blastx -query SRR2485281.shovill/contigs.fa -db resfinder_db/resfinder.fasta`
- `blastx -query SRR2485281.shovill/contigs.fa -in resfinder_db/resfinder.fasta`
- `blastn -query SRR2485281.shovill/contigs.fa -db resfinder_db/resfinder.fasta`
- `blastn -query SRR2485281.shovill/contigs.fa -in resfinder_db/resfinder.fasta`

### Question 7

For the next questions, query your genome against the individual BLAST databases.  

Does your genome have any aminoglycoside genes? If so, what is the closest allele?

- Yes; `blaCTX-M-65_1_EF418608`
- Yes; `aph(4)-Ia_1_V01499`
- Yes; `ant(3'')-Ia_1_X02340`
- No

### Question 8

Does your genome have any tetracycline genes? If so, which allele matches most closely to yours?

- Yes; `tet(A)_4_AJ517790`
- Yes; `tet(A)_6_AF534183`
- Yes; `ole(B)_1_L36601`
- No

### Question 9

Does your genome have any nitroimidazole genes? If so, which one is the closest allele?

- Yes; `aph(4)-Ia_1_V01499`
- Yes; `ant(3'')-Ia_1_X02340`
- Yes; `ole(B)_1_L36601`
- No

## Mash

Download *Salmonella Infantis* genomes using the command:

```bash
datasets download genome taxon --assembly-source refseq --released-after '01/01/2023' --released-before '10/30/2023' --filename 2023.infantis.zip 595
```

Unzip the resulting directory.

Rename the resulting directory to "2023.infantis".

Next, run a similar command to download all of the 2022 Infantis genomes, released anywhere from Jan 1, 2022 to Jan 1, 2023. Rename this directory to "2022.infantis".

### Question 10

What was the command to download all of the 2022 Infantis genomes?

- `datasets --download --genome --taxon --assembly-source refseq --released-after '01/01/2022' --released-before '01/01/2023' --filename --output 2022.infantis.zip --taxid 595`
- `datasets download genome taxon --assembly-source refseq '01/01/2022' '01/01/2023' --filename 2022.infantis.zip 595`
- `datasets download genome taxon --assembly-source refseq --released-after '01/01/2022' --released-before '01/01/2023' --filename 2022.infantis.zip 595`

### Question 11

Make a mash sketch for all 2023 genomes, and a separate one for 2022 genomes. The resulting output filenames should be `2023.infantis.msh` and `2022.infantis.msh`. What is the command to sketch all the 2022 genomes?

- `mash sketch -o 2022.infantis.msh *.*`
- `mash sketch -o 2022.infantis.msh --in 2022.infantis/data/GCF_*/*.fna`
- `mash sketch -o 2022.infantis.msh 2022.infantis/data/GCF_*/*.fna`
- `mash sketch 2022.infantis.msh 2022.infantis/data/GCF_*/*.fna`

### Question 12

Run a mash dist between all 2022 and 2023 Infantis genomes. Which is a valid command to run mash dist?

- `mash dist 2022.infantis.msh 2023.infantis.msh`
- `mash dist 2022.infantis 2023.infantis`
- `mash dist -query 2022.infantis.msh -db 2023.infantis.msh`
- `mash dist -i 2022.infantis.msh -j 2023.infantis.msh`

### Question 13

What are some Linux commands to pipe `mash dist` into, so that you can sort by closest Mash distance and get the top results?

- `order`, `shuf`
- `sort`, `uniq`
- `order`, `head`
- `sort`, `column`
- `sort`, `head`
- `sort`, `shuf`

### Question 14

Between 2022 and 2023 genomes, what are the most similar genomes in terms of mash distance?

- `GCF_022670675.1_ASM2267067v1_genomic.fna (2022), GCF_030435995.1_ASM3043599v1_genomic.fna (2023)`
- `GCF_022670675.1_ASM2267067v1_genomic.fna (2022), GCF_029591745.1_ASM2959174v1_genomic.fna (2023)`
- `GCF_025176845.1_ASM2517684v1_genomic.fna (2022), GCF_030262635.1_ASM3026263v1_genomic.fna (2023)`
- `GCF_025176845.1_ASM2517684v1_genomic.fna (2022), GCF_029103825.1_ASM2910382v1_genomic.fna (2023)`

### Question 15

For the best matched genomes between 2022 and 2023, how many hashes were in common?

- `1/1000`
- `999/1000`
- `1000/1000`
- `0/1000`
