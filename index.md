---
title       : The Galton Height Predictor
subtitle    : Submission for Coursera Data Science Project
author      : rutulian
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : solarized_light     # 
widgets     : [mathjax]            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
assets      :
        css: "./assets/css/app.css"
--- .dark .nobackground


<q>The Galton Height Predictor is a handy and convenient way to inaccurately
predict the heights of any Victorian children to be born!</q>

--- &twocol

## The dataset
The data used to create this predictor was collected by [Francis Galton]
(http://en.wikipedia.org/wiki/Francis_Galton) in 1885.  It is a list of
midparent heights and child heights, both in inches.  The midparent height
is calculated as the average of the father's height and 1.08 * mother's height.

*** {name: left}
The first 6 items:
<!-- html table generated in R 3.1.2 by xtable 1.7-4 package -->
<!-- Thu Nov 20 18:00:50 2014 -->
<table border=1>
<tr> <th>  </th> <th> child </th> <th> parent </th>  </tr>
  <tr> <td align="right"> 1 </td> <td align="right"> 61.70 </td> <td align="right"> 70.50 </td> </tr>
  <tr> <td align="right"> 2 </td> <td align="right"> 61.70 </td> <td align="right"> 68.50 </td> </tr>
  <tr> <td align="right"> 3 </td> <td align="right"> 61.70 </td> <td align="right"> 65.50 </td> </tr>
  <tr> <td align="right"> 4 </td> <td align="right"> 61.70 </td> <td align="right"> 64.50 </td> </tr>
  <tr> <td align="right"> 5 </td> <td align="right"> 61.70 </td> <td align="right"> 64.00 </td> </tr>
  <tr> <td align="right"> 6 </td> <td align="right"> 62.20 </td> <td align="right"> 67.50 </td> </tr>
   </table>
*** {name: right}
A summary of the data:
<!-- html table generated in R 3.1.2 by xtable 1.7-4 package -->
<!-- Thu Nov 20 18:01:16 2014 -->
<table border=1>
<tr> <th>  </th> <th>     child </th> <th>     parent </th>  </tr>
  <tr> <td align="right"> 1 </td> <td> Min.   :61.70   </td> <td> Min.   :64.00   </td> </tr>
  <tr> <td align="right"> 2 </td> <td> 1st Qu.:66.20   </td> <td> 1st Qu.:67.50   </td> </tr>
  <tr> <td align="right"> 3 </td> <td> Median :68.20   </td> <td> Median :68.50   </td> </tr>
  <tr> <td align="right"> 4 </td> <td> Mean   :68.09   </td> <td> Mean   :68.31   </td> </tr>
  <tr> <td align="right"> 5 </td> <td> 3rd Qu.:70.20   </td> <td> 3rd Qu.:69.50   </td> </tr>
  <tr> <td align="right"> 6 </td> <td> Max.   :73.70   </td> <td> Max.   :73.00   </td> </tr>
   </table>

--- .class #id

## The predictive model
1. The child height $Y$ is the dependent variable
2. The parent height $X$ is the independent variable
3. A simple linear regression of the form $Y = \alpha + \beta X$ is performed


```r
lm(galton)$coefficients
```

```
## (Intercept)      parent 
##  23.9415302   0.6462906
```

--- .class #id

## How to use
1. Go to [https://rutulian.shinyapps.io/GaltonShiny](https://rutulian.shinyapps.io/GaltonShiny)
2. Enter the height of the father in feet and inches
3. Enter the height of the mother in feet and inches
4. Observe the histogram, which displays where the child of these
two parents is predicted to lie within the distribution of heights
of children in the original dataset

Please note, the heights of father and mother are restricted to be
close to the extreme values within the original dataset.

