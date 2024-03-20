# Microbial Genomics Journey Workshop Gaborone 2024
## Part 9: Phylogenetic analysis
## IQ-Tree
## Background
### IQ-Tree was originally released in 2014 as an alternative methods of ML tree inference. Since, an updated version of the tool was assembled, IQ-Tree v2 (REF:https://doi.org/10.1093/molbev/msaa015), which we'll be using for this class. IQ-Tree is a fast, user-friendly, and **extremely** well documented tool that has been growing in popularity evolutionary sciences since it's initial release. It works on most data sets, including nucleotide/amino acid alignments in any format, traits, or gene presence/absence (both of which are binary data). It runs quickly your computer for lightweight analyses, and can be threaded to work on a cluster if you have a larger dataset. There is also an online GUI to help you get started, but I really prefer the CLI. We'll just scratch the surface of what it can do, but if you want to know more, check out the documentation here (http://www.iqtree.org/doc/).

### Imporantly, IQ-Tree does two things better than any other maximum-likelihood tool I've used.  First, it uses another tool, ModelFinderPlus, that goes through your data and finds the substitution model. Secondly, by using Ultrafast bootstapping, you can get a sense for the branch supports in a fraction of the time and on your laptop (if you ask most phylogenetists, they hate running boots because they are massively time consuming).

### We'll just scratch the surface of what it can do, but if you want to know more, check out the documentation here (http://www.iqtree.org/doc/).

### Things I've used IQ-Tree for:
    - Phylogenetic inference from binary data
    - Building trees based on amino acid alignments
    - Ancestral state reconstruction of common ancesetors
    - Statistical analyses of tree congruence
    - Substitution model selection
    - Tree topology statistical test
    - Approximating evolutionary rates at specific sites

***Remember*** Building phylogenies is time and energy intensive and requires your attention as a scientist. There are multiple steps you have to complete and check before you make the tree. Once you have the tree, it can be hard to analyze or understand. It can feel overwhelming at first, but it gets easier with practice.

#### Run IQTree
```
cd /data/iqtree
ls
bash iqtree_instruction.sh
```
What is in the script?
```
iqtree2 -s /data/iqtree/core.full.aln -m GTR+I+G
```

#### You did it! The program outputs a bunch of files, and you should read about what each one is. But the <NAME>.treefile can be opened in [Itol](https://itol.embl.de/tree/1631161576354651710185868).

## Cladebreaker
Genomic surveillance for emerging diseases, transmission events, epidemics and outbreaks is becoming the gold standard for molecular epidemiology. Whole genome phylogenetic analysis is the primary method for inferring clonality (monophyly) of outbreaks and transmission patterns, but clear criteria for testing these inferences remain unclear. One approach is to include existing genomes from public databases to test relationships inferred in the phylogeny.  If genomes not associated with the outbreak or transmission event “break up” relationships in the tree by branching within putative outbreak clades, then the observed outbreak may not be clonal. With large genomic databases it may not be clear which genomes to add to a phylogenetic analysis, and including all genomes can become extremely computationally expensive.<br/>  

[CladeBreaker](https://github.com/andriesfeder/cladebreaker) test the hypothesis of clonality by using the most similar genomes available in the database. If these genomes fail to break up the monophyly of the outbreak clade then this provides the strongest evidence possible for clonality.<br/>

* Cladebreaker uses the topgenome function of the WhatsGNU application to quickly identify the most similar genomes to each of the genomes in an outbreak or transmission investigation.
* It takes in sequence reads, finds the most similar genomes from a database, and runs a full sequence-based phylogenetic analysis based on a reference-based SNP matrix or concatenated amino acids.  The output is a phylogenetic tree containing both the best-hit genomes and the query genomes.  
* Let's have a look at this [tree](https://itol.embl.de/tree/1631161576354651710185868)in iTol from a project we are currently working on.

## Further Readings
* [Viewing Tables on the command line](https://rrwick.github.io/2023/04/19/viewing_tables_on_the_command_line.html)
* [iqtree manual](http://www.iqtree.org/doc/)
* [Ascertainment bias correction](http://www.iqtree.org/doc/Substitution-Models#ascertainment-bias-correction)
* [BEAST Tutorials for Bayesian Inference](http://www.beast2.org/tutorials/)
