---
layout: default
title:  "EPD conf"
categories: notes
description: "Some notes about the conf"
---

# EPD conference

## First day
### Artemis Harzigeorgiou - Promoter prediction evolution thorugh the decades
* How to detect promoters of miRNA. Website about miRNA: DIANA


### Sridhar Hannenhalli - REmote control of gene expression
* Where to look for regulary elements
* Look at regions that are really conserved (control has to be conserved)
* Only fraction (50%) of binding sites in droso are conserved
* Look at the histone code for enhancers
* Ernst et al nature 2011  - paper with combination of marks
* Nat comm integrative models of eQTL
* Genes are epxressed with methzlated promoter, those usually have CpG island upstream (distal CpG
    island 50KB, not working as enhancers, alternative prom - from question could be polycomb genes)


### Denis Thieffry - Qualitative dynamical modelling of euracryotic transcriptional newtorks
* Gene network based on ChIPseq of TF and valideated through in-vitro/vivo stuff in B-cell to Macrophate reprogramming
* TF ChIP-seq -> gene netwrok -> micorarrays to see if it works

### Gary Stormo - Modellling the speciificity of transcription factors
* SPEC-seq measure of binding afffiniy to a dna site vaires with sequence  (run gel then sequecn)
* PFM matrices and Energy Logo, some math -> logo depending on the concentration
* TF combination based on the motif 
* COOP-seq > library of sequences, add protein, run gel > get the DNA bound by either one or both or
    none, ratios of those can 
* Paper in review

### Bart Deplancke
* PBM > microarrays with probes of different sequence, infer the binding of a protein 
* HT-selex > perform bad
* Most TF are not characterized, dimer TF is even worse
* SMiLE-seq > microfluidics flow layer (mitomi like), detection chamber.  Define TF binding affinity
* TF tagged GFP, tagged fluo DNA sequence lib. Flow DNA in the chamber then wash, only bound stay. 
* Only need 1000 reads, you can spike  it easy

* Selected ZNF collab with Didier
* 9 of 19 got motif
* Alexandra Kalantzi is looking at ZNF: predict which zinc-fingers bind

### Tugce Bilgin Sonay - Tandem repeats in promoters confer gene expression divergence
* Tandem repeats mutate a lot
* Tandem repeats affect phenotype, promote adaptation etc... (like TE in the end)
* Form secondary structure, bring methylation marks
* Genes with tandem repeats in the promoter have more expression divergence
* Bilgin Sonay et al. Genome research 2015

* Idea: Look at gene divergence relative to TE distance


### Paul Gaghnic - A pattern approach for promoter research
* From sequence of promoter make patterns (enigma machine algo)
* Idea: Could try to run the program on TE

### Jake Yeung - Tissue-wide analysis reeals distinct roles of promoters underlytin rhythmic gene expression
* Sacrifice mice over 24h and sequence some tissues, KO vs WT of bmal KO (clock not functioning)
* Find genes that depend on the clock and some on the system

### Mahmoud Ibrahim - Promoter dynamics during directed differentiation of motor neurons
* ES > Motoneuron using NIL in 48H
* Bivalent promoter: H3K27ac + H3K27me3 switch
* Co-clustering of multiple datasets overtime: feed data in the model 
* Bayesian network 

### Dominik Hartl - Dissecting sequence determinants of CpG island promoter activiy
*  High CpG density reduce methylation 
*  and increase transcription

### Sarah Natalia Mapelli - Promoter-proximal transcripts: a genome-wide prediction and functional validation study
* longNonCodingRNA 
* Highly transcribed but degarded 
* Transcribed in both sense
* GRO-seq to catch stuff degraded fast
* paRNA promoter associated noncoding RNA
* Difficult to see correlations as for TE, heterogeniousA
* Nuclear Poly A depleted RNA-seq 
* Gene is going up and down when you remove the paRNA
 
### Maroun Bou Sleiman - The alternative splicing landscape of the drosophila gut upon enteric infection
* Upon infection, there is more reads on the intron than on the genes
* Retrained introns are enriched for some TF like LARK
* Changing the levle of lark affects the intron retention

