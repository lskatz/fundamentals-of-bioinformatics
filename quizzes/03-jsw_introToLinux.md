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
