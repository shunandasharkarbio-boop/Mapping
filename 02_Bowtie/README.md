Map reads on a reference genome
Read mapping is the process to align the reads on a reference genomes. A mapper takes as input a reference genome and a set of reads. Its aim is to align each read in the set of reads on the reference genome, allowing mismatches, indels and clipping of some short fragments on the two ends of the reads.
Currently, there are over 60 different mappers, and their number is growing. In this tutorial, we will use Bowtie2, a fast and memory-efficient open-source tool particularly good at aligning sequencing reads of about 50 up to 1,000s of bases to relatively long genomes
Checking the mapping statistics is an important step to do before continuing any analyses. There are several potential sources for errors in mapping, including (but not limited to):

Polymerase Chain Reaction (PCR) artifacts: Many high-throughput sequencing (HTS) methods involve one or multiple PCR steps. PCR errors will show as mismatches in the alignment, and especially errors in early PCR rounds will show up in multiple reads, falsely suggesting genetic variation in the sample. A related error would be PCR duplicates, where the same read pair occurs multiple times, skewing coverage calculations in the alignment.
Sequencing errors: The sequencing machine can make an erroneous call either for physical reasons (e.g. oil on an Illumina slide) or due to properties of the sequenced DNA (e.g., homopolymers). As sequencing errors are often random, they can be filtered out as singleton reads during variant calling.
Mapping errors: The mapping algorithm can map a read to the wrong location in the reference. This often happens around repeats or other low-complexity regions.
So if the mapping statistics are not good, you should investigate the cause of these errors before going further in your analyses.

After that, you should have a look at the reads and inspect the BAM file where the read mappings are stored.

Inspection of a BAM file
A BAM (Binary Alignment Map) file is a compressed binary file storing the read sequences, whether they have been aligned to a reference sequence (e.g. a chromosome), and if so, the position on the reference sequence at which they have been aligned.

Col	Field	Type	Brief Description
1	QNAME	String	Query template NAME
2	FLAG	Integer	Bitwise FLAG
3	RNAME	String	References sequence NAME
4	POS	Integer	1- based leftmost mapping POSition
5	MAPQ	Integer	MAPping Quality
6	CIGAR	String	CIGAR String
7	RNEXT	String	Ref. name of the mate/next read
8	PNEXT	Integer	Position of the mate/next read
9	TLEN	Integer	Observed Template LENgth
10	SEQ	String	Segment SEQuence
11	QUAL	String	ASCII of Phred-scaled base QUALity+33


