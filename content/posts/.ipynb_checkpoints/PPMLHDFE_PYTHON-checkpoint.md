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

```{code-cell} ipython3
# HOW TO RUN A PPMLHDFE STATA COMMAND FROM PYTHON
```

```{code-cell} ipython3
###The newer versions of Stata allow for a very convenient integration with Python.
###In this post, I give a small demostration on how can we possibly run an econometric model with a Stata command from python. 
###I will focus on the regression command ppmlhdfe, which https://scorreia.com/software/ppmlhdfe/
#####https://arxiv.org/abs/1903.01633.

####ppmlhdfe is a Stata package developed by Correia, Guimarães, Zylkin (2019a). It allows to run Poisson pseudo-maximum likelihood regressions (PPML) with multi-way fixed effects.

####Working as a migration economist, I stumbled across applications of gravity models of migration quite a few times. 
####These models ofter rely on a rich combination of fixed effects (e.g. origin, destination and year) and require some code that optimizes computation time.
####As migration from i to j is typically measured as a dyadic count or frequency measure, scholars have preferred moving away from linear models, as Santos Silva and Tenreyro recommend in their seminal paper The Log of Gravity. (https://direct.mit.edu/rest/article/88/4/641/57668/The-Log-of-Gravity).


```

```{code-cell} ipython3
#### In a recent work, I wanted to compare how the typical gravity-style regression estimates compare with some models that Machine Learning (ML) scholars have adopted.

#Specifically, I wanted to see if out of sample, models like Random Forests or Gradient Boosting perform better to predict migration patterns.


####In other words, I wanted:
 - to rely on the nice functionalities of Python's Scikit-Learn to split the sample and run the ML models, 
 - but for the same training and test samples I wanted to benchmark against a ppml regression.
```

```{code-cell} ipython3

```
