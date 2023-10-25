# lab9_comparative_genomics

# OUTLINE

[Step 1 - Setup](#step-1---set-up-folder)

[Step 2 - Align Seqs](#step-2---align-the-sequences)

[Step 3 - Create Gene Tree](#step-3---create-your-gene-based-phylogeny)

[Step 4 - Analyze Output(#step-4---analyze-your-log-file)

[LQ1](#lq-1)

[LQ2](#lq-2)

[LQ3](#lq-3)

[LQ4](#lq-4)

[LQ5](#lq-5)

[LQ6](#lq-6)

[LQ7](#lq-7)

[Step 5 - iTOL](#step-5---upload-tree-file-to-itol)

[Step 6 - Root the Tree](#step-6---root-your-tree)

[LQ8](#lq-8)

[Step 7 - Compare Trees](#step-7---compare-trees)

[LQ9](#lq-9)

[LQ10](#lq-10)

This week we are going to build and visualize a phylogenetic gene-tree based on the metabolic genes you found in the previous labs. 

## Step 1 - Setup folder

You will need to make a new folder called ```lab_9```

Move into the folder using ```cd```

Now you can copy the sequences from your gene that you were investigating and researching in Lab 8. This will be your **GENE**.

Copy the file from the class space containing the sequences. 

```bash
cp /projects/class/binf3101_001/class_seqs/GENE.class.fasta .
```
&ensp;

## Step 2 - Align the sequences 

We need to align our sequences prior to creating a phylogenetic tree. We will use MAFFT again to do this. 

&ensp;

### Step 2a - Load MAFFT
First you will need to load mafft

```bash
module load mafft
```

&ensp;

### Step 2b - Create an alignment

The general formula for mafft is 

```mafft inputfile > outputfile```

In this case your input file is the ```GENE.class.fasta``` file that we will use to build our tree. 
The output file will be a new name. But I suggest something like ```GENE.align.fasta```


You should now have two files in your directory. You should check with ```ls```

There will be the original GENE file and the aligned GENE file.

&ensp;

## Step 3 - Create your gene-based phylogeny

We will use a program called IQTree to build a phylogenetic tree. 

IQTree is very easy to run and only requires one argument - your aligned GENE file. 

To run IQ tree on _your_ gene alignment use the code below as an example

```bash
module load iqtree

iqtree2 -s GENE.align.fasta
```

You will see things start to print to your screen. When it is done running, it will print the day and time. 

&ensp;

## Step 4 - Analyze your log file 

The analysis conducted by IQTree are saved in the **log** file that will have the format ```GENE.align.fasta.log```

Look at this file using the ```cat``` command or ```less```. Answer the following questions about your tree

### Examine the input sequences

&ensp;

# LQ 1
How many sequences were in the alignment file?

&ensp;

# LQ 2 
How many sites/columns were parsimony-informative?

&ensp;

# LQ 3 
How many sites/columns were constant?

&ensp;

# LQ 4
Each of the sequences is now labeled with the SRR number in front of the gene name. Find your SRR number in the section that lists the Gap/Ambiguity scores. 
What percent of your sequence was either a Gap or an Ambiguity?

&ensp;

### Examine the ModelFinder Results

&ensp;

# LQ 5

ModelFinder tests various models of evolution that are then used to build the tree. 
Which is the "Best-fit model"? 

&ensp;

# LQ 6
The model selected likely has multiple parts separated by "+" signs. The first part of this model (before the first +) is the **amino acid exchange rate matrix**. 

For example, a model could be ```mtInv+I+G4```

mtInv - Mitochondrial Invertebrate amino acid exchange rate matrix

I - Rate heterogeneity setting to allow for a proportion of invariable sites

G4 - Discrete Gamma model

What does your amino acid exchange rate matrix stand for? Aka what is the name of it? Use this website to find out http://www.iqtree.org/doc/Substitution-Models 

&ensp;

### Examine the section called ```FINALIZING TREE SEARCH```

This section will report how your tree search went. Examine this section and answer the questions below

&ensp;

# LQ 7

What was the total number of iterations used to search for your tree? 

&ensp;

## Step 5 - Upload tree file to iTOL

You will now need to download the tree file which ends in "treefile" - for example ```GENE.align.fasta.treefile```

If you cannot remember how to download files from the cluster onto your computer, refer to previous labs. 


We will look at our tree on a website called itol or the Interactive Tree of Life. 
&ensp;
Go to https://itol.embl.de/
&ensp;
Once you are at the itol site click the **Upload** button
&ensp;
<img src="https://github.com/BINF-3101/lab9_comparative_genomics/assets/47755288/6b41a864-0b66-4449-b27b-5914cac0b379" width=500>

You will see an option to **Choose File** - this is where you will upload your treefile 

&ensp;

## Step 6 - Root your tree

You will see a branch that is labeled **OUTGROUP**. We need to re-root our tree to make sure the outgroup is on the _outside_ of our tree

Follow the steps below to re-root your tree

&ensp;

### Step 6a - Hover over the branch labeled OUTGROUP

<img src="https://github.com/BINF-3101/lab9_comparative_genomics/assets/47755288/6548d761-7cf3-49f9-a243-74b80501470e" width=500>

&ensp;

### Step 6b - Click on the branch labeled OUTGROUP

<img src="https://github.com/BINF-3101/lab9_comparative_genomics/assets/47755288/1d001310-2d79-44ea-8f2f-ee73db263a16" width=500>

&ensp;

### Step 6c - Under Tree Structure click "Re-root the tree here"
<img src="https://github.com/BINF-3101/lab9_comparative_genomics/assets/47755288/844c2680-837b-4a81-92f2-6c10cd072a37" width=500>

The new tree should now be rooted by the OUTGROUP

<img src="https://github.com/BINF-3101/lab9_comparative_genomics/assets/47755288/8a6db345-892a-42b1-84c8-ddb151d2f081" width=500>

Examine the tree and identify the **smallest clade** that includes your species and the sister taxa

&ensp;

# LQ 8 

What are the names of the species that form a clade with your sequence? If this clade includes _all the other sequences_ you can specify that. 

You will need to take the SRR numbers and convert them to species: https://docs.google.com/spreadsheets/d/1dMQB6ykYhzzFyWtFi-jBCXJQd3Yk2UCLWxDkSXm-Gk4/edit?usp=sharing 

&ensp;

## Step 7 - Compare trees

Below I have copied the **species tree**. There is also a copy of this on the Canvas site. 

![species_tree](https://github.com/BINF-3101/lab9_comparative_genomics/assets/47755288/24ff7c31-f561-4334-9637-24d8067fb602)

&ensp;

# LQ 9

Based on the **species tree** What are the names of the species that form a clade with your species? If this clade includes _all the other species_ you can specify that. 

&ensp;

# LQ 10 

Are there any species within the **gene-based clade** that are **_not_** found in the **species-based clade**? 















