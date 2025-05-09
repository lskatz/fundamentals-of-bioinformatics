# Assembly and prediction

## _Vibrio cholerae_ 2012EL-2176

Search the NCBI SRA database for "vibrio cholerae haiti 2012EL-2176" which is an important Vibrio cholerae isolate containing a plasmid.

### Question 1

Which accessions are Illumina?  Please enter them in numerical order to help with automated grading.  They begin with "SRR."

`______`  
`______`

### Question 2

Which accession is the entire genome and not just the plasmid?  You can find this in the "Design" field under each entry.  Many questions in this homework depend on this knowing this accession.

`_____`

### Question 3

What Illumina instrument was the whole genome sequenced on?

* MiSeq
* PacBio
* HiSeq
* NovaSeq
* MiniSeq

## QC the reads

### Question 4

How would you install fastqc into a new environment called fastqc using mamba?

* `conda --install fastqc`
* `mamba --install -n fastqc fastqc`
* `conda --create fastqc`
* `conda install fastqc`
* `conda create -n fastqc fastqc`

### Question 5

How would you load this environment using conda after it has been installed to the fastqc environment?

* `conda activate fastqc`
* `conda switch fastqc`
* `conda load fastqc`
* `mamba install fastqc`

### Question 6

Using the program fastqc, what is the command you would use to QC the reads? Assume that you have already compressed the files into fastq.gz and they are in the directory $SRR.reads.

* `fastqc /$SRR.reads/*.fastq`
* `fastqc $SRR.reads/*.fastq.gz`
* `fastqc $SRR.reads/*.fastq`
* `fastqc /$SRR.reads/*.fastq.gz`

### Question 7

What conda command would you use to deactivate the fastqc environment after you already activated it?  Use a single space between words in the command to help with automatic grading.  Do not use the mamba command.

`_____`

## Assembly

Assemble the genome of the reads you downloaded.  Some of the answers in this section ask about parameters or flags.  Be sure to use the double dash before each parameter or flag as needed.  For example if there is a parameter and value in the program, be sure to format it like "--parameter value" with a single space in between.

### Question 8

How do you view what other parameters are available in shovill (ie, the usage)?
