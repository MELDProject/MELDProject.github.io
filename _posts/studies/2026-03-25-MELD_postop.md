---
layout: post
title:  MELD PostOp
categories: studies
excerpt: Automated Segmentation of Post-Surgical Resection Cavities on MRI 
tags: []
image:
  feature:
link:
date: 2026-03-25
author: jieun_seo
modified:
share: true
---

### Automated Segmentation of Post-Surgical Resection Cavities on MRI - a MELD study 

1 in 5 epilepsy patients experience seizures caused by structural abnormality in the brain. For these patients, resection surgery to remove the epileptogenic zone is one of the best chances of cure, and complete resection of the epileptogenic zone is important for achieving seizure freedom. 
Quantitative assessment of resection completeness requires: 
- accurate delineation of the postoperative resection cavity, and 
- comparison with the preoperative lesion 

However, existing delineation approaches are often time-consuming, labour-intensive, and difficult to generalise across datasets and imaging protocols. 

To address this challenge, we developed MELD-PosTOp, a deep learning tool that automatically segments resection caivites directly from postoperative 3D T1-weighted MRI scans, without requiring additional preprocessing or additional modalities. 

The model was trained using 965 postoperative scans with annotations, sourced from the MELD Focal Epilepsies dataset and the open-source EPISURG dataset


<figure>
<img src="/images/MELD_postop_overview.jpg"
alt="MELD Graph processing pipeline.">
<figcaption>MELD-PostOp overview. The Prototype Cohort (n=285) was used to train the prototype model. The prototype model was applied to an inference cohort. All predictions underwent visual quality control (QC). Failed cases were manually refined using nnInteractive and ITK-SNAP. The masks that passed QC and manually edited masks were combined with the Prototype Cohort to form the MELD-PostOp Train Cohort (n=965), which was used to train the final MELD-PostOp model. Model performance was evaluated on the Stratified Test Cohort and Independent Test Cohort. MELD-PostOp performance was compared with the Epic-CHOP and ResectVol. 
</figcaption>
</figure>

### Results ####

MELD-PostOp demonstrates fast, reproducible, and generalisable segmentation performance across large and heterogeneous imaging cohorts. MELD-PostOp detected 135/137 resection cavities (98.5%), and 128 segmentations achieved meaningful overlap with ground truth segmentation (Dice > 0.5). No statistically significant performance differences were shown across: sex, age (adult vs paediatric), pathology (HS vs non-HS), surgical lobe (temporal vs extra-temporal), surgical side, MRI field strength, and image isotropy. Runtime was 17 seconds per image, compared to >10 minutes for other tools.


<figure>
<img src="/images/MELD_postop_results.jpg"
alt="MELD-PostOp results">
<figcaption> [A] Raw postoperative T1w MRI scans, ground truth manual resection masks, and automated segmentation from Epic-CHOP, ResectVol and MELD-PostOp models. The number displayed beneath each predicted mask indicates the Dice Similarity Coefficient (DSC) and the 95th percentile Hausdorff distance (HD95) relative to the manual mask. [B, C] Box and scatter plots of DSCs (B) and HD95 (C) across models in the combined test cohorts (n=137). MELD-PostOp achieved a significantly higher median DSC and HD95 than Epic-CHOP and ResectVol (p < 0.001).</figcaption>
</figure>

### Installation & Usage ###
Instructions for installation and usage can be found here: [MELD-PostOp Github Page](https://github.com/MELDProject/MELD-PostOp)

Pre-trained model weights can be downloaded here: [MELD-PostOp Figshare Page](https://figshare.com/s/c5a3d4a5604b229eeb5f)

### Preprint ###
For more details, preprint is available here: [MELD-PostOp MedRxiv](https://www.medrxiv.org/content/10.64898/2026.02.26.26347093v1)



