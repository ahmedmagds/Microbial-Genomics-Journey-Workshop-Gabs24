# Microbial Genomics Journey Workshop Gaborone 2024
## Part 7: Pangenome analysis
The pangenome of a microbial species is the total set of genes present in all members of that species. It is typically much larger than the genome of any single member of the species. The pangenome can be divided into two categories: the core genome and the accessory genome.<br/>

The core genome is the set of genes that are present in all members of the species. These genes are essential for the basic functions and survival of the microorganisms and are typically conserved due to their importance.<br/>

The accessory genome (also known as the dispensable or flexible genome) is the set of genes that are present in some, but not all, members of the species. It is typically more variable than the core genome. These genes can provide additional capabilities or adaptations to specific environments, such as resistance to antibiotics, virulence factors, or metabolic pathways. The accessory genome contributes to the genomic diversity and ecological success of a species.<br/>

The pangenome can be used to study the evolution of microbial species, to identify genes that are important for particular functions, and to develop new methods for microbial diagnostics and therapeutics.<br/>

Here are some examples of how the pangenome has been used in research:

* To study the evolution of microbial species: The pangenome can be used to compare the genomes of different strains of a species
* To identify genes that have been gained or lost over time. This can help to understand how the species has adapted to different environments.
* To identify genes that are important for particular functions:
* To develop new methods for microbial diagnostics and therapeutics: The pangenome can be used to identify genes that are unique to particular strains of a species. This can help to develop new methods for diagnosing and treating microbial infections.

## Roary
[Roary](http://sanger-pathogens.github.io/Roary/) is a tool designed to quickly build large-scale pan genomes for prokaryote populations, consisting of hundreds or thousands of isolates. It identifies core and accessory genes, enabling researchers to gain insights into the genetic structure of prokaryotic genomes. Roary can allow efficient analysis on a standard desktop without sacrificing accuracy. It will give different outputs which can be explored and understood from the explanation available from roary website.

#### Run Roary
```
cd /data/roary
bash roary_instruction.sh
```
What is in the script?
```
roary -e -n -p 4 -f /data/roary/ /data/roary/gff3/*.gff3
```
Let's explore the roary_results
```
less summary_statistics.txt
cd result
less summary_statistics.txt
less gene_presence_absence.csv
```
## Scoary
[Scoary](https://github.com/AdmiralenOla/Scoary) is a tool that uses Roary's gene_presence_absence.csv file and a user-created traits file to calculate associations between accessory genome genes and traits. It generates a list of genes ranked by the strength of association for each trait.
#### Run Scoary
```
scoary -p 1 -g /session7/roary_results/gene_presence_absence.csv -t traits.csv
```

## Further Readings
* [roary](https://academic.oup.com/bioinformatics/article/31/22/3691/240757)
* [Scoary](https://genomebiology.biomedcentral.com/articles/10.1186/s13059-016-1108-8)
* [Panaroo](https://genomebiology.biomedcentral.com/articles/10.1186/s13059-020-02090-4)
