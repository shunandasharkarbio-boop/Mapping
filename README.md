# Mapping
Sequencing produces a collection of sequences without genomic context. We do not know to which part of the genome the sequences correspond to. Mapping the reads of an experiment to a reference genome is a key step in modern genomic data analysis. With the mapping the reads are assigned to a specific location in the genome and insights like the expression level of genes can be gained.

The reads do not come with position information, so we do not know what part of the genome they came from. We need to use the sequence of the read itself to find the corresponding region in the reference sequence. But the reference sequence can be quite long (~3 billion bases for human), making it a daunting task to find a matching region. Since our reads are short, there may be several, equally likely places in the reference sequence from which they could have been read. This is especially true for repetitive regions.

In principle, we could do a BLAST analysis to figure out where the sequenced pieces fit best in the known genome. We would need to do that for each of the millions of reads in our sequencing data. Aligning millions of short sequences this way may, however, take a couple of weeks. And we do not care about the exact base to base correspondence (alignment). What we are interested in is “where these reads came from”. This approach is called mapping.

In the following, we will process a dataset with the mapper Bowtie2 and we will visualize the data with the program IGV.
