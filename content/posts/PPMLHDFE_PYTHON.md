+++ 
draft = true
date = 2024-10-28T12:59:04+01:00
title = "A List of Datasets Collecting National Migration Policies"
description = ""
slug = ""
authors = []
tags = ["migration", "data", "migration policy", "datasets"]
categories = ["migration policy"]
externalLink = ""
series = ["Theme Demo"]
+++

---
jupytext:
  formats: md:myst
  text_representation:
    extension: .md
    format_name: myst
    format_version: 0.13
    jupytext_version: 1.16.1
kernelspec:
  display_name: Python 3 (ipykernel)
  language: python
  name: python3
---

# HOW TO RUN A PPMLHDFE STATA COMMAND FROM PYTHON


The newer versions of Stata allow for a very convenient integration with Python.

In this post, I give a small demostration on how can we possibly run an econometric model with a Stata command from python. 
I will focus on the regression command , which  __[**ppmlhdfe**](https://scorreia.com/software/ppmlhdfe/)__



## A general Motivation
**ppmlhdfe** is a Stata package developed by __[Correia, Guimarães, Zylkin (2019a)](https://arxiv.org/abs/1903.01633)__. It allows to run Poisson pseudo-maximum likelihood regressions (PPML) with multi-way fixed effects.

Working as a migration economist, I stumbled across applications of gravity models of migration quite a few times. 
These models ofter rely on a rich combination of fixed effects (e.g. origin, destination and year) and require some code that optimizes computation time.
As migration from i to j is typically measured as a dyadic count or frequency measure, scholars have preferred moving away from linear models, as Santos Silva and Tenreyro recommend in their seminal paper The Log of Gravity. (https://direct.mit.edu/rest/article/88/4/641/57668/The-Log-of-Gravity).



## My own setting
In a recent work, I wanted to compare how the typical gravity-style regression estimates compare with some models that Machine Learning (ML) scholars have adopted.
Specifically, I wanted to see if out of sample, models like Random Forests or Gradient Boosting perform better to predict migration patterns.


In other words, I wanted at the same time:

 - to rely on the nice functionalities of Python's Scikit-Learn to split the sample and run the ML models, 
 - but for the same training and test samples to make a benchmark with the ppml regression I was mostly familiar with.


```{code-cell} ipython3

```

## Before we start (a bit of bla bla)

As a word of caution, there are most surely plenty of alternative ways out there to reproduce this exercise while fully relying on python-based commands. After spending a few hours trying a full-python alternative, I then discovered the package I was adopting had a compatibility issue with new Pandas versions (the issue was already reported to the package mainteners).
Discouraged by the time loss, and being already familiar with the Stata hdfe world, I then decided for the first time to try out the new python-stata integration functionalities. 
An hour in, I was already excited by the simplicity of adapting my python code to the Stata-based additions.
I had worked on a project in the past that involved some mata coding. I needed to go back and forth from the inputs from Stata to the outputs of mata and viceversa, I find this integration quite straightforward, compared to that experience.

I'll give a simple demonstration below, that may be of use for anyone willing to do a similar exercise. My prediction is that I am not alone, among my colleagues in wanting from time to time that particular package from that particular software, but without sacrificing all the rest of nice functionalities and already existing code written in another.

## The implementation

 CTRL + SHIFT + V