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

- [ ] `which shovill`
- [ ] `ls shovill`
- [ ] `shovill --what`
- [ ] `ls -l shovill`
- [ ] `shovill --help`

### Question 9

What is the command for assembling the genome such that you get an output directory of $SRR.shovill?

- [ ] `shovill --R1 $SRR.reads/*_1.fastq.gz --R2 $SRR.reads/*_2.fastq.gz --cpus 1 > $SRR.shovill `
- [ ] `shovill $SRR.reads/*_1.fastq.gz $SRR.reads/*_2.fastq.gz --outdir $SRR.shovill --cpus 1`
- [ ] `shovill *.fastq.gz --outdir $SRR.shovill --cpus 1`
- [ ] `shovill --R1 $SRR.reads/*_1.fastq.gz --R2 $SRR.reads/*_2.fastq.gz --outdir $SRR.shovill --cpus 1`

### Question 10

What option would you have used to change the underlying assembler to skesa instead of spades?  Use double dashes as needed; use a single space between words.  The answer will start with a double dash and will not start with the word 'shovill.'  The word 'skesa' will appear in the answer too.

`_____`

### Question 11

How would you specify using 4 CPUs in shovill?  This answer also starts with a double dash and contains the number 4.  Separate words with a single space.

`_____`

### Question 12

After your assembly completes, what is your assembly filename?  Specify the filename without the directory. Hint: the filename starts with a "c."  For example, if the assembly were located in ~/my/directory/assembly.fasta, the answer would be "assembly.fasta"

`_____`

## QC the assembly

### Question 13 

How many contigs do you have in your assembly?  Round to the nearest 50.  For example, if you have 249 contigs, the answer is 250.  

`_____`

### Question 14

Which command would be helpful in determining the number of contigs in your assembly?  Each contig is a fasta entry starting with `>`

- [ ] `cd ~`
- [ ] `rm -v`
- [ ] `grep -c`
- [ ] `ls -l`

### Question 15

What is the name of the metric that tells you the contig size, where half the genome size is contained in that contig size or greater?

* median contig size
* grep
* N50
* N90
* average contig size
