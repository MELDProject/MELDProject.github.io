---
layout: page
title: Studies
excerpt: "On-going Projects"
search_omit: true
---



### Automated Detection of Focal Cortical Dysplasias

Focal cortical dysplasia (FCD) is a congenital abnormality of cortical development and a leading cause of surgically remediable drug resistant ep\
ilepsy. MRI has played a major role in the evaluation of patients; yet, significant proportions of lesions remain undetected by conventional imag\
e analysis. Machine learning offers a powerful framework to develop automated and individualised clinical tools that may improve the detection of\
 lesions and prediction of clinically relevant outcome.


<ul class="post-list">
{% for post in site.categories.resources %}
  <li><article><a href="{{ site.url }}{{ post.url }}">{{ post.title }} <span class="entry-date"><time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%B %d, %Y" }}</time></span>{% if post.excerpt %} <span class="excerpt">{{ post.excerpt | remove: '\[ ... \]' | remove: '\( ... \)' | markdownify | strip_html | strip_newlines | escape_once }}</span>{% endif %}</a></article></li>
{% endfor %}
</ul>
