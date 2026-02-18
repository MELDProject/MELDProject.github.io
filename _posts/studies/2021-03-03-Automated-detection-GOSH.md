---
layout: post
title:  Surface-based automated FCD detection at GOSH
categories: studies
excerpt:
tags: []
image:
  feature:
link:
date: 2021-03-03
modified:
author: sophie_konrad
share: true
---

### Automated Detection of Focal Cortical Dysplasias at GOSH using a surface-based approach

Focal cortical dysplasia (FCD) is a congenital abnormality of cortical development and a leading cause of surgically remediable drug resistant epilepsy. MRI has played a major role in the evaluation of patients; yet, significant proportions of lesions remain undetected by conventional image analysis. Machine learning offers a powerful framework to develop automated and individualised clinical tools that may improve the detection of lesions and prediction of clinically relevant outcome.

In work [published in Neuroimage: Clinical](http://www.sciencedirect.com/science/article/pii/S2213158216302674?via%3Dihub) in 2017, Adler, Wagstyl et al., developed a classifier using surface-based features to identify focal abnormalities of cortical development in a paediatric cohort from Great Ormond Street Hospital. Focal cortical dysplasias in this paediatric cohort were correctly identified in 73% of the children.

<figure>
<img src="/images/Example_classifier_results.png"
alt="FCD examples">
<figcaption>Examples of cortical area detected by the neural network classifier in 5 patients with a radiological diagnosis of FCD. First column: T1-weighted images. Second column: FLAIR images. White circle on T1 and FLAIR images indicates lesion location. Third column: Neural network classifier output (yellow) and manual lesion mask (light blue) viewed on pial surface, for large lesions, or inflated surface, for small lesions buried in sulci.</figcaption>
</figure>

Further studies have since validated validated this method:
[Jin et al., 2018, in Epilepsia,](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5934310/)
[Mo et al., 2018, Frontiers in Neuroscience,](https://www.frontiersin.org/articles/10.3389/fnins.2018.01008/full)
and [Wagstyl, Adler et al., Epilepsia](https://onlinelibrary.wiley.com/doi/full/10.1111/epi.16574)


