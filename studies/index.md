---
layout: page
title: Studies
excerpt: "On-going Projects"
search_omit: true
---



### Automated Detection of Focal Cortical Dysplasias

Focal cortical dysplasia (FCD) is a congenital abnormality of cortical development and a leading cause of surgically remediable drug resistant epilepsy. MRI has played a major role in the evaluation of patients; yet, significant proportions of lesions remain undetected by conventional image analysis. Machine learning offers a powerful framework to develop automated and individualised clinical tools that may improve the detection of lesions and prediction of clinically relevant outcome.

In work [published in Neuroimage: Clinical](http://www.sciencedirect.com/science/article/pii/S2213158216302674?via%3Dihub) in 2017, Adler, Wagstyl et al., developed a classifier using surface-based features to identify focal abnormalities of cortical development in a paediatric cohort. Focal cortical dysplasias in this paediatric cohort were correctly identified in 73% of the children.

<figure>
<img src="/images/Example_classifier_results.png"
alt="FCD examples" width="400" height="500" text-align: center>
<figcaption>Examples of cortical area detected by the neural network classifier in 5 patients with a radiological diagnosis of FCD. First column: T1-weighted images. Second column: FLAIR images. White circle on T1 and FLAIR images indicates lesion location. Third column: Neural network classifier output (yellow) and manual lesion mask (light blue) viewed on pial surface, for large lesions, or inflated surface, for small lesions buried in sulci.</figcaption>
</figure>

<figure>
<img src="/images/WRLD-EPS-02-4001-01.png"
alt="MELD around the world">
<figcaption>World map showing locations of collaborators.</figcaption>
</figure>

Further studies have validated this method 

<ul class="post-list">
{% for post in site.categories.resources %}
  <li><article><a href="{{ site.url }}{{ post.url }}">{{ post.title }} <span class="entry-date"><time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%B %d, %Y" }}</time></span>{% if post.excerpt %} <span class="excerpt">{{ post.excerpt | remove: '\[ ... \]' | remove: '\( ... \)' | markdownify | strip_html | strip_newlines | escape_once }}</span>{% endif %}</a></article></li>
{% endfor %}
</ul>
