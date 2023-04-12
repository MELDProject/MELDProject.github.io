---
layout: post
title:  Atlases of FCDs
categories: studies
excerpt: Atlas of lesion locations and post-surgical seizure freedom in FCD
tags: []
image:
  feature:
link:
date: 2022-04-04
modified:
share: true
---
### Planning SEEG using automated lesion detection

One‐third of children with epilepsy are medication‐resistant. In children with a focal seizure onset zone (SOZ), stereoelectroencephalography (sEEG) can be used to delineate the SOZ in complex patients. This involves electrodes being implanted into the brain to record brain activity. Currently, electrode placement is a clinical decision but planning SEEG can be challenging and time-consuming. In half of the patients selected for sEEG, the MRI scan looks normal which makes planning where to implant electrodes difficult. 

In this study [published in Epilepsia](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC8432161/) in 2020 we aimed to evaluate the feasibility and potential benefits of using deep learning on structural magnetic resonance imaging (MRI) to plan implantation of electrodes for stereoelectroencephalography (sEEG) in pediatric patients with drug-resistant epilepsy. 


The study trained a neural network classifier to identify lesions in MRI data from 34 patients with known cortical dysplasias and 20 healthy controls. 

<figure>
<img src="/images/seeg_method.jpeg"
alt="Framework for automated lesion detection and colocalization with sEEG electrodes.">
<figcaption> Framework for automated lesion detection and colocalization with sEEG electrodes. A, Surface‐based feature extraction, lesion labeling, and training of neural network classifier on MRI‐positive patient cohort. B, Testing of classifier on presurgical MRI of patients undergoing sEEG.</figcaption>
</figure>

The classifier was able to detect lesions with a sensitivity of 74% in patients with known lesions and had a specificity of 100% in healthy controls. In 34 patients who underwent SEEG, we then assessed whether the  seizure onset zone (SOZ) overlapped with the classifier output. 

<figure>
<img src="/images/seeg_case.png"
alt="Example case report where there is concordance between ictal contacts and classifier output">
<figcaption>Example case report where there is concordance between ictal contacts and classifier output.  The case includes a brief clinical overview (left upper), a plot of distance of the stereoelectroencephalography (sEEG) contacts from the predicted lesion (right upper), visualization of the electrode positioning (ictal contacts = red, interictal = yellow, other = black) with automated clusters (red = top cluster, yellow = other clusters, lower panels), and a coronal section of the FLAIR MRI scan with lesion indicated by red arrow. </figcaption>
</figure>

*** We found that in 62% of the patients with focal SOZs and 86% of histopathologically confirmed FCDs the results were concordant! ****

This suggested that incorporating deep-learning-based MRI analysis could be a useful tool for planning sEEG implantations. 

One **limitation** of the study was its retrospective nature, which meant that further research was needed to determine the effectiveness of the automated method in a prospective study. 

**However, the study provided a framework for using automated lesion detection to plan optimal electrode trajectories and the results supported the prospective evaluation of this approach in future studies. This work led the MAST clinical trial!**