- - - 

## Second day

### Alexander Kei - TRANSFAC and beyond
* Program to recognise promoter, use motif around start transcription
* TRRD - transcription regulatory region database
* 6500 PWMs 
* Sites are not really well defined, PWM gives a lot of posible binding site, also sites needs sometime multiple factor for them to work
* Evolution of binding sites goes along with evolution of TF (paiting metaphore)
* For information theory, the more message look like white noise, the more message you can encode inside

### Martin Vingron  -Co-localization networks on promoters
* Window > look if 2 TF are in the window (log-odd score)
* Prediction of co-localization compares to real interaction of the 2 guys
* Rank target genes of TF and test list for the 2 list > if many common genes, co-loc
* Doing this by tissues makes it possible to get a tissue by tissue network
* We need to look ad chromatin conformation to know which TF is active
* Histone marks correlate with promoters but only to some
* Inverse of the Cov matrix brings to linear relationship network and remove the problem of all is connected

### Uwe Ohler - Pervasive transcription and the diversity of eukaryotic
* Divergence transcription happend often at promoters
* 5' gro-seq: get fresh/nascent transcript (before degraded)
* Biderectional genes the histone marks also look bimodal when centering
* Total RNA: around TSS, it goes to forward
* GroCap: saround TSS, some TSS goes to forward only, some reverse only, some are bivalent
* Biderectional transcription happens different in different species. Yeast always have Biderectional

### Boris Lenhard - Promoter classes and promoter codes: looking beyond motifs
* Sharp peak (single peak) promoters and broad promoters
* Multiple CpGi and few CpGi promoter
* Special promoters for oocyte and other development stages
* Promoter can be interpreted in different ways in different tissues

### Tammy Juven-Gershon - The core promoter: at the heart of gene expression

* TF have core elements (like small domains) - like TATA etc...
* Element: detect core promoter elements
* Enhancer specific to development and housekeeping
* Idea: look at the core elements and look if they are in the ERE
* Lagha et al 2013 Cell - look for the skymap plot


### Roberto Mantovai - The CCAAT/NF-Y duo: paternerships in promoters and beyond

* LTR are bound by NF-Y (LTR12 in particular)
* ZNF143 could be target of LTR12 then, cause it's associated to NF-Y

### Erik van Nimwegen - The role o expression noise in the evolution of gene regulation: lessons from evolved synthetic promoters
* ISMARA sib - predict TF in the system you upload
* CRUNCH - analysis chipseq fastq to peaks 
* DWT are like PWM but never overfit when correlation in the column of the PWM. (Bayesian)
* Take random promoter (random dna seq), clone it in front of GFP, select fluorescent. In 2 generation, the promoter you get is better than the one in e.coli
* Less noise in the synthetic promoters
* Noisy genes have more regulary inputs
* Coupling a gene to a regulator makes it easy to expressed more or less a gene
* In this process, the noise is propagaged
* Best regulator is either very high correlation with what we want, or very very noisy (Wolf et al eLife 2015)

### Martin Kuiper - Taking care of transcription factors - building a knowledge commons for gene regulatory network analysis
* There is a lot of TF that are wrongly anotated in the db, method for curating these lists
* theGRECO.org
* TFcheckpoint.org

### Valentina Boeva - Discovery of core regulatory circuiteies in neuroblastoma and identification of disctinct neuroblastoma identity types
* Find super enhancer using chipseq H3K27ac 
* CRCs set of TF that autoregulate themselves and determine cell identity
* Chip-seq of 20 neuroblastoma H3K27ac + RNA-seq
* PCA analysis on the super enhancer signals
* Look at Saint-Andre et al GEnome research 2016

### Nicolas Mermod - Bioinformatics modeling and experimental characterization of epigenetic regulatory elements
* S/MAR structure DNA in nucleus
* MAR makes expression more consistent
* PollII is at MAR, paused. Could be a reserve for polII to be close to promoters
* Stabilise transcription
