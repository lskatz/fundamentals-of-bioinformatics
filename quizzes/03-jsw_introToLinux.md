# Intro to Linux

## The game

Questions in this section are related to the game Bashcrawl.  Get the game with these commands:

```bash
wget https://gitlab.com/slackermedia/bashcrawl/-/archive/master/bashcrawl-master.zip

unzip bashcrawl-master.zip
```

### Question 1

What room was the potion originally in?

`_____`

### Question 2

What are the two commands to give yourself hit points (HP)? Assume 15 HP.

- [ ] cd armoury
- [ ] export HP=15
- [ ] cat scroll
- [ ] ./potion

### Question 3

Name two items that you had in your inventory.

- [ ] gloves
- [ ] lute
- [ ] coins
- [ ] Fundamentals of bioinformatics syllabus
- [ ] sword

### Question 4

What is the command to add `goblet` to your inventory?

- [ ] cd entrance
- [ ] find . -name goblet
- [ ] let HP=$HP-5
- [ ] export l=goblet,$l

### Question 5

How did you get into the entrance room (folder)?

- [ ] cd entrance
- [ ] find . -name entrance
- [ ] mkdir entrance
- [ ] export HP=15

### Question 6

How did you list the file contents of the room (folder) after you arrived?

- [ ] ls
- [ ] cd ..
- [ ] find
- [ ] cd /
- [ ] cd
- [ ] cd .

### Question 7

How did you show the contents of the scroll in many of the rooms?

- [ ] cd scroll
- [ ] ls scroll
- [ ] cat scroll
- [ ] find . -name scroll

## Bioinformatics

Let's change topics from the dungeon to bioinformatics.

Download the SARS-CoV-2 Wuhan-1 reference genome using this command in Linux:

```bash
curl 'https://www.ncbi.nlm.nih.gov/sviewer/viewer.cgi?tool=portal&save=file&log$=seqview&db=nuccore&report=genbank&id=1798174254&conwithfeat=on&withparts=on&hide-cdd=on' > SC2.gbk
```

### Question 8

How do you look at the top 10 lines of a file SC2.gbk?
Last 10 lines?
Choose two answers.

- [ ] top SC2.gbk
- [ ] head SC2.gbk
- [ ] bottom SC2.gbk
- [ ] tail SC2.gbk
- [ ] cd SC2.gbk

### Question 9

How do you find the number of times LOCUS appears in SC2.gbk? You can run `man something` or `something --help` to find more information about a command.

- [ ] grep -c LOCUS SC2.gbk
- [ ] cd LOCUS SC2.gbk
- [ ] ls SC2.gbk
- [ ] cd ..

### Question 10

What are two ways to view the whole contents of a file SC2.gbk?

_Select 2 correct answers_.

- [ ] ls SC2.gbk
- [ ] cat SC2.gbk
- [ ] less SC2.gbk (followed by `q` to exit)
- [ ] grep SC2.gbk

## More bioinformatics

Download the Wuhan-1 reference genome using this command in Linux (we already did this in the previous question): 

```bash
curl 'https://www.ncbi.nlm.nih.gov/sviewer/viewer.cgi?tool=portal&save=file&log$=seqview&db=nuccore&report=genbank&id=1798174254&conwithfeat=on&withparts=on&hide-cdd=on' > SC2.gbk
```

### Question 11

Using a Linux command, how many lines does the Wuhan-1 genbank file have?

In the second blank: what command did you use to find the number of lines in the Wuhan-1 genbank file? Hint: this command starts with a "w" and ends with "SC2.gbk".

1. `_____`
2. `_____`

### Question 12

How many times does the text "gene=" appear in the file?

What command did you use to find the number of times "gene=" appears?  Hint: the correct answer will have "gene=" and the filename in the command.

1. `_____`
2. `_____`

### Question 13

Count how many times the dinucleotide "aa" appears in the wuhan-1 genome.  Use the command "grep -o 'aa' SC2.gbk | wc -l"

I'll accept plus or minus one on your count.

`_____`

### Question 14

Critical thinking: the previous question's command does not in fact give you the number of times "aa" appears in the entire genome's sequence especially if we repeated this command for other genome files. Why? Look at the content of the file to see what information is presented to get a hint.

_Select 2 correct answers_.

- [ ] The genbank file has spaces or newlines between some nucleotides and so grep will not count dinucleotides that are split by whitespace. 
- [ ] grep irrevocably adds an additional "aa" to the file.
- [ ] "aa" could appear anywhere in the file, not just the nucleotide sequence. Therefore, some text in the header or some gene named, e.g., "aac", could add incorrect counts.
- [ ] The -o parameter indicates an output file, and so the grep command outputs nothing to the file "aa" instead.
- [ ] The method we used to download SC2.gbk does not include the sequence of the genome at all.
