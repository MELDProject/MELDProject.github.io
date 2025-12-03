---
layout: post
title:  MELD Graph based FCD lesion segmentation
categories: studies
excerpt: Graph based FCD lesion segmentation 
tags: []
image:
  feature:
link:
date: 2025-12-03
by: Mathilde Ripart
modified:
share: true
---

### Graph based FCD lesion segmentation - a MELD study

Focal Cortical Dysplasia (FCD) are small abnormalities occuring during brain development that can cause epileptic seizures. Identifying these lesions on MRI and removing them surgically can often cure epilepsy. However, FCDs are frequently subtle and difficult to detect, and up to half are missed by radiologists. 

Previously, our group developed [MELD FCD](/_posts/studies/2022-08-06-MELD_FCD.md) an AI model trained on a large, multicentre MRI dataset of epilepsy patients and controls. The model can detect 67% of FCD lesions, but typically produced around two false-positive clusters per subject. This is a common challenge in lesion-detection AI models, which increases the radiologist’s workload as they need to review more putative lesions.

In work published in [published in JAMA Neurology in 2025](https://jamanetwork.com/journals/jamaneurology/article-abstract/2830410), the Multi-centre Epilepsy Lesion Detection (MELD) Project introduced a new graph-based AI model with substantially improved accuracy.

To build this model (MELD Graph), we used a graph neural network trained on surface-based cortical features. Unlike the previous multilayer perceptron (MLP) approach, which analysed each cortical vertex independently, the graph neural network take into consideration neighbourhood information, makink the model more aware about the surrounding tissue.

To allow direct comparison, MELD Graph was trained and evaluated on the same multicentre dataset of 703 patients described in the original publication.

<figure>
<img src="/images/MELD_Graph_overview.jpg"
alt="MELD Graph processing pipeline.">
<figcaption>MELD Graph processing pipeline.</figcaption>
</figure>

### Results ####

In the test dataset (n=260 patients), MELD Graph achieved 67% accuracy (70% sensitivity; 60% specificity), compared with 39% accuracy (67% sensitivity; 54% specificity) for the earlier MELD MLP model. Importantly, MELD Graph produced zero false-positive predictions on average. Along with the predicted lesion, MELD Graph also generates interpretable reports describing lesion location, size, salient features, and a confidence score.

Below are examples showing MELD Graph vs. MELD MLP predictions and the reduction in false positives:

<figure>
<img src="/images/MELD_Graph_predictions.jpg"
alt="Example of ">
<figcaption> Reduction in false positive clusters with MELD Graph compared to MELD MLP. (A) Example classifier predictions for four patients using MELD Graph and the baseline multilayer perceptron (MELD MLP). Black line = manual lesion mask. Red = classifier predictions. (B) Box-and-whisker plot showing the mean positive predictive value (PPV) and the confidence interval (CI) in the test patients detected by both MELD MLP and MELD Graph models (N=161). (C) Box-and-whisker plot showing median, interquartile range and outlier numbers of false positive (FPs) clusters predicted on patients and controls in the test dataset using MELD Graph compared to MELD MLP. Gray lines connect identical subjects between the models.</figcaption>
</figure>

### Running the pipeline on new patients ###

The pipeline outputs an individualised patient report including predicted lesion location, imaging features, saliency values, and a confidence score. Predicted lesions are also mapped back to the native T1 image for radiological review.

<figure>
<img src="/images/MELD_Graph_patient_report.jpg"
alt="Individual patient reports.">
<figcaption>Examples of interpretable patient reports. MELD Graph outputs for two patients from the independent test cohort. Patient 1 is an example of an MRI-positive FCD detected by MELD Graph with a high confidence prediction (93%). Patient 2 has a FCD that was not identified by 5
expert radiologists but detected by MELD Graph with low confidence (7%). (A) Classifier predictions (red) and 20% most salient vertices (orange) visualized on brain surfaces of the lesional hemisphere and on the T1 volume. (B) Z-scored mean feature values within 20% most salient vertices of predicted lesions. Color represents saliency scores. Features driving the classifier’s prediction are positive (pink). Features inconsistent with MELD Graph prediction are negative (green). (C) T1 and FLAIR coronal sections with a red box indicating the lesional cortex..</figcaption>

</figure>

**MELD Graph worldwide use**

MELD Graph is open-source and available on macOS, Windows, and Linux via [Github](https://github.com/MELDProject/meld_graph). Tutorial videos to help install and uses the tool are available on our [Youtube channel](https://www.youtube.com/@MELDproject)

As of December 2025 (10 months after publication), it is reported to be in use in more than 100 hospitals worldwide as a research tool. Our work has also been featured in the news, including coverage by the [BBC](https://www.bbc.co.uk/news/articles/cvg1xd7l5pvo) and [Reuters](https://www.dailymotion.com/video/x9fwx0u). 

*Written with the assistance of ChatGPT*


