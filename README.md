# NGS-Data-Analysis
NGS Data Analysis for WGS and RNASeq: Pipeline

  ![miRNA](https://user-images.githubusercontent.com/97247515/149810739-f0eaa3eb-6430-4538-8235-e82af3e912f5.jpg)
  
## **Tools for** Analysis 
![ngstool](https://user-images.githubusercontent.com/97247515/155968414-0872cb0c-828b-4888-8e30-1d311b1d7da2.png)

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

### Important QC info:
**Quality Score:** The quality score heavily depends on the average number of times each base in the genome is actually read during the sequencing process.

The Phred score is a measure for base quality in DNA sequencing. The larger the Phred value, the better the quality of a sequenced base.
Phred quality scores Q are defined as a property that is logarithmically related to the base-calling error probabilities P.

![pred](https://user-images.githubusercontent.com/97247515/155059854-154c1362-6dad-49c8-8bf8-bce698690f26.png)

For example, if Phred assigns a quality score of 30 to a base, the chances that this base is called incorrectly are 1 in 1000.

![prr2](https://user-images.githubusercontent.com/97247515/155060160-ed531742-ee15-4c9d-b321-b25ccea8eb12.png)

The Phred quality score is the negative ratio of the error probability to the reference level of P=1 expressed in Decibel (dB).
Example: 
Character: @HWI ASCII symbol
Sequence:  AAGA sequenced nucleotides on the Fastq file

For the 1st base A the corresponding quality score @ so the score for A as per each of the scoring schemes will be…? If the Character @ and its ASCII value as per lookup table is = 64

Then Quality Score(Q) for base A = ASCII value - Base Value for sanger (i.e: 33)
                                                         = 64-33 
                                                         = 31 corresponding Phred quality score is 99.9%
The guanine-cytosine (GC) content of a gene or whole genome is the percentage of nitrogenous bases that are guanine (G) or cytosine (C)

**GC content**  = (number of G's + C's)  /  (number of T's + A's)  * 100


**Coverage:** The average coverage for a whole genome can be calculated from the length of the original genome (G), the number of reads (N), and the average read length (L)

Number of reads*average read length / Genome length

If the 
Genome size is: 40.000bp
Read length is: 100bp
No of reads generated: 1000.000
Then Coverage is: 100*1000.000 / 40.000 = 2500x Coverage

For example, a hypothetical genome with 2,000 base pairs reconstructed from 8 reads with an average length of 500 nucleotides will have 2× redundancy. This parameter also enables one to estimate other quantities, such as the percentage of the genome covered by reads (sometimes also called the breadth of coverage). High coverage in shotgun sequencing is desired because it can overcome errors in base calling and assembly. The subject of DNA sequencing theory addresses the relationships of such quantities.
**Depth of coverage (mapping depth):** How strong is a genome "covered" by sequenced fragments (short reads)?

Per-base coverage is the average number of times a base of a genome is sequenced. The coverage depth of a genome is calculated as the number of bases of all short reads that match a genome divided by the length of this genome. It is often expressed as 1X, 2X, 3X,... (1, 2, or, 3 times coverage)

**The breadth of coverage (covered length)** 
How much of a genome is "covered" by short reads? Are there regions that are not covered, even not by a single read?

The breadth of coverage is the percentage of bases of a reference genome that are covered with a certain depth. For example: "90% of a genome is covered at 1X depth, and still 70% is covered at 5X depth.

