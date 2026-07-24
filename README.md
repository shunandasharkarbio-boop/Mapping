# 🧬 Read Mapping using Bowtie2 in Galaxy

## 📖 Overview

Sequencing technologies generate millions of short DNA sequences (**reads**), but these reads do not contain information about their original positions within the genome. **Read mapping** is the process of aligning these sequencing reads to a **reference genome**, allowing researchers to determine where each read originated.

Mapping is a fundamental step in modern bioinformatics workflows and serves as the foundation for downstream analyses such as **RNA-Seq**, **variant calling**, **genome assembly**, and **gene expression analysis**.

---

## 🎯 Objectives

- Understand the concept of read mapping
- Learn why reference genomes are essential
- Map sequencing reads using **Bowtie2**
- Visualize mapped reads using **IGV**
- Prepare alignment data for downstream analyses

---

## ❓ Why is Read Mapping Important?

Raw sequencing reads lack genomic coordinates, making it impossible to determine:

- Which chromosome they belong to
- Which gene they originate from
- Whether they contain genetic variants
- Their contribution to gene expression

By comparing each read against a **reference genome**, mapping assigns the most likely genomic location to every sequence.

---

## 🔬 Challenges in Read Mapping

Mapping millions of sequencing reads presents several computational challenges:

- 🧬 Human genomes contain approximately **3 billion base pairs**
- 📄 NGS experiments often generate **millions of short reads**
- 🔁 Repetitive genomic regions may produce multiple possible mapping locations
- ⚡ Efficient algorithms are required to process large datasets within a reasonable time

Specialized mapping tools are designed to overcome these challenges by rapidly identifying the most likely genomic position for each read.

---

## 🆚 Mapping vs Sequence Alignment

Although mapping and sequence alignment are related concepts, they serve different purposes.

| Mapping | Sequence Alignment |
|---------|--------------------|
| Determines the genomic origin of sequencing reads | Compares nucleotide sequences base by base |
| Optimized for millions of short reads | Optimized for detailed sequence comparison |
| Fast and computationally efficient | More computationally intensive |
| Used in RNA-Seq, variant calling, and genome analysis | Commonly performed using tools such as BLAST |

> While tools like **BLAST** can identify similar sequences, performing BLAST searches for millions of reads would be computationally expensive. Read mappers such as **Bowtie2** are specifically designed to rapidly locate the most likely genomic position of each sequencing read.

---

## 🔄 Workflow

```text
Raw FASTQ Reads
        │
        ▼
Reference Genome
        │
        ▼
Read Mapping (Bowtie2)
        │
        ▼
SAM/BAM Alignment Files
        │
        ▼
Alignment Visualization (IGV)
        │
        ▼
Downstream Analysis
```

---

## 🛠️ Tools Used

| Tool | Purpose |
|------|---------|
| 🧬 **Bowtie2** | Fast and accurate alignment of sequencing reads to a reference genome |
| 👁️ **IGV (Integrative Genomics Viewer)** | Visualization and exploration of mapped sequencing reads |
| 🌌 **Galaxy Platform** | Workflow execution and reproducible bioinformatics analysis |

---

## 📊 Applications

Read mapping is an essential step in numerous genomic analyses, including:

- 🧬 RNA-Seq
- 🔬 ChIP-Seq
- 🧪 Variant Calling
- 🌍 Whole Genome Sequencing (WGS)
- 🧫 Whole Exome Sequencing (WES)
- 📈 Gene Expression Analysis
- 🦠 Microbial Genome Analysis

---

## 🎓 Learning Outcomes

Through this tutorial, I learned how to:

- Understand the principles of read mapping
- Align sequencing reads to a reference genome using **Bowtie2**
- Generate and interpret alignment files (SAM/BAM)
- Visualize mapped reads with **IGV**
- Appreciate the role of mapping in downstream genomic analyses
- Perform reproducible alignment workflows using Galaxy
