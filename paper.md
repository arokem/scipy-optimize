---
title: 'A short course about fitting models with the `scipy.optimize` module'
tags:
- scipy
- optimization
- models 
authors:
- name: Ariel Rokem
  orcid: 0000-0003-0679-1985
  affiliation: 1
affiliations:
- name: The University of Washington eScience Institute
  index: 1
date: 23 April 2018
bibliography: paper.bib
---

# Summary 

Fitting models and testing the match of the models to the measured data is a fundamental 
activity in many fields of science. This short (approximately 3-hour) course aims to teach 
participants to use the Scipy library's  `optimize` module to fit models to data [@scipy]. 
Using data from a psychology experiment [@rokem091553] as an example, the course motivates the 
use of explicit mathematical models to  explain and predict data and compares linear models 
and non-linear models. The core of the  lesson focuses on fitting a curve with the `curve_fit` 
function. Finally, the course introduces the idea of model comparison with cross-validation
for evaluation and selection between non-nested non-linear models. A video of an example of instructing this lesson by the author is available on [YouTube](https://www.youtube.com/watch?v=0eFokR-ikaA)
 
# Statement of need 

The target audience for this course are researchers or students with some programming 
knowledge (e.g., having participated in a 'Software Carpentry' workshop beforehand). 
Model fitting is useful in many different fields of research, but optimization for model
fitting is not a topic that is usually covered in introductory statistics or computing 
classes in. This course fills an existing need for hands-on curriculum that goes beyond the 
topics taught in introductory computing workshops, such as 'Software Carpentry', providing 
material for follow-up workshops on advanced/intermediate topics. 

# References