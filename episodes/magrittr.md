---
title: "magrittr - Piping"
teaching: 10
exercises: 2
---

:::::::::::::::::::::::::::::::::::::: questions 

- How do you use pipes in R with magrittr`?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- ...

::::::::::::::::::::::::::::::::::::::::::::::::

## Introduction

![Magrittr Logo](https://magrittr.tidyverse.org/logo.png){alt='magrittr logo.'}



Look at magrittr

:::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::: instructor

Inline instructor notes can help inform instructors of timing challenges
associated with the lessons. They appear in the "Instructor View"

::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: challenge 

## Challenge 1: Can you do it?

What is the equivalent of using pipes
```r
f(x)
```

:::::::::::::::::::::::: solution 

## Output
 
```r
x %>% f
```

:::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: challenge 

## Challenge 2: Can you do it?

Can you rewrite the following with pipes to make it easier to read?
```r
carData <-
 transform(
 aggregate(
 . ~ cyl,
 data = subset(mtcars, hp > 100),
 FUN = function(x) round(mean(x), 2)
 ),
 kpl = mpg*0.4251
 )
```

:::::::::::::::::::::::: solution 

## Output
 
```r
carData <-
mtcars %>%
subset(hp > 100) %>%
aggregate(
. ~ cyl,
data = .,
FUN = . %>% mean %>% round(2)
) %>%
transform(kpl = mpg %>% multiply_by(0.4251))
```

:::::::::::::::::::::::::::::::::
::::::::::::::::::::::::::::::::::::::::::::::::


::::::::::::::::::::::::::::::::::::: keypoints 

- magrittr is cool

::::::::::::::::::::::::::::::::::::::::::::::::

[r-markdown]: https://rmarkdown.rstudio.com/
