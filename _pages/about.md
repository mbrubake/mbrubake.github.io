---
permalink: /
title: "About Me"
excerpt: "About Me"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

I'm an Assistant Professor of [Computer Science](http://www.eecs.yorku.ca/) at [York University](http://yorku.ca), a Faculty Affiliate at the [Vector Institute](http://vectorinstitute.ai) and an Adjunct Professor in the [University of Toronto Department of Computer Science](http://www.cs.toronto.edu).  Previously I was a Researcher Director (2018-2020) at [Borealis AI](http://borealisai.com) where I continue to work as an Academic Advisor.  I am also a co-founder and advisor of [Structura Biotechnology](https://structura.bio) (makers of [cryoSPARC](https://cryosparc.com/)), one of the original contributors to [Stan](https://mc-stan.org/) and was a Research Associate at [Cadre Research Labs](https://www.cadreresearchlabs.com/) (makers of [TopMatch-GS](https://www.cadreforensics.com/)).  I studied at the University of Toronto where I received my PhD in 2011.  I also did postdocs at the Toyota Technological Institute at Chicago and the University of Toronto.  My research interests span fundamental methods in computer vision, machine learning and statistics.  Recently I have been focusing on probabilistic generative models (like normalizing flows) and methods for electron cryomicroscopy (cryo-EM).

I am a member of the [Centre for Vision Research](http://www.cvr.yorku.ca) and core member of the [Vision: Science to Application (VISTA)](http://vista.info.yorku.ca/) program.  I currently serve as an Associate Editor for [IET Computer Vision](http://digital-library.theiet.org/content/journals/iet-cvi) and have been an Area Chair for a number of conferences.


## Research Interests
I am interested in building rich, detailed models which capture fundamental relationships between the world and our observations of it. Such models ultimately enable us to measure and predict sometimes surprising details.

Most recently I have been focusing on probabilistic generative models, specifically normalizing flows.  My research has been exploring theoretical aspects of normalizing flows and their applications.  I also have an interest on the problem of estimating the 3D structure of biological molecules such as proteins and viruses with Cryo-EM.  Beyond those current focuses, I have also worked on vehicle localization for robotics, physically realistic models of human motion, probabilistic programming languages, Bayesian methods, MCMC and forensic ballistics.

## Prospective Students
Interested in joining my group?  I'm also on the look out for exceptional students and colleagues to work with.  More information is available [here](/joining/).

# Recent News
{% include base_path %}
{% assign news = site.news | reverse %}
{% assign first_post = news | first %}
{% assign first_year = first_post.date | date: '%Y' %}
{% assign first_day = first_post.date | date: '%j' %}
{% assign post_count = 0 %}
{% for post in news %}
  {% assign cyear = post.date | date: '%Y' %}
  {% assign cday = post.date | date: '%j' %}
  {% if cyear != first_year %}
    {% assign ellapsed_days = first_year | minus:cyear | times:365 | plus:first_day | minus:cday %}
  {% else %}
    {% assign ellapsed_days = first_day | minus:cday %}
  {% endif %}
  
  {% if ellapsed_days > 365 and post_count > 3 %}
    {% break %}
  {% endif %}
  {% include archive-single.html %}
  {% assign post_count = post_count | plus: 1 %}
{% endfor %}

---

For more news see [here](/news/).
