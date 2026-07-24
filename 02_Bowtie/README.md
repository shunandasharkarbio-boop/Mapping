# 🧬 Read Mapping to a Reference Genome

## 📖 Overview

Read mapping is the process of aligning sequencing reads to a **reference genome** to determine their original genomic locations. This is one of the most important steps in any **Next-Generation Sequencing (NGS)** analysis because it provides the genomic context required for downstream analyses such as **variant calling**, **gene expression analysis**, and **peak detection**.

In this tutorial, read alignment is performed using **Bowtie2**, a fast and memory-efficient aligner optimized for mapping short sequencing reads (approximately **50 bp to several thousand base pairs**) to large reference genomes.

---

## 🎯 Objectives

- Map paired-end sequencing reads to a reference genome
- Generate alignment (BAM) files
- Evaluate mapping quality and statistics
- Inspect read alignments
- Prepare data for downstream genomic analyses

---

## 🛠️ Tool Used

| Tool | Purpose |
|------|---------|
| 🧬 **Bowtie2** | Align sequencing reads to the reference genome |
| 🌌 **Galaxy Platform** | Execute reproducible bioinformatics workflows |
| 👁️ **IGV** | Visualize mapped reads stored in BAM files |

---

## 🔄 Workflow

```text
Paired-End FASTQ Files
          │
          ▼
Reference Genome
          │
          ▼
Bowtie2 Read Mapping
          │
          ▼
SAM/BAM Alignment Files
          │
          ▼
Mapping Statistics
          │
          ▼
BAM Inspection (IGV)
          │
          ▼
Downstream Analysis
```

---

## 📊 Why Check Mapping Statistics?

Evaluating mapping statistics is an essential quality control step before continuing any downstream analysis. Poor mapping quality may indicate problems with the sequencing data, reference genome, or alignment process.

Common causes of mapping errors include:

### 🧪 PCR Artifacts

During library preparation, **Polymerase Chain Reaction (PCR)** can introduce:

- Amplification errors
- Duplicate read pairs
- False mismatches
- Biased coverage estimates

---

### ⚠️ Sequencing Errors

Sequencing instruments may occasionally generate incorrect base calls due to:

- Instrument-related issues
- Low-quality sequencing cycles
- Homopolymer regions
- Random base-calling errors

These errors can often be filtered during variant calling.

---

### 🧬 Mapping Errors

Reads may align to incorrect genomic locations, especially in:

- Repetitive DNA regions
- Low-complexity sequences
- Highly similar genomic regions

Incorrect alignments can lead to inaccurate biological interpretations.

> **Good mapping statistics are essential for producing reliable downstream results.**

---

# 📁 Inspecting a BAM File

After mapping, sequencing alignments are stored in a **BAM (Binary Alignment Map)** file.

A BAM file is a compressed binary version of a SAM file and contains:

- Sequencing read information
- Alignment positions
- Mapping quality scores
- Read orientation
- Alignment operations

BAM files are commonly visualized using tools such as **IGV (Integrative Genomics Viewer)**.

---

## 📋 BAM File Format

| Column | Field | Description |
|---------|-------|-------------|
| **1** | **QNAME** | Query (read) name |
| **2** | **FLAG** | Bitwise flag describing read properties |
| **3** | **RNAME** | Reference sequence (chromosome) name |
| **4** | **POS** | Leftmost mapping position on the reference genome |
| **5** | **MAPQ** | Mapping quality score |
| **6** | **CIGAR** | Alignment operations describing matches, insertions, deletions, and clipping |
| **7** | **RNEXT** | Reference name of the mate read |
| **8** | **PNEXT** | Position of the mate read |
| **9** | **TLEN** | Observed template length |
| **10** | **SEQ** | Read nucleotide sequence |
| **11** | **QUAL** | Phred-scaled base quality scores |

---

## 🎓 Learning Outcomes

Through this exercise, I learned how to:

- Map paired-end sequencing reads using **Bowtie2**
- Generate and interpret **SAM/BAM** alignment files
- Evaluate mapping quality statistics
- Recognize common sources of mapping errors
- Inspect read alignments using **IGV**
- Prepare high-quality alignment data for downstream bioinformatics analyses
