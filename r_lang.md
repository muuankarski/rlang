---
title:  'Open research methods in computational social sciences and humanities: introducing R'
author: Markus Kainu
date: January 23, 2014
affiliation: University of Turku
tags: [r-language, open science]
bibliography: bibtex.bib
lang: english
...

<!--
cd ~/workspace/openscience/digihist
pandoc -s r_lang.md -o r_lang.html --toc --filter pandoc-citeproc -H ~/workspace/web/css/rmarkdown.css

pandoc r_lang.md -o r_lang.pdf --toc --number-sections --filter pandoc-citeproc
pandoc r_lang.md -o r_lang.odt --toc --number-sections --filter pandoc-citeproc
pandoc r_lang.md -o r_lang.docx --toc --number-sections --filter pandoc-citeproc
pandoc -s r_lang.md -o r_lang.rtf --toc --number-sections --filter pandoc-citeproc
pandoc r_lang.md -o r_lang.epub --toc --number-sections --filter pandoc-citeproc
#
pandoc r_lang.md -o r_lang.pdf --template=../../template/pandoc_article/tex_templates/pandoc.latex.template --number-sections --toc --latex-engine=xelatex -V lang=english -V papersize:a4paper -V documentclass=scrartcl

-->

Introduction - Open Research Methods
================

The debate on open science in the context of Social Sciences and Humanities (SSH) has been predominantly focusing on open access to research publication and opening up the various types of digital research data (open research data). The openness of research methods has received a less attention.

I can think of two main reasons for that. On the one hand, research methods in SSH have predominantly been qualitative where software has played only a supporting role. Such research methods, let's take *discourse analysis*, have always been open, free to use and to modify and redistribute.  On the other hand, the quantitative fields of SSH have mostly used statistics or survey and register data, or other, often closed, tailor-made data that custom proprietary data analysis tools such as SPSS, Stata or Excel are well suited for. However, the future of SHH looks somewhat different as the quantity and multiplicity of sources of digital data are challeging both traditional approaches in SSH, the purely qualitative approach and custom tools approach in quantitative analysis. The future that Gary @king2014 of Harvard describes as:

>An important driver of the change sweeping the field is the enormous quantities of highly informative data inundating almost every area we study. In the last half-century, the information base of social science research has primarily come from three sources: survey research, end-of-period government statistics, and one-off studies of particular people, places, or events. In the next half-century, these sources will still be used and improved, but the number and diversity of other sources of information are increasing exponentially and are already many orders of magnitude more informative than ever before.

In the data rich future of SSH research, as the role of software and computation becomes more central, the questions of licensing, ownership, modification and distribution of that software will become increasingly important. This chapter will introduce one viable option for analysing your data called R.

<!--

As relevant data for SSH is being generated and published in multiple sites and as the data is often messy and big in size this development calls for flexible tools that can be tailored and modified for the particular data and research question. The custom proprietary tools that are well fitted for analysis of survey, register and statistical data are not capable of adjusting to these emerging individual needs of researcher. Therefore we have witnessed an unseen growth in userbase and developers of free and open source computational research methods. 

And it is not only that there are no proprietary software for these purposes, but the open research methods are also required becaused of

-->

What is R?
================

