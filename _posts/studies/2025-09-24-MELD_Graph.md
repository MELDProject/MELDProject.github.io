---
layout: post
title:  MELD Graph based FCD lesion segmentation
categories: studies
excerpt: Graph based FCD lesion segmentation 
tags: []
image:
  feature:
link:
date: 2025-09-27
modified:
share: true
---

### Graph based FCD lesion segmentation - a MELD study


Focal Cortical Dysplasia (FCD) are small brain lesions that occurs during brain development and that can cause epilepsy seizure. Finding the lesion on MRI scan and removing it with surgery can cure the patient from epilepsy seizure. However, FCDs can be subtle and difficult to see with the human eye and up to half of these lesions are missed by radiologists. 

Previously, our group has developped [MELD FCD](/_posts/studies/2022-08-06-MELD_FCD.md), a AI model trained on a large dataset of MRI scans from epilepsy patients and controls and capable of detecting 67% of FCD lesions. However, as well as predicting the lesion, the model also predicted on average 2 false-positive cluster per subjects, meaning that radiologists had to review few predicted clusters in order to find the correct lesion. This high number of false-positive prediction is a common challenge faced by many AI models that do image detection. 

In work [published in JAMA](https://jamanetwork.com/journals/jamaneurology/article-abstract/2830410) in 2025, the Multi-centre Epilepsy Lesion Detection (MELD) Project details the development of a new AI Graph based model capable of detecting FCD lesions with bette accuracy.

For that, we used a graph neural network (MELD Graph) trained to identify FCD on surface-based features. Compare to the previous FCD model which used a multilayer perceptron (MLP) model trained on each individual point of the brain surface, the graph neural network offers the advantage of taking in consideration neighbourgh points, and therefore having a context of the surrounding tissues in the prediction of a single point. 

To enable comparison with our previous MLP model, MELD Graph was trained and evaluated on the same multicentre dataset of 703 epilepsy patients detailed in the [publication](https://jamanetwork.com/journals/jamaneurology/article-abstract/2830410). 


<figure>
<img src="/images/MELD_Graph_overview.jpg"
alt="MELD Graph processing pipeline.">
<figcaption>MELD Graph processing pipeline.</figcaption>
</figure>

### Results ####

In the test dataset (n=260 patients), MELD Graph accuracy was 67% (70% sensitivity; 60% specificity), compared with 39% (67% sensitivity; 54% specificity) using the previous MELD FCD model. On average, MELD Graph predicted no false-positive prediction. As well as producing an interpretable reports characterize the lesion location, size, and salient features, MELD Graph also output a confidence score associated with the prediction.

Below are examples of the predictions with MELD Graph and MELD MLP, and the reduction of number of false-positive predictions using MELD Graph:

<figure>
<img src="/images/MELD_Graph_predictions.jpg"
alt="Example of ">
<figcaption> Reduction in false positive clusters with MELD Graph compared to MELD MLP. (A) Example classifier predictions for four patients using MELD Graph and the baseline multilayer perceptron (MELD MLP). Black line = manual lesion mask. Red = classifier predictions. (B) Box-and-whisker plot showing the mean positive predictive value (PPV) and the confidence interval (CI) in the test patients detected by both MELD MLP and MELD Graph models (N=161). (C) Box-and-whisker plot showing median, interquartile range and outlier numbers of false positive (FPs) clusters predicted on patients and controls in the test dataset using MELD Graph compared to MELD MLP. Gray lines connect identical subjects between the models.</figcaption>
</figure>

### Running the pipeline on new patients ###

Our pipeline outputs individual patient reports with the location of predicted lesions, along with their imaging features and relative saliency to the classifier and a confidence score. The pipeline also maps the predicted lesions back to the native T1 so that they can be reviewed by a radiologist. 

<figure>
<img src="/images/MELD_Graph_patient_report.jpg"
alt="Individual patient reports.">
<figcaption>Examples of interpretable patient reports. MELD Graph outputs for two patients from the independent test cohort. Patient 1 is an example of an MRI-positive FCD detected by MELD Graph with a high confidence prediction (93%). Patient 2 has a FCD that was not identified by 5
expert radiologists but detected by MELD Graph with low confidence (7%). (A) Classifier predictions (red) and 20% most salient vertices (orange) visualized on brain surfaces of the lesional hemisphere and on the T1 volume. (B) Z-scored mean feature values within 20% most salient vertices of predicted lesions. Color represents saliency scores. Features driving the classifier’s prediction are positive (pink). Features inconsistent with MELD Graph prediction are negative (green). (C) T1 and FLAIR coronal sections with a red box indicating the lesional cortex..</figcaption>

</figure>

**MELD Graph worldwide use**

MELD Graph is open-source and can be downloaded from [Github](https://github.com/MELDProject/meld_graph). It is available on multiple OS systems (Mac, Windows, Linux).

In December 2025 (10 months after publication), MELD Graph is reported to have being used in over 100 hospitals worldwide as a research tool. 

Our work has been featured in the news at [BBC](https://www.bbc.co.uk/news/articles/cvg1xd7l5pvo)


