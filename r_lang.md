---
title:  'R-language for statistical computing and visualization in social sciences and humanities'
author: Markus Kainu
date: January 23, 2014
affiliation: University of Turku
tags: [r-language, open science]
bibliography: bibtex.bib
lang: english
abstract: In sit amet sapien mollis ligula dignissim vehicula. Fusce turpis dui, semper consequat erat eget, laoreet rutrum diam. 
...

<!--
cd ~/workspace/openscience/digihist
pandoc -s r_lang.md -o r_lang.html --toc --filter pandoc-citeproc -H ~/workspace/web/css/rmarkdown.css

pandoc r_lang.md -o r_lang.pdf --toc --number-sections --filter pandoc-citeproc
#
pandoc r_lang.md -o r_lang.pdf --template=../../template/pandoc_article/tex_templates/pandoc.latex.template --number-sections --toc --latex-engine=xelatex -V lang=english -V papersize:a4paper -V documentclass=scrartcl

-->

# Introduction - Open Research Methods

The debate on open science in the context of Social sciences and humanities (SSH) has been predominantly focusing on open access to research publication and opening up the various types of digital research data (open research data). The use of open research methods has received a lot less attention due to obvious reason.

Firstly, research methods in SSH have been predominantly qualitative meaning that the role of software or computation has been minor in the analytical process. Second, the quantitative fields of SSH have mostly used tailor-made survey and other specific closed research data that was well suited for analysis of custom statistical tools as SPSS, Stata or Excel. However, the future looks different as the quantity and multiple sources of digital data are challeging both traditional approaches in SSH, the purely qualitative approach and custom tools approach in quantitative analysis. 

As Gary @king2014 describes it:

>An important driver of the change sweeping the field is the enormous quantities of highly informative data inundating almost every area we study. In the last half-century, the information base of social science research has primarily come from three sources: survey research, end-of-period government statistics, and one-off studies of particular people, places, or events. In the next half-century, these sources will still be used and improved, but the number and diversity of other sources of information are increasing exponentially and are already many orders of magnitude more informative than ever before.

The new open digital data is often big and messy and it calls for flexible tools that can be tailored and modified for the particular question and data. This haastaa ei vain yliopiston vaan myös yrityksen ja siksi on nähty.... From this demand we have witnessed an unseen growth in user and developers of free and open source computational research methods.


# What is R? - Origin and characteristics

## Origin
- R-language was iniated by two 
- open source

## R-language as a programming language
- object oriented, s-language bell laboratories
(G)UI's, IDE Rstudio, git
- contributed packages

## R-language as a tools for statistical computing
- structure
- visual
- open source, community, licensing, teaching

## Popularity of R-language
- enterprise level services

<!--

# Who makes the R possible? -  R-project

## Organisation of the project
- development vs. user help

## Development of the language

## User support
- mailing lists - general vs. special interest groups
blogs
- q & a sites

## Contributed packages
- CRAN - task views
R-forge
- Github
- bioconductor

# What is R used for? - R in action
Why R-language is popular

## Development of statistical methods
- new methods implemented first in R

## Applied statistics

### Bio/geo-sciences
- Geograhical Information Systems

### Social sciences/economics

### Humanities - analysis of natural languages

## Business/enterprise analytics
- insurance, big data, banking, industry
- social media: facebook, google, twitter

## Data journalism
- Guardian, New York Times, Chicago Herald Tribune

# How does it work? - Visualising data in humanities using R-language

## Word clouds

## Networks maps

## Spatial visualisation

## Clustering

## 
-->

# References


