# Installation of software

## BLAST

### Question 1

What does BLAST stand for?

- [ ] Better Local Alignment Search Technique
- [ ] Bacteria's Lively Attempt at Sequence Sorting
- [ ] Basic Local Alignment Search Tool
- [ ] Basic Local Alignment Search Technique
- [ ] Biosequence Local Alignment Search Tool

### Question 2

Match the flavor of BLAST with what it does

1. tblastx
2. blastp
3. tblastn
4. blastn
5. blastx

- Translates a nucleotide query sequence in all six reading frames and compares it against a nucleotide sequence database also translated in all six reading frames.
- Compares a protein query sequence against a protein sequence database.
- Compares a protein query sequence against a nucleotide sequence database translated in all six reading frames.
- Compares a nucleotide query sequence against a nucleotide sequence database.
- Translates a nucleotide query sequence in all six reading frames and compares it against a protein sequence database.

### Question 3

Who developed and hosts the BLAST software?

* DDBJ
* NCBI
* EBI
* GSU

### Question 4

Before running BLAST, what is one thing that you have to do?

* Format the query
* Run the help menu
* Transform all nucleotides to uppercase
* Format the database

### Question 5

What is Conda?

* A pipelining tool
* A method of comparing a query against a database
* A package manager for installing software
* A website

### Question 6

How would you make a new env in Conda, called myenv, to install both BLAST and clustalo?

* `conda create -y myenv blast clustalo`
* `conda create -n myenv blast clustalo`
* `conda install -n myenv blast clustalo`
* `conda install -y myenv blast clustalo`

### Question 7

You want to install some new software called samtools to a new environment, myenv. How do you find out what the conda software is called before you even install it?
	
* `conda search samtools`
* `conda find -n myenv samtools`
* `conda search -n myenv samtools`
* `conda find samtools`

### Question 8

How would you run the blast help menu after logging into a fresh terminal, assuming that blast is installed in an environment called myenv?

* `mamba activate myenv`  
`blast -help`
* `conda load myenv`  
`blast -help`
* `mamba load myenv`  
`blast -help`
* `conda activate myenv`  
`blast -help`

### Question 9

After running the blast help menu on the previous question, how do you switch to the clustal environment?

* `conda unload`  
`conda load clustal`
* `conda deactivate blast`  
`conda activate clustal`
* `conda unload blast`  
`conda load clustal`
* `conda deactivate `  
`conda activate clustal`
