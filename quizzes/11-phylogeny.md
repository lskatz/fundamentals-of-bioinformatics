# Homework - Phylogeny

## Section 1

### Question 1

What is a phylogenetic tree?

- A depiction of evolutionary relationships between collection of items, for all life. Any diagram with less than all of life is not a phylogenetic tree.
- A depiction of clustering between all known items, with no information on evolution. Any diagram with less than all known items is not a phylogenetic tree.
- A depiction of clustering between items, with no information on evolution
- A depiction of evolutionary relationships between collection of items

### Question 2

What can I use a phylogenetic tree for? _Four options are allowed_.

- [ ] Most recent common ancestor (MRCA) reconstruction
- [ ] Determining which species are superior
- [ ] Identifying how individuals or strains are related within a species
- [ ] Determining the age of a tree
- [ ] Estimating the geographic distribution of a species
- [ ] Describing co-evolution of pathogens with hosts
- [ ] Identifying a date when an evolutionary event happened
- [ ] Representing the food chain or food web
- [ ] Finding the family history of a gene family
- [ ] Finding species that are related
- [ ] Divergence time estimation

### Question 3

What is a branch on a phylogeny? An internal node?

- A branch visualizes a link between a node and its ancestor. An internal node is a confidence score that the tree is correct.
- A branch is a measure of how many nodes are on the tree. An internal node is a confidence score that the tree is correct.
- A branch is a confidence score that the tree is correct. An internal node is a hypothetical ancestor that gives rise to descendant lineages.
- A branch visualizes a link between a node and its ancestor. An internal node is a hypothetical ancestor that gives rise to descendant lineages.

### Question 4

What are leaves, tips, and terminal nodes?

- They are all synonyms for a taxon with no descendants.
- They are all synonyms for a confidence score of an ancestor node.
- They are all synonyms for fine-level definitions of a tree.
- They are all synonyms for a taxon that might not evolve much more in the future.
- They are like the last stop on the evolutionary bus route. It's where all the cool species hop off and say, 'This is our final destination! We've reached our stop, folks!'

### Question 5

What is a rooted tree vs an unrooted tree?

- A rooted tree has connections between all nodes, but an unrooted tree does not connect every node to each other (floating nodes).
- A rooted tree bifurcates at each hypothetical ancestor, but an unrooted tree can have more than two splits at each ancestor.
- A rooted tree implies a directionality of evolution or time, and an unrooted tree shows the same information without directionality of evolution or time.
- A rooted tree is based on a single ancestor, but an unrooted tree is based on multiple ancestors.

### Question 6

Tips have `_` connection(s), internal nodes have `_` connection(s), and the root has `_` connection(s). Use a numerical answer instead of spelling it out. For example, for the number 1, use "1" instead of "one" (without quotes).

`_____`
`_____`
`_____`

### Question 7

A branch support value is a(n)

- measure of confidence
- measure of evolution between ancestor and descendent
- extra connection between nodes to ensure connectivity
- quality control (QC) measure to determine whether the trees can have additional nodes

### Question 8

What are some assumptions of a phylogeny when it is created?

_Select 2 correct answers_.

- [ ] survival of the fittest
- [ ] a genome size of at least 1 megabase
- [ ] standard temperature and pressure
- [ ] correct alignment
- [ ] vertical, not horizontal evolution

### Question 9

What does a scale bar show on a tree?

- Average weight of the branches
- The total size of the tree
- Support of the last common ancestor
- Evolutionary distance

### Question 10

What are the two treeing methods?

_Select 2 correct answers_.

- Character-based
- Codon bias
- Distance matrix
- Indel ratios
- Kmers

### Question 11

If you have a tree with 100 tips, why can't you evaluate every possible tree to ensure you have the best tree?

- Even after you solve for the most correct tree, there is always another tree topology that is equally correct
- The science has not caught up with the computing power
- My computer is not powerful enough, but another might be for this tree with 100 tips
- There are too many choices to parse through

### Question 12

On the other hand, what is a danger of using a heuristic?

- Sometimes it does not include a taxon: solving with the heuristic might output a tree of only 99 tips when 100 were required.
- There is no danger; it is simply another algorithm
- You might miss the most optimal tree
- The heuristic itself has not been properly solved in this situation

### Question 13

Which of the following is not a valid bootstrap of this alignment? Two samples are shown, with four positions in the alignment.

```text
1 2 3 4  
A T C G  
T T C A  
```

- 2 2 3 4  
  T T C G  
  T T C A  
- 1 2 3 4  
  A T C G  
  T T C A  
- 1 2 3 5  
  A T C A  
  T T C A  
- 4 4 4 4  
  G G G G  
  A A A A  

### Question 14

What is a valid command to run iqtree on an alignment file, `in.fasta`?

- `iqtree -s in.fasta`
- `iqtree -a in.fasta`
- `conda activate iqtree`
- `iqtree in.fasta`