# Metagenomics - HMAS

## Background

### Question 1

The targeting approach that we described in HMAS is a form of quasi-metagenomics. From context, how is quasi-metagenomics defined?

- Sequencing 10% of a sample
- Sequencing the RNA of a sample
- Sequencing 10% of the RNA of a sample
- Enrichment of a specific type of DNA in a sample and then sequencing

### Question 2

What is a culture independent diagnostic test (CIDT), and why is this a challenge for PulseNet?

- A CIDT is a rapid test for a pathogen, without having a live sample to send to PulseNet. This actually does not present a challenge.
- A CIDT is a metagenomic sample sent to the local public health lab. This actually does not present a challenge.
- A CIDT is a rapid test for a pathogen, without having a live sample to send to PulseNet. Without a significant number of actual isolates, it is difficult to have a genomic epidemiology program.
- A CIDT is a metagenomic sample sent to the local public health lab. Without a significant number of actual isolates, it is difficult to have a genomic epidemiology program.

## Step Mothur

We will run quasi-metagenomics analysis with Step Mothur.

Download the software using the instructions provided in the README at [https://github.com/ncezid-biome/HMAS-QC-Pipeline2](https://github.com/ncezid-biome/HMAS-QC-Pipeline2):

```bash
git clone https://github.com/ncezid-biome/HMAS-QC-Pipeline2.git 
cd HMAS-QC-Pipeline2
conda env create -n hmas -f bin/hmas.yaml 
```

and then one more step not mentioned in the README:

```bash
git checkout v1.2.1
```

### Question 3

Load the conda environment. Run the test as described in the README and copied below. What is the name of the output folder? Only display the relative path. If the folder is called "out", then the answer will be "out" and not "./out" and not "/absolute/path/to/out". Do not include a leading slash: for example, the answer will not be "out/".

```bash
nextflow run hmas2.nf -profile test
```

`_____`

### Question 4

Open the MultiQC report embedded in the output HTML file. Look at the reads in `NC-HEC_S8_L001_R1_001`.

What is the average read length? Do not include units. For example, if the average read length is 100 base pairs, then the answer is "100".

What is the median read length? Again, do not include units.

`_____`  
`_____`

### Question 5

Keep the MultiQC report open. Go down to the HMAS run report. Look at sample `2012K_0845`.

What is the mean read depth?

How many successful loci were found? Do not include the ratio. If you're looking at a ratio, just include the numerator.

`_____`  
`_____`

### Question 6

Look at the sample labeled "Water1". This is a negative control. Why do we want to run a negative control?

- It's what plants crave. It's got electrolytes.
- The experiment needs water and so this explicitly shows that we added that component to the master mix.
- This gives an idea of the number of primers and loci identified just by the background material alone, without directly adding samples.
- This gives an idea of the number of primers and loci identified, compared to the situation when we add a sample for analysis.

### Question 7

For the purposes of this quiz, we will pretend that sample `2010K_1649` is a positive control. What does a positive control mean in the context of this report?

- This is the sample that does not contain a strain. Other samples that have a strain should also produce similar counts.
- This is the sample that does not contain a strain. Nothing else can come close to this.
- This is the sample that definitely has a strain that should produce a strong result. Other samples that have a strain should also produce similar counts.
- This is the sample that definitely has a strain that should produce a strong result. Nothing else can come close to this.

### Question 8

Based on the positive control and the negative control, how did sample `2010K_0968` fare? What about sample `2013K-1153`? If a value shows "n/a", then interpret it as though there is a zero count.

- `2010K_0968`: The number of successful primer pairs is much closer to the positive control than the negative control and so it passed the quality check.
  `2013K-1153`: The number of successful primer pairs is much close to the negative control and so it passed the quality check.
- `2010K_0968`: The number of successful primer pairs is much closer to the positive control than the negative control and so it failed the quality check.
  `2013K-1153`: The number of successful primer pairs is much close to the negative control and so it passed the quality check.
- `2010K_0968`: The number of successful primer pairs is much closer to the positive control than the negative control and so it failed the quality check.
  `2013K-1153`: The number of successful primer pairs is much close to the negative control and so it failed the quality check.
- `2010K_0968`: The number of successful primer pairs is much closer to the positive control than the negative control and so it passed the quality check.
  `2013K-1153`: The number of successful primer pairs is much close to the negative control and so it failed the quality check.
