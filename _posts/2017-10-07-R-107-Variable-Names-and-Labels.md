---
layout: post  
title: R 기초 107 변수 이름 및 레이블 (Variable Names and Labels)  
date: 2017-10-07  
category: [R for Beginners]  
tag: [R]  
author: hkim  
image: /assets/images/icon/iconmonstr-monitoring-6-240.png
headerImage: true

---

***preface*** 이번 포스트에서는 R에서 변수의 이름과 레이블을 설정하는 방법에 대하여 설명합니다.

## Variable Names

```r
# names(): 변수 이름을 모두 출력하는 함수
names(mydata)
```

```r
# 특정 변수 이름을 변경할 때 (변수 이름 기준)
names(mydata)[names(mydata) == "old.var.name"] <- "new.var.name"

# 특정 변수 이름을 변경할 때 (위치 기준)
colnames(mydata)[2] <- "new.var.name" # 2번째 column 변수명 변경


# 전체 변수 이름을 지정하여 변경할 때
# 변수의 갯수와 이름의 갯수가 같아야 합니다 
names(mydata) <- c("apple","banana","cherry")

# 전체 변수 이름을 VAR1, VAR2, VAR3, ... 으로 변경할 때
# 변수 이름이 한글로 되어있고, 이를 모두 영어로 바꿀 필요가 있을 때 유용합니다
names(mydata)[1:dim(mydata)[2]] <- paste("VAR", 1:dim(mydata)[2], sep="") # 연속하는 이름 붙이기

```

## Variable Labels

다음 자료를 참고하였습니다:  
- [http://www.statmethods.net/input/variablelables.html](http://www.statmethods.net/input/variablelables.html)

R의 변수 레이블 처리 능력은 다소 만족스럽지 않습니다.

Hmisc 패키지를 사용하는 경우 몇 가지 레이블 기능을 이용할 수 있습니다.

```r
library(Hmisc)
label(mydata$myvar) <- "Variable label for variable myvar"
describe(mydata)
```

안타깝게도이 레이블은 Hmisc 패키지에서 제공하는 함수(예: describe ())에서만 유효합니다. 다른 방법은 변수 이름으로 변수 레이블을 사용한 다음, 위치 색인을 사용하여 변수를 참조하는 것입니다.

```r
names(mydata)[3] <- "This is the label for variable 3"
mydata[3] # list the variable
```
