# lab9_comparative_genomics

This week we are going to build and visualize a phylogenetic gene-tree based on the metabolic genes you found in the previous labs. 

## Step 1 - Set up folder

You will need to make a new folder called ```lab_9```

Move into the folder using ```cd```

Now you can copy the sequences from your gene that you were investigating and researching in Lab 8. This will be your **GENE**.

Copy the file from the class space containing the sequences. 

```bash
cp /projects/class/binf3101_001/class_seqs/GENE.class.fasta .
```

## Step 2 - Align the sequences 

We need to align our sequences prior to creating a phylogenetic tree. We will use MAFFT again to do this. 

### Step 2a - Load MAFFT
First you will need to load mafft

```bash
module load mafft
```

### Step 2b - Create an alignment

The general formula for mafft is 

```mafft inputfile > outputfile```

In this case your input file is the ```GENE.class.fasta``` file that we will use to build our tree. 
The output file will be a new name. But I suggest something like ```GENE.align.fasta```


You should now have two files in your directory. You should check with ```ls```

There will be the original GENE file and the aligned GENE file.

## Step 3 - Create your gene-based phylogeny

We will use a program called IQTree to build a phylogenetic tree. 

IQTree is very easy to run and only requires one argument - your aligned GENE file. 

To run IQ tree on _your_ gene alignment use the code below as an example

```bash
module load iqtree

iqtree2 -s GENE.align.fasta
```

You will see things start to print to your screen. When it is done running, it will print the day and time. 

## Step 4 - Analyze your log file 

The analysis conducted by IQTree are saved in the **log** file that will have the format ```GENE.align.fasta.log```

Look at this file using the ```cat``` command or ```less```. Answer the following questions about your tree

### Examine the input sequences

# LQ 1
How many sequences were in the alignment file?

# LQ 2 
How many sites/columns were parsimony-informative?

# LQ 3 
How many sites/columns were constant?

# LQ 4
Each of the sequences is now labeled with the SRR number in front of the gene name. Find your SRR number in the section that lists the Gap/Ambiguity scores. 
What percent of your sequence was either a Gap or an Ambiguity?


### Examine the ModelFinder Results

# LQ 5

ModelFinder tests various models of evolution that are then used to build the tree. 
Which is the "Best-fit model"? 

# LQ 6
The model selected likely has multiple parts separated by "+" signs. The first part of this model (before the first +) is the **amino acid exchange rate matrix**. 

For example, a model could be ```mtInv+I+G4```

mtInv - Mitochondrial Invertebrate amino acid exchange rate matrix

I - Rate heterogeneity setting to allow for a proportion of invariable sites

G4 - Discrete Gamma model

What does your amino acid exchange rate matrix stand for? Aka what is the name of it? Use this website to find out http://www.iqtree.org/doc/Substitution-Models 


### Examine the section called ```FINALIZING TREE SEARCH```

This section will report how your tree search went. Examine this section and answer the questions below

# LQ 7

What was the total number of iterations used to search for your tree? 


# Step 5

You will now need to download the tree file which ends in "treefile" - for example ```GENE.align.fasta.treefile```

If you cannot remember how to download files from the cluster onto your computer, refer to previous labs. 


We will look at our tree on a website called itol or the Interactive Tree of Life. 

Go to https://itol.embl.de/

Once you are at the itol site click the **Upload** button

![image](https://github.com/BINF-3101/lab9_comparative_genomics/assets/47755288/6b41a864-0b66-4449-b27b-5914cac0b379)