R is one of the most popular platforms for data analysis and visualization currently available. R is distributed under the terms of the *GNU General Public License* so it is free and open source and it can be distributed under those conditions. R is available from [Comprehensive R Archive Network](http://cran.r-project.org/) (CRAN). The name R comes from the first names of two New Zealand statisticians Ross Ihaka and Robert Gentleman who created the language in late 1990's. 

R can be regarded as an implementation of the S language which was developed at Bell Laboratories in 70's by Rick Becker, John Chambers and Allan Wilks  [@venables_introduction_2013]. R is an object-oriented programming language which means that unlike in SPSS or SAS that give you abundant information on particular model you implement, R only creates a *fit object* in memory that can be used in subsequent analysis. This structure of R directs the user to implement the data-analysis as stepwise process which becomes very useful later on when solving complex research problems using vast and messy data typical for emerging computational SSH research.


R user-interfaces
----------------

R runs in Windows, Mac OS X and GNU/Linux operating systems on local computer, but a different server implementations are becoming increasingly popular, such as [R-Fiddle](http://www.r-fiddle.org/#/) or [rnotebook](http://ramnathv.github.io/rNotebook/). The most basic user interface for R is *console*, which allows user to type in commands and outputs the results of the analysis. If the results is a plot a pop-up graphical windows is opened. There are several graphicsl user interfaces (GUI) in R that may be helpful in the beginning, like [RCommander](http://www.rcommander.com/) or [Deducer](http://www.deducer.org/). Perhaps the most productive way for using R is through a [integrated development environment](http://www.sciviews.org/_rgui/projects/Editors.html) (IDE) that provide the user, in addition to console, several useful functionalities for controlling the whole research project. [RStudio](http://www.rstudio.com/ide/download/) has gained a lot of popularity in last couple of years and is also my personal favourite IDE. It combines the console with script editor, plot browser, file browser and environment window. If the user uses plain text (latex or markdown) for typesetting the texts, RStudio has a tailored text editor and support for version control either in [git](http://git-scm.com/) or in [subversion](http://subversion.tigris.org/). In addition, RStudio has native support for html-based presentation graphics using [reveal.js](http://lab.hakim.se/reveal-js/#/)-framework. All these operations makes it possible to squeeze the whole research process within a single software environments from planning to publishing. Rstudio can also be run on a remote server through web browser. The RStudio company has another exciting open source tool for R called [*shiny*](http://www.rstudio.com/shiny/) that can be used for creating interactive web applications such as this [experimental gadget of mine](http://glimmer.rstudio.com/muuankarski/QogCorr/).


Structure of R-project
----------------

For someone new to R, the peculiar structure of the language creates a very steep learning curve. Same applies to learning how the whole project is organised. 

Official name [The R Project for Statistical Computing](http://www.r-project.org/) refers both to the centrally maintained core as well as R's distributed structure of contributed extensions, called *packages*. Packages in R are collections of functions and/or data that are packaged for conviniency. Installing a package broadens your the functionality of your R installation. Basic R installation consists of so called *base installation* that includes the core with some 25 additional *packages* for the most basic functionality. The core of the language is maintained by *R Development Core Team*, but the additional packages are developed and maintained by individual developers and research institutes. R users often create packages for themselves, but if one thinks the package could be useful for other users too, the packages can be distributed through repositories.

CRAN is the "official" repository for contributed packages and currently hosts 5150 packages that can be used to extend R. In the last couple of years various code hosting sites such as [GitHub](https://github.com/) have become increasingly important resources especially for collaborative development of new packages. Github hosts currently rougly 1500 packages for R. [Bioconductor](http://www.bioconductor.org/) is another separate package repository, but can be regarded as *domain spesific* for it hosts packages for *the analysis and comprehension of high-throughput genomic data*. Other such domain spesific projects are for example [rOpenSci](http://ropensci.org/) and emerging [rOpenGov](http://ropengov.github.io/) that provide tools for open science and open government data, respectively.

Learning the language
===============

As the internet has brought together the vast community around R, the internet has become the main channel for delivering instructions for R. The official *Introduction to R* by @venables_introduction_2013 is an important document to master when getting into the language. Besides this general introduction R-project has also a domain spesific structure where you can start learning from so called [task views](http://cran.r-project.org/web/views/). For SSH researcher the [social sciences](http://cran.r-project.org/web/views/SocialSciences.html) and [natural language processing](http://cran.r-project.org/web/views/NaturalLanguageProcessing.html) task views are good places to begin with. 

Discussions and announcement on R happen mainly through [R official mailing lists](http://www.r-project.org/mail.html) that have their own lists for development and user help. [R help](https://stat.ethz.ch/mailman/listinfo/r-help) is the main list for general help and receives tens of mails per day. Most of the individual packages have their own mailing list for development where anyone can join if wanting to contribute to the packages.

The official mailing lists have recently been challenged by so called Question & Answer -sites like [Stack Overflow](http://stackoverflow.com/questions/tagged/r) in delivering solutions for one-off user questions. Stack Overflow has currently almost 47000 questions tagged with R. In comparison to proprietary software, there are 2014 questions tagged with SAS, 616 with Stata and 362 SPSS. These figures are used as one indicator of the [increasing popularity of R](http://r4stats.com/articles/popularity/). Besides the Question & Answer sites, there are hundreds of blogs discussing specific analytical problem using R and feeds from the blogs are aggregated in [R-bloggers](http://www.r-bloggers.com/)-website. 

Another, more formal channel for distributing and communicating R have become the so called massive open online courses (MOOC). MOOCs seem to work well for teaching programming and many courses in [Coursera](https://www.coursera.org/) and [EdX](https://www.edx.org/) have become hugely popular attracting tens of thousands of students each year. The free licensing of R has made it primary language on these coursesas it is basicly the only viable alternative for teaching statistical programming for massive crowds.

Aside with vibrant internet community more and more books are being published on R. Books can be put in three categories. First are the general introductions to statistics using R. *Discovering Statistics Using R* by @field_discovering_2012 and *R in Action: Data Analysis and Graphics With R* by Robert @kabacoff_r_2013 are popular examples of that category. Second there are more and more books addressing how to solve some specific analytical problems using R. A prime examples of books in this category are *Complex Surveys: A Guide to Analysis Using R*  by Thomas @lumley_complex_2011, *Text Analysis with R for Students of Literature* by Matthew @jockers_text_2014, *R Graphics Cookbook* by @chang2012r and *Dynamic documents with R and knitr* by Yihui @xie_dynamic_2014. A third category are the books that focus on specific theoretical issue in statistics and use R as a primary language to demonstrate this. Such books are for instance *Bayesian Data Analysis* by @gelman_bayesian_2013 or *Multilevel Analysis: An Introduction to Basic and Advanced Multilevel Modeling* by @snijders_multilevel_2011.


Use of R language
================

Throughout it's existence the main use of R has been implementation of new statistical methods. This is still the case and implementations of new statistical methods are usually first available in R. However, various fields of applied statistics have become more active as researchers across disciplines have started to migrate into R. *Bioconductor* was already mentioned as an example of a domain spesific initiative to apply R in their analysis, for genome data in this case. Natural sciences in general have been early adopters and for example in Geographical Information Systems (GIS) the R has started rival proprietary GIS-software. In the case of GIS in R it is possible to combine traditional statistical methods and programming with spatial data and statistics in one environment. In SSH this is  useful as there are a lot of spatial data available and researcher may want to cluster the data thematically, but also visualize it as maps. As for humanities,  Matthew @jockers_text_2014 book is one of the first attemps to foster use of R. In digital humanities blogoshpere there are few others besides [Jockers blog](http://www.matthewjockers.net/) that are worth reading, namely [W. Caleb McDaniel from Rice University](http://wcm1.web.rice.edu/index.html) and [Quantifying Memory blog by Rolf Fredheim from Cambridge](http://quantifyingmemory.blogspot.com/).

Addition to academic applications, R has become a major player in business analytics. This is largely due to R's capabilities in visualisation and analysing so called *big data*, but also die to companies like [Revolution Analytics](http://www.revolutionanalytics.com/) that have started proving consultation and creating tailored application for enterprise needs. Annual [R/Finance 2014](http://www.rinfinance.com/)-conference gives nice overview of adoption of R in banking and insurance sectors. For example [Google](https://plus.google.com/+ResearchatGoogle/posts/em2i7TEpHgj) uses R in-house and also provides packages as [r-google-analytics](http://code.google.com/p/r-google-analytics/) or [rgooglevis](http://code.google.com/p/google-motion-charts-with-r/). One emerging fiels is so called data journalism where major players as [New York Times](http://blog.revolutionanalytics.com/2011/03/how-the-new-york-times-uses-r-for-data-visualization.html) or [Guardian](http://cran.r-project.org/web/packages/GuardianR/index.html) use R in the data-driven stories [such as this](http://chartsnthings.tumblr.com/post/22471358872/sketches-how-mariano-rivera-compares-to-baseballs).



Conclusions
================

R is certainly not the only alternative for proprietary data analysis software or for analysis of complex digital data. For example, [Python](http://www.python.org/) is another viable option especially for someone looking for more general purpose language that also masters data analysis. [Whether python is going to displace R](http://readwrite.com/2013/11/25/python-displacing-r-as-the-programming-language-for-data-science#awesm=~ouemDFJ542FxpR) has recently been debated in data science blogosphere. The data analysis is becoming mainstream on many fields, not just in academic research, but R is still remaining hard to learn and very much researcn oriented. Programmers rather want to extend the language they already know than learn a new one and python is a lot more common than R. For very intensive computation [Julia](http://julialang.org/) is becoming popular open source option, too. It is still in early phase of development, but is already viable option if processing time is important.

But for scientific work I would emphasize the *licensing* of the software more than the name of the particular technology. It is well possible that the recent buzz around digital data in SSH marks only the beginning of a data intensive research tradition. For someone wanting to success in that game it will be equally important to develop the subtantial understanding of the research topics as well as technological understanding of the new emerging tools. R is a prime example of this development where academics have taken a major role in software development and created tools that suits better for their research problems than proprietary software. 

This development will go on and therefore it is advisable for someone who is interested in learning these techniques to carefully look at the licensing before investing time and effort in learning the technology. Free and open source tools are great in this respect as once you can pick up the skills to use the techonolgy, you soon will find that it needs to be improved for your purposes. In free and open source technology you can learn how the code works, write improvements and then publish them for the wider research community for use and for further development. In addition, free licensing also allows you to teach the technology, apply it in any purpose, including commercial, and to distribute it. Open source research software is not always the easiest and quickest way to get job done, but in the long run they are often worth the time invested.

In addition, the openness of the computational research methods is important from the *reproducibility* of your research. Along with demands for open access of research publications there are tendencies that more and more journals in computational sciences will require both the data and algorithms behind the results to published together with the article. As SSH scholars are moving towards computational analysis this issue of reproducibility should also be taken into account. R is a great tool that fullfills all these conditions, but are several other out there, too. After all, it is not necessary for all to become software developers, but to have basic understanding and to pair with developers who know more. 

Steve @lohr_literary_2013 interviewed some leading digital humanists in New York Times article *Literary History, Seen Through Big Data’s Lens* on the future of SSH and posed a question whether these emerging computational technologies will undermine the role qualitative research in the field. Matthew Jocker, whose book *Macroanalysis: Digital Methods and Literary History* [-@jockers2013macroanalysis] was central in the article, emphasized that finding the right questions and flaws in the analysis still requires deep, both qualitative and quantitative, understanding of the field:

>But we’re at a moment now when there is much greater acceptance of these methods than in the past. There will come a time when this kind of analysis is just part of the tool kit in the humanities, as in every other discipline.

And that:

>Quantitative tools in the humanities and the social sciences, as in other fields, are most powerful when they are controlled by an intelligent human. Experts with deep knowledge of a subject are needed to ask the right questions and to recognize the shortcomings of statistical models.

The quest for new kind of collaboration between scholars and fields of research is also emphasized by professor Gary @king2014. He claims that the analysis of large digital data requires skills that can't be found from traditional fields of social sciences.

>Through collaboration across fields, however, we can begin to address the interdisciplinary substantive knowledge needed, along with the engineering, computational, ethical, and informatics challenges before us.

In addition, @king2014 assumes that this collaboration will eventually blur the dichotomy between qualitative and quantitative analysis, and he portraits a future where both traditions have merged into social sciences where the important research problems are solved in collaboration.

> Instead of quantitative researchers trying to build fully automated methods and qualitative researchers trying to make due with traditional human-only methods, both now are heading toward, using, or developing computer-assisted methods that empower both groups. This development has the potential to end the divide, to get us working together to solve common problems, and to greatly strengthen the research output of social science as a whole.

This may well be true for humanities as well if we dare to take upo the challenge. (Or some other sentimental ending...)
 
References
================


