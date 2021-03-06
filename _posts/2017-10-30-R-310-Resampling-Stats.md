---
layout: post  
title: Resampling Statistics  
date: 2017-10-30  
category: [R for Beginners]  
tag: [R]  
author: hkim  
hidden: true # don't count this post in blog pagination  
image: /assets/images/icon/iconmonstr-monitoring-6-240.png
headerImage: true

---

다음 자료를 참고하였습니다:  
- [https://www.statmethods.net/stats/resampling.html](https://www.statmethods.net/stats/resampling.html)

# Resampling Statistics
The coin package provides the ability to perform a wide variety of re-randomization or permutation based statistical tests. These tests do not assume random sampling from well-defined populations. They can be a reasonable alternative to classical procedures when test assumptions can not be met. See coin: A Computational Framework for Conditional Inference for details.

In the examples below, lower case letters represent numerical variables and upper case letters represent categorical factors. Monte-Carlo simulation are available for all tests. Exact tests are available for 2 group procedures.

## Independent Two- and K-Sample Location Tests

```r
# Exact Wilcoxon Mann Whitney Rank Sum Test
# where y is numeric and A is a binary factor
library(coin)
wilcox_test(y~A, data=mydata, distribution="exact")

# One-Way Permutation Test based on 9999 Monte-Carlo
# resamplings. y is numeric and A is a categorical factor
library(coin)
oneway_test(y~A, data=mydata,
  distribution=approximate(B=9999))
```

## Symmetry of a response for repeated measurements

```r
# Exact Wilcoxon Signed Rank Test
# where y1 and y2 are repeated measures
library(coin)
wilcoxsign_test(y1~y2, data=mydata, distribution="exact")

# Freidman Test based on 9999 Monte-Carlo resamplings.
# y is numeric, A is a grouping factor, and B is a
# blocking factor.
library(coin)
friedman_test(y~A|B, data=mydata,
   distribution=approximate(B=9999))
```

## Independence of Two Numeric Variables

```r
# Spearman Test of Independence based on 9999 Monte-Carlo
# resamplings. x and y are numeric variables.
library(coin)
spearman_test(y~x, data=mydata,
   distribution=approximate(B=9999))
```

## Independence in Contingency Tables

```r
# Independence in 2-way Contingency Table based on
# 9999 Monte-Carlo resamplings. A and B are factors.
library(coin)
chisq_test(A~B, data=mydata,
   distribution=approximate(B=9999))

# Cochran-Mantel-Haenzsel Test of 3-way Contingency Table
# based on 9999 Monte-Carlo resamplings. A, B, are factors
# and C is a stratefying factor.
library(coin)
mh_test(A~B|C, data=mydata,
   distribution=approximate(B=9999))

# Linear by Linear Association Test based on 9999
# Monte-Carlo resamplings. A and B are ordered factors.
library(coin)
lbl_test(A~B, data=mydata,
   distribution=approximate(B=9999))
```

Many other univariate and multivariate tests are possible using the functions in the coin package. See A Lego System for Conditional Inference for more details.

## To Practice
Try the exercises in this course on data analysis and statistical inference in R.
