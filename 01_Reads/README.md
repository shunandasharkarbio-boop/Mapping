## 📥 Import Paired-End Sequencing Data

### 📖 Overview

The first step in this workflow is to import the raw **paired-end FASTQ** sequencing files into the **Galaxy** platform. These files represent sequencing reads generated directly from a sequencing facility.

The datasets are then organized into a **paired collection**, allowing both forward and reverse reads to be processed together throughout the analysis.

---

## 📂 Input Files

Import the following FASTQ files from **Zenodo** (or your Galaxy Data Library if provided by your instructor):

| File | Description |
|------|-------------|
| `wt_H3K4me3_read1.fastq.gz` | Forward reads (R1) |
| `wt_H3K4me3_read2.fastq.gz` | Reverse reads (R2) |

### 🔗 Dataset Source

- https://zenodo.org/record/1324070/files/wt_H3K4me3_read1.fastq.gz
- https://zenodo.org/record/1324070/files/wt_H3K4me3_read2.fastq.gz

---

## 🛠️ Galaxy Steps

1. Import both FASTQ files into your Galaxy history.
2. Select the two datasets.
3. Create a **Paired Dataset Collection**.
4. Name the collection **`Paired Reads`**.

---

## 🧬 Why Use a Paired Collection?

Paired-end sequencing produces two reads for each DNA fragment:

- 🔴 **Read 1 (R1)** – Forward read
- 🔵 **Read 2 (R2)** – Reverse read

Keeping these reads together as a **paired collection** allows Galaxy tools to correctly process corresponding read pairs during alignment and downstream analyses.

---

## ⚠️ Quality Control Before Mapping

Raw sequencing data may contain:

- Low-quality bases
- Sequencing errors
- Adapter contamination
- Overrepresented sequences
- Duplicate reads

These issues can affect downstream analyses and lead to inaccurate biological interpretations.

Therefore, **quality assessment should always be performed before read mapping or any other downstream analysis.**

> **Recommendation:** Perform a complete quality control analysis (e.g., using **FastQC** and **Cutadapt**) before continuing with the mapping workflow.

---

## 🎓 Learning Outcome

Through this step, I learned how to:

- Import paired-end sequencing datasets into Galaxy
- Organize FASTQ files as a paired collection
- Understand the structure of paired-end sequencing data
- Recognize the importance of quality control before downstream bioinformatics analyses
