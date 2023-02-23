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

## Plotting

- TODO: move to new epsiode, add epsidoe to config.yaml

:::::: challenge

Can you display an image

:::solution
![This is a cool plot. Adapted from https://alison.netlify.app/rls-plot-twist/]([https://magrittr.tidyverse.org/logo.png](https://raw.githubusercontent.com/daydreamer125/Workshop_R_tidyverse/main/episodes/bakeoff_viewers.png)){alt='ggplot plot.'}

:::


::::::


::::::::::::::::::::::::::::::::::::: keypoints 

- magrittr is cool

::::::::::::::::::::::::::::::::::::::::::::::::

[r-markdown]: https://rmarkdown.rstudio.com/
