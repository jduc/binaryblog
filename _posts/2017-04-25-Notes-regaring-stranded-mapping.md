---
layout: default
title:  "Notes regarding stranded mapping"
categories: bioinfo
description: "Stranded reads are unaware of where they come from"
---

# Stranded RNA-seq mapping remarks

Stranded RNA-seq with the true-seq protocol of illumnia is not telling you from which strand the read emanated. It simply ensures that all the reads coming from a locus all have the same strand.  

## Mapping with different strand parameters yield the same results
That's why in the settings fr-firststrand, fr-secondstrand or unstranded when mapping with tophat for instance (hisat or anything), the mapper yield the same informations. Indeed, in the fastq there is no information regarding the strand, so the mapper can just align the read and mention if it has to reverse complement the read to map it (strand -). Looking at this bam differently mapped in a genome browser will show you exactly the same results. 

## The XS flag 
Depending on the mapper used and the parameters, some flags will be set differently. Notably, there is the `XS` flag that is suppose to correspond to "the strand from which emanated the RNA". If the mapper is aware of the real GTF (i.e. tophat), it cleverly look into the GTF to find out what is the correct direction of the gene and set the `XS` flag accordingly. 

If the mapper does not know about the GTF (tophat de novo, hisat etc...) or if there are no feature in the GTF at this locus, then depending on the parameters it will set the `XS` flag differently. It will be the same as the strand to which the read mapped if in mode fr-secondstrand, otherwise it will be the opposite strand to which the read mapped. 

## Stranded does matter
It could appear like the strand does not matter but hopefully it's not the case. For instance, if all the reads from a locus come from one strand, then in the alignment they will all map on the same strand. Knowing this, the read summarization can be done only counting strand specifically. As long as the counter is looking only at which strand the read aligned, then this step will be independent of the mapping parameters though. 

However,  when assembling transcriptome using stringtie or cufflinks, the `XS` flag is used in order to infer the RNA direction. So for post-processing of the BAM, the way the bam was aligned can matter and will bring to completely wrong results if the data were not mapped correctly. 
