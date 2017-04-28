---
layout: default
title:  "StringTie"
categories: bioinfo
description: "Some learnings from Stringtie's paper "
---

# Stringtie
* First, stringtie (ST) makes cluster of reads
* ST builds a flow network of the reads to infer transcripts
* It maximizes the network flow to estimate the abundance and expression
* Finally report what asked

### About the network

* It uses the splicing to build the node of the network
* The number of spliced reads determine the capacity of the edge
* Correct for bias of the 3prime and 5prime end difference in mapping
* Smooth the coverage along the exons and through introns to make the computation better

### Compared to cufflinks
Very similar results, cufflinks uses a EM algo to compute the coverage. Claim stringtie is more
sensitive.

![Workflow]({{ site.baseurl }}/assets/2017_stringtie/workflow.png)

![Example of network]({{ site.baseurl }}/assets/2017_stringtie/network.png)

