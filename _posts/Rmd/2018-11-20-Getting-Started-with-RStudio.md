---
layout: post  
title: R 기초 102 RStudio 와 친해지는 방법  
date: 2018-11-19  
category: [R for Beginners]  
tag: [R]  
author: hkim  
image: /assets/images/icon/iconmonstr-monitoring-6-240.png
headerImage: true

---

***preface*** (last update: 2018.11.21) RStudio 를 실행하고 사용하는 방법에 대하여 설명합니다.

RStudio 를 처음 실행하면 화면이 크게 3등분 되어있습니다.

좌측은 콘솔(Console), 우측 상단은 Environment, 우측 하단은 Files 탭이 표시됩니다. 

Console 창에는 아마도 아래와 비슷한 메세지가 출력될 것입니다.

```
R version 3.4.4 (2018-03-15) -- "Someone to Lean On"
Copyright (C) 2018 The R Foundation for Statistical Computing
Platform: x86_64-w64-mingw32/x64 (64-bit)

R is free software and comes with ABSOLUTELY NO WARRANTY.
You are welcome to redistribute it under certain conditions.
Type 'license()' or 'licence()' for distribution details.

R is a collaborative project with many contributors.
Type 'contributors()' for more information and
'citation()' on how to cite R or R packages in publications.

Type 'demo()' for some demos, 'help()' for on-line help, or
'help.start()' for an HTML browser interface to help.
Type 'q()' to quit R.

> 
```

## Console 창 사용하기

먼저 간단하게 1 + 1 을 계산해 봅시다. Console 창에서 `>` 옆에 클릭하면 입력할 수 있는 것을 확인할 수 있습니다. 그럼 아래와 같이 입력하고 엔터키를 누릅니다.


{% highlight r %}
1+1
{% endhighlight %}



{% highlight text %}
## [1] 2
{% endhighlight %}

그럼 위와 같이 2 가 출력되는 것을 확인할 수 있습니다. `[1]` 은 첫번째 줄의 값이라는 뜻이니 우선은 크게 신경쓰지 맙시다.

변수를 저장하고 변수끼리 계산할 수도 있습니다. 먼저 `x` 라는 변수에 값 1 을 저장해봅시다. 값을 저장할때에는 `<-` 라는 기호를 씁니다.


{% highlight r %}
x <- 1
{% endhighlight %}

Console 창에는 아무런 표시가 되지 않지만, 우측 상단의 Environment 탭에서 x 라는 변수에 1 이 저장되었음을 확인할 수 있습니다. 그럼 Console 창에서 `x` 를 입력해 봅시다. 그럼 아래와 같이 1 값을 출력하는 것을 확인할 수 있습니다.


{% highlight r %}
x
{% endhighlight %}



{% highlight text %}
## [1] 1
{% endhighlight %}

그럼 `y` 에 100 을 저장하고 `x+y` 를 계산해봅시다.


{% highlight r %}
y <- 100
x+y
{% endhighlight %}



{% highlight text %}
## [1] 101
{% endhighlight %}






