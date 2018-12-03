---
layout: post
title: "The face-to-face meeting at AES"
categories: blog
excerpt: Minutes
tags: []
image:
  feature:
link:
date: 2018-12-02
modified:
share: true
author: sophie_adler
---

# The face-to-face meeting at AES #


Hello! :wave: It was an absolute pleasure to be able to meet collaborators representing 9 of our 23 sites at AES 2018.

#### Date: ####

2nd December 2018

#### Present: ####

Sophie Adler-Wagstyl (SAW; Great Ormond Street Institute of Child Health, UK), Konrad Adler-Wagstyl (KAW; University of Cambridge, UK), Z. Irene Wang (ZIW; Cleveland Clinic, USA), Estefania Conde Blanco (ECB; Hospital Clinic of Barcelona, Spain),  Fernando Cendes (FC; UNICAMP, Brazil), Kai Zhang (KZ; Beijing Tiantan Hospital, China), Reeta Kalviainen (RK; University of Eastern Finland, Finland), Jonathan O'Muircheartaigh (JOM; Kings College London, UK), John Duncan (JD; University College London, UK), Gavin Winston (GW; University College London, UK), Heath Pardoe (HP; New York University, USA), 


<figure>
<img src="/images/AES_meeting.jpeg"
alt="AES Meeting">
</figure>


#### Presentation ####

The meeting began with introductions by all attendees and a short presentation covering:
* Introduction to the challenge of identifying FCDs on MRI
* Overview of the approach we are using to automatically identify FCDs - this included explaining the steps involved in the protocols:
        * Freesurfer reconstructions
        * Calculation of a variety of surface-based features including cortical thickness, grey-white matter intensity contract, sulcal depth, curvature, intrinsic curvature, FLAIR (at a number of different cortical and subcortical depths)
        * Registration to a template space 
        * Normalisation procedures
        * Lesion mapping
        * Generation of the matrix of anonymised features (stored as hdf5 files) - this is what is shared! 
* Results from the initial work done at Great Ormond Street Hospital on a paediatric cohort
* Results from replication studies done at the Cleveland Clinic and the National Hospital for Neurology and Neurosurgery
* Demonstration of the importance of sample size for classifier performance and motivation behind establishing the MELD Project
* Map of the locations of the current 23 sites with an estimated over 500 patients
* Timeline of the MELD Project


<figure>
<img src="/images/data_collection.png"
alt="Timeline of MELD Project">
</figure>


* Overview of the proposed primary analyses:    
        * Lesion characterisation of total cohort
        * Lesion detection using a multilayer perceptron 
        * Analysis of lesion topography and relation to genetics / cytoarchitecture 
* Other analyses / work:
        * Classifier development - network saliency and graph attention architectures

#### Discussion ####

Throughout the presentation and after there was a lively discussion. Here is an overview of what was discussed:

:arrow_forward:  HP : Does motion artefact affect false positives?
* Yes! Motion can cause false positives or affect the features of lesional cortex and make detection more challenging. 
* We are hoping that with this large cohort the classifier will become more robust and better trained to handle motion artefact. However, the QC protocol (protocol 3) will also allow us to experiment with including / excluding poor quality data and assessing the effect on sensitivity, specificity, false positives.

:arrow_forward: ZIW : What do we include as training data on the lesional hemisphere outside of the lesion label? Could you be including data that is actually lesional? 
* In the previous studies only the contralateral hemisphere was used as training examples for non-lesional cortex. However we dicussed the possibility to include a boundary zone of uncertainty around the lesion labels. This would allow us to throw away less of the non-lesional data.

:arrow_forward: This led to a discussion on class imbalance - balancing quantities on lesional and non-lesional training examples.
* There are different approaches to dealing with class-imbalance including: increasing the weighting of lesional data so that the classifier learns more from these examples, oversampling the lesional data or undersampling the non-lesional data

