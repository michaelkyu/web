---
layout: page
title: variability-profile-txt [artifact]
categories: [anvio]
comments: false
image:
  featurerelative: ../../../images/header.png
  display: true
---


{% include _toc.html %}


<img src="../../images/icons/TXT.png" alt="TXT" style="width:100px; border:none" />

A TXT-type anvi'o artifact. This artifact can be generated, used, and/or exported **by anvi'o**. It can also be provided **by the user** for anvi'o to import into its databases, process, and/or use.

Back to the **[main page](../../)** of anvi'o programs and artifacts.

## Provided by


<p style="text-align: left" markdown="1"><span class="artifact-p">[anvi-gen-variability-profile](../../programs/anvi-gen-variability-profile)</span></p>


## Required or used by


<p style="text-align: left" markdown="1"><span class="artifact-r">[anvi-display-structure](../../programs/anvi-display-structure)</span> <span class="artifact-r">[anvi-gen-fixation-index-matrix](../../programs/anvi-gen-fixation-index-matrix)</span> <span class="artifact-r">[anvi-script-calculate-pn-ps-ratio](../../programs/anvi-script-calculate-pn-ps-ratio)</span> <span class="artifact-r">[anvi-script-snvs-to-interactive](../../programs/anvi-script-snvs-to-interactive)</span> <span class="artifact-r">[anvi-script-variability-to-vcf](../../programs/anvi-script-variability-to-vcf)</span></p>


## Description


This artifact contains various information about the SNVs, SCVs, and SAAVs across a <span class="artifact-n">[profile-db](/software/anvio/help/7/artifacts/profile-db)</span> that is thoroughly described [on this blogpost](http://merenlab.org/2015/07/20/analyzing-variability/#the-output-matrix).  

This is generated by <span class="artifact-n">[anvi-gen-variability-profile](/software/anvio/help/7/programs/anvi-gen-variability-profile)</span>, which is also described in [that blogpost](http://merenlab.org/2015/07/20/analyzing-variability/#the-anvio-way).  

{:.notice}
Unsure what SNV, SCV, and SAAVs are or looking for a refresher? You can find that information [on the same blogpost](http://merenlab.org/2015/07/20/analyzing-variability/#an-intro-to-single-nucleotidecodonamino-acid-variation).  

In summary, [go to the blogpost](http://merenlab.org/2015/07/20/analyzing-variability/). Because the blogpost preceded this document by 5 years, most of the pertinent information that should be in here is actually over there. One day we will remedy this situation. Until then, this document serves as a quick reference for content more verbosely explained in the blog post.


<span class="artifact-n">[variability-profile-txt](/software/anvio/help/7/artifacts/variability-profile-txt)</span> is the output matrix for your SNVs, SCVs, or SAAVs. What you do with your <span class="artifact-n">[variability-profile-txt](/software/anvio/help/7/artifacts/variability-profile-txt)</span> is entirely up to your discretion. We maintain the stance that this output should be as raw as possible, so that you can analyze it how you please. Attached to each SNV, SCV, and SAAV is a plethora of annotated information.


### What kinds of information?  

#### SNVs 

For each of your SNVs, this matrix include their position in the contig and gene, sample, coverage data, the A, C, G, and T counts, the reference and consensus nucleotides, entropy value, and more.  

#### SCVs 

This information will only appear if you requested it when running your earlier analysis. To do this, use the flag `--profile-SCVs` when you run <span class="artifact-n">[anvi-profile](/software/anvio/help/7/programs/anvi-profile)</span>. Then, when running <span class="artifact-n">[anvi-gen-variability-profile](/software/anvio/help/7/programs/anvi-gen-variability-profile)</span> use the flag `--engine CDN`.  

For each SCVs, this matrix details the position, sample, coverage data, count for each of the 64 codons (AAA, AAC, ..., TTG, TTT), entropy, synonymity, etc.  

#### SAAVs 

Like the information about SCVs, this information will only appear if you requested it when running your earlier analysis. To do this, use the flag `--profile-SCVs` when you run <span class="artifact-n">[anvi-profile](/software/anvio/help/7/programs/anvi-profile)</span> or <span class="artifact-n">[anvi-merge](/software/anvio/help/7/programs/anvi-merge)</span>. Then, when running <span class="artifact-n">[anvi-gen-variability-profile](/software/anvio/help/7/programs/anvi-gen-variability-profile)</span> use the flag `--engine AA`.  

For each SCVs, this matrix details the position, sample, coverage data, count for each of the 20 amino acids (as well as the stop codon), entropy, BLOSUM62, etc.  

#### Structural information 

If you provided <span class="artifact-n">[anvi-gen-variability-profile](/software/anvio/help/7/programs/anvi-gen-variability-profile)</span> with a <span class="artifact-n">[structure-db](/software/anvio/help/7/artifacts/structure-db)</span>, then you'll also have some additional columns to your matrices. These include structural annotations, the residue's solvent accessibility, information about bond angles, and a list of residues that are in physical contact with the residue you're looking at. 


For more information on any of this, check out [this page](http://merenlab.org/2015/07/20/analyzing-variability/#the-output-matrix), where every column in these matrices is not only listed, but explained.


#### Additional amino acid and nucleotide data 

If you provided <span class="artifact-n">[anvi-gen-variability-profile](/software/anvio/help/7/programs/anvi-gen-variability-profile)</span> with the flag `--include-additional-data` and you have any <span class="artifact-n">[misc-data-amino-acids](/software/anvio/help/7/artifacts/misc-data-amino-acids)</span> data stored in your <span class="artifact-n">[contigs-db](/software/anvio/help/7/artifacts/contigs-db)</span>, that data will added as additional columns to the matrix.


{:.notice}
This is currently only implemented for `--engine AA` and `--engine CDN`. `--include-additional-data` will not currently append <span class="artifact-n">[misc-data-nucleotides](/software/anvio/help/7/artifacts/misc-data-nucleotides)</span> data to your matrix output when `--engine NT` is used.




{:.notice}
Edit [this file](https://github.com/merenlab/anvio/tree/master/anvio/docs/artifacts/variability-profile-txt.md) to update this information.

