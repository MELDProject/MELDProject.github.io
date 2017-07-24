---
layout: page
title: Welcome
excerpt: "MELD project home page."
search_omit: true
---

The Multi-centre Epilepsy Lesion Detection (MELD) project is an international collaboration dedicated to improving the detection of lesions in patients with drug-resistant epilepsy.

We hope you find this site a useful source of information about the MELD project.

### Automated Detection of Focal Cortical Dysplasias

Focal cortical dysplasia (FCD) is a congenital abnormality of cortical development and a leading cause of surgically remediable drug resistant epilepsy. MRI has played a major role in the evaluation of patients; yet, significant proportions of lesions remain undetected by conventional image analysis. Machine learning offers a powerful framework to develop automated and individualised clinical tools that may improve the detection of lesions and prediction of clinically relevant outcome. 

In work [published in Neuroimage: Clinical](http://www.sciencedirect.com/science/article/pii/S2213158216302674?via%3Dihub) in 2017, Adler, Wagstyl et al., developed a classifier using surface-based features to identify focal abnormalities of cortical development in a paediatric cohort. Focal cortical dysplasias in this paediatric cohort were correctly identified in 73% of the children.

<figure>
<img src="/images/FCD_radiological.png"
alt="FCD examples">
<figcaption>  Examples of cortical area detected by the neural network classifier in 5 patients with a radiological diagnosis of FCD. First column: T1-weighted images. Second column: FLAIR images. White circle on T1 and FLAIR images indicates lesion location. Third column: Neural network classifier output (yellow) and manual lesion mask (light blue) viewed on pial surface, for large lesions, or inflated surface, for small lesions buried in sulci.</figcaption>
</figure>

### Open, Reproducible Research

One of the major focuses of the MELD Project is to create open-access, robust and generalisable tools for FCD detection. 

### Contact

You can contact us at [MELD.study@gmail.com](mailto:MELD.study@gmail.com).

You're very welcome to contact us via [GitHub](https://github.com/MELDProject) too. 

This website is hosted via [GitHub pages](https://github.com/MELDProject/MELDProject.github.io). If you see any typos or other mistakes please let us know...or file a pull request with your edits.


<!---
Commented out the code to list recent posts. Might be useful again one day in the future!
<ul class="post-list">
{% for post in site.posts limit:10 %}
  <li><article><a href="{{ site.url }}{{ post.url }}">{{ post.title }} <span class="entry-date"><time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%B %d, %Y" }}</time></span>{% if post.excerpt %} <span class="excerpt">{{ post.excerpt | remove: '\[ ... \]' | remove: '\( ... \)' | markdownify | strip_html | strip_newlines | escape_once }}</span>{% endif %}</a></article></li>
{% endfor %}
</ul>
-->