:arrow_forward: JD: Will this be abnormality detector or descriptive of subtype?
* There is the ability to do both with this unique dataset. We will be able to train classifiers to detect lesions (regardless of FCD histopathological subtype) and to train classifiers to subtype into histopathological subtypes. 
* It is important to note that most of our data is FCD type IIa and IIb

:arrow_forward: ZIW: Emphasised that they had 3 sites in their replication study highlighting that the classifier can handle heterogeneity in terms of scanners / sequences 
* There was a discussion around how increasing sample size can help deal with heterogeneity (in age, lesion types, lesion locations, scanners, sequences etc.)

:arrow_forward: JD: Raised problem that only 20-30% of MRI negative are FCD
* ZIW: 50% of MRI negative at Cleveland were FCD
* We had a discussion around different types of MRI negative patients (those that are MRI negative, those MRI negative but histopathologically confirmed FCD and those that were once reported MRI negative but a lesion has since been seen). 
* We discussed how we can aim for high sensitivity in MRI positive patients, those that are MRI negative but histopathologically confirmed FCD and those that were once reported MRI negative. However we would expect a lower yield in prospective MRI negative patients as only a low proportion of these patients will actually have a FCD as the pathology.

:arrow_forward: JD: Is there a measure of quality control?
* Discussion around QC protocol and possible exclusion of poor data in classifier training dataset

:arrow_forward: JOM: Suggested normalisation of data according to sequences
* Discussion about how current protocols normalise by site's controls in sites that have controls and by a template control created by us in those that do not have controls. However, we will also have a large normative dataset created by the MELD Project which will allow us to create age specific templates. 

:arrow_forward: ZIW: Do we have access to our data? What about other sites data?
* Yes all your sites data is in the hdf5 files and we can provide scripts helping you manipulate this file format so that centres can explore there own data. 
* In terms of other sites data, the MOU details how to apply for the total dataset. A site in the MELD consortium or external can write a project proposal and all sites have a period of time to object to their data being shared. If there are no objections, then the total dataset is shared.
* Discussion around challenges of releasing total anonymised dataset and agreement to have discussions about this possibility in the future.

:arrow_forward: Discussion around topography of lesions (the current lesion locations of the first 250 patients).

<figure>
<img src="/images/all_sites_lesion_locations.png"
alt="Lesion Locations">
</figure>

* Is this a true topography (potentially indicative of a biological susceptibility of particular neocortex)? Clinicians indicated that they do see increased numbers of lesions in these areas.
* Is there a selection bias? Are lesions in these areas easier to detect (due to particular characteristic syndromes or due to the actual neocortical structure of these areas)? Are patients with lesions in these areas more likely to be evaluated for surgery as these are not particularly eloquent cortex?
* In healthy population would there be FCDs in other areas but are they less likely to be epileptogenic?
* JOM suggested looking in autism datasets
* JD: Look at the 2 hemispheres as selection bias more likely in LH due to language lateralisation. 
* JOM: less thalamic innervation to temporoparietal junction, this might relate to apparent absence of lesions in this area.
* JD: Some clinical syndromes are pathognomonic eg SMA lesions. 
* This topography might be explained by cytoarchitectonic/genetic susceptibility.

:arrow_forward: ECB: Type 1 - can we include these? What about Type III?
* We have very few examples of Type I currently. This is likely due to the neuropathologists around the world having very different ideas about what is a Type I FCD (highlighted in Maria Thom's talk)
* FC: suggested we could in the future approach the problem the other way round and collect a cohort with good surgical outcome and no clear histology indicative of Type IIa or IIb. I.e. a cohort of FCD type I, gliosis, non-specific neocortical changes etc. and see if we have characteristic imaging signatures which could form a classification system.
* This could be a future project and we would need to send a survey round to find out whether we would have a reasonable sample size to do this type of analysis.

:arrow_forward: Lastly we discussed grant applications and funding 
* Lots of useful ideas and advice of possible funding avenues including combined grant applications.


***Thank you to everyone who attended and a BIG THANK YOU to everyone who has been powering through the protocols!*** :rocket:




