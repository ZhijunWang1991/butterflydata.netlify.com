---
title: R学习进展
author: Jon
date: '2020-02-12'
slug: rnotebook
categories:
  - R
tags:
  - data science
---
1 Some function to manage the R workSpace

```r
##change the working direction
setwd()

##show the current working direction
getwd()

##save images
save.image("myfile")
png("filename.png")
```

2 creat a matrix

```r
y <- matrix(1:20, nrow = 5, ncol = 4)

y
```

3 input excel or csv files

```r
library(readxl)
dataset <- read_excel("direction")

dataset <- read.csv2("direction")
```
4 Legend options

Example: Comparing drug A and drug B response by dose

```r

dose <- c(20, 30, 40, 45, 60)
drugA <- c(16, 20, 27, 40, 60)
drugB <- c(15, 18, 25, 31, 40)

opar <- par(no.readonly=TRUE)
par(lwd=2, cex=1.5, font.lab=2)

plot(dose, drugA, type="b",
    pch=15, lty=1, col="red", ylim=c(0, 60),
    main="Drug A vs. Drug B",
    xlab="Drug Dosage", ylab="Drug Response")
lines(dose, drugB, type="b",
    pch=17, lty=2, col="blue")
abline(h=c(30), lwd=1.5, lty=2, col="gray")

library(Hmisc)
minor.tick(nx=3, ny=3, tick.ratio=0.5)

legend("topleft", inset=0.1, title="Drug Type", c("A","B"),
    lty=c(1, 2), pch=c(15, 17), col=c("red", "blue"))

par(opar)

```
![](/cn/2020-02-12-rnotebook_files/lengend.png)

5 How to mark the Mathematical Annotation?
```r
help(plotmath)
demo(plotmath)
```
Some examples:
![](/cn/2020-02-12-rnotebook_files/math.png)
![](/cn/2020-02-12-rnotebook_files/math2.png)
![](/cn/2020-02-12-rnotebook_files/math3.png)
























