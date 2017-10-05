---
layout: post  
title: R Basic 201 Creating New Variables  
date: 2017-10-02  
category:
- Data Analysis  

tags: [R]  
published: false  
---

# User-written Functions

다음 자료를 참고하였습니다:  
- http://www.statmethods.net/management/userfunctions.html

# User-written Functions

One of the great strengths of R is the user's ability to add functions. In fact, many of the functions in R are actually functions of functions. The structure of a function is given below.

```r

myfunction <- function(arg1, arg2, ... ){
statements
 return(object)
 }

```

Objects in the function are local to the function. The object returned can be any data type. Here is an example.

```r
# function example - get measures of central tendency
# and spread for a numeric vector x. The user has a
# choice of measures and whether the results are printed.

mysummary <- function(x,npar=TRUE,print=TRUE) {
 if (!npar) {
   center <- mean(x); spread <- sd(x)
 } else {
   center <- median(x); spread <- mad(x)
 }
 if (print & !npar) {
   cat("Mean=", center, "\n", "SD=", spread, "\n")
 } else if (print & npar) {
   cat("Median=", center, "\n", "MAD=", spread, "\n")
 }
 result <- list(center=center,spread=spread)
 return(result)
}

# invoking the function
set.seed(1234)
x <- rpois(500, 4)
y <- mysummary(x)
Median= 4
MAD= 1.4826
# y$center is the median (4)
# y$spread is the median absolute deviation (1.4826)

y <- mysummary(x, npar=FALSE, print=FALSE)
# no output
# y$center is the mean (4.052)
# y$spread is the standard deviation (2.01927)
```

It can be instructive to look at the code of a function. In R, you can view a function's code by typing the function name without the ( ). If this method fails, look at the following R Wiki link for hints on viewing function sourcecode.

Finally, you may want to store your own functions, and have them available in every session. You can customize the R environment to load your functions at start-up.