# NGS-Data-Analysis
NGS Data Analysis for WGS and RNASeq: Pipeline

  ![miRNA](https://user-images.githubusercontent.com/97247515/149810739-f0eaa3eb-6430-4538-8235-e82af3e912f5.jpg)
### Packages
1. Fast-QC and ea-utils
2. SRA-Toolkit
3. Samtools
4. Hisat
5. StringTie
6. R-Bioconductor
7. CuffDiff and cummeRbund  
8. Entre EDirect
9. Emboss
10. Blast+
11.minimap2
12.bcftools 
13.samtools
14.DWGSIM: a whole Genome Simulator for Next-Generation Sequencing 
15.V-pipe: V-pipe is a pipeline designed for analysing NGS data of short viral genomes
16.CD-HIT: is a very widely used program for clustering and comparing protein or nucleotide sequences.

  
## Genome Analysis: Overview

 ![Ge](https://user-images.githubusercontent.com/97247515/149814959-ca477ac1-1884-486f-8110-9215448cdb3e.png)
 ## What are Contig, Reads and Scaffold
 A contig is a set of overlapping DNA segments that together represent a consensus region of DNA (most frequent residues)relatively 150-1000 nucleotides bases in lenght.
 
Reads, sequencing can involve single-end (SE) or paired-end (PE) reads. In single end, machine can run the sequencing from one end to another end as a result we got single fastQ file per fragment/run whereas Paired-end sequencing means sequencing both ends of the DNA fragments and aligning the forward and reverse reads as read pairs and each run produce two fastQ files. Paired-end reads are preferable for de novo transcript discovery or isoforms expression analysis, as well as to characterise poorly annotated transcriptomes.
![reads](https://user-images.githubusercontent.com/97247515/155056129-023e2546-9499-419f-8caf-a45b3f838de4.png)

The orientation of contigs constructed from the reads and allows for their assembly into scaffolds in a process called scaffolding each scaffold consist of overlapping contigs separated by gaps of known length also known as supercontigs.

![scaffold](https://user-images.githubusercontent.com/97247515/155056861-39f56ebc-df2a-4e82-bba9-995bc19ddab8.png)

### FastQ Format:
1. Header - starts with @
   1. Must start with a unique identifier (up to first space)
   2. Can often have substructure
2. Base calls (can include N or IUPAC codes)
3. Mid-line - starts with + usually empty
4. Quality scores
   1. Per base signal:noise assessment
   2. ASCII encoded Phred score

![fastq](https://user-images.githubusercontent.com/97247515/155057852-e7adc578-835a-42be-8200-0c0f5c0895da.png)



