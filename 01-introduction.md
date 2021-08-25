---
title: "Using RMarkdown"
teaching: 10
exercises: 2
---

:::::::::::::::::::::::::::::::::::::: questions 

- How do you write a lesson using RMarkdown and `{sandpaper}`?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Explain how to use markdown with the new lesson template
- Demonstrate how to include pieces of code, figures, and nested challenge blocks

::::::::::::::::::::::::::::::::::::::::::::::::

## Introduction



```r
library("curl")
library("cowsay")
```

```{.error}
Error in library("cowsay"): there is no package called 'cowsay'
```

```r
say("catfact", "cat")
```

```{.error}
Error in say("catfact", "cat"): could not find function "say"
```


This is the new Carpentries template. It is written in [RMarkdown][r-markdown],
which is a variant of Markdown that allows you to render code inside the
lesson. Please refer to the [lesson
example](https://carpentries.github.io/lesson-example) for full documentation.

What you need to know is that there are three block quotes required for a valid
Carpentries lesson template:

 1. `questions` are displayed at the beginning of the episode to prime the
    learner for the content.
 2. `objectives` are the learning objectives for an episode displayed with
    the questions.
 3. `keypoints` are displayed at the end of the episode to reinforce the
    objectives.

::::::::::::::::::::::::::::::::::::: challenge 

## Challenge 1: Can you do it?

What is the output of this command?


```r
paste("This", "new", "template", "looks", "good")
```

:::::::::::::::::::::::: solution 

## Output
 

```{.output}
[1] "This new template looks good"
```

:::::::::::::::::::::::::::::::::


## Challenge 2: how do you nest solutions within challenge blocks?

:::::::::::::::::::::::: solution 

You can add a line with at least three colons and a `solution` tag.

:::::::::::::::::::::::::::::::::
::::::::::::::::::::::::::::::::::::::::::::::::

## Figures

You can also include figures generated from RMarkdown:


```r
pie(
  c(Sky = 78, "Sunny side of pyramid" = 17, "Shady side of pyramid" = 5), 
  init.angle = 315, 
  col = c("deepskyblue", "yellow", "yellow3"), 
  border = FALSE
)
```

<div class="figure" style="text-align: center">
<img src="fig/01-introduction-rendered-pyramid-1.png" alt="pie chart illusion of a pyramid"  />
<p class="caption">Sun arise each and every morning</p>
</div>

Or you can use standard markdown for static figures:

![You belong in The Carpentries!](https://raw.githubusercontent.com/carpentries/logo/master/Badge_Carpentries.svg){alt='Blue Carpentries hex person logo with no text.'}


## Math

One of our episodes contains $\LaTeX$ equations when describing how to create
dynamic reports with {knitr}, so we now use mathjax to describe this:

`$\alpha = \dfrac{1}{(1 - \beta)^2}$` becomes: $\alpha = \dfrac{1}{(1 - \beta)^2}$

Cool, right?

::::::::::::::::::::::::::::::::::::: keypoints 

- Use `.Rmd` files for lessons even if you don't need to generate any code
- Run `sandpaper::check_lesson()` to identify any issues with your lesson
- Run `sandpaper::build_lesson()` to preview your lesson locally

::::::::::::::::::::::::::::::::::::::::::::::::


```r
sessioninfo::session_info()
```

```{.output}
─ Session info ───────────────────────────────────────────────────────────────────────────────────
 setting  value                       
 version  R version 4.1.1 (2021-08-10)
 os       macOS Catalina 10.15.7      
 system   x86_64, darwin17.0          
 ui       X11                         
 language (EN)                        
 collate  en_US.UTF-8                 
 ctype    en_US.UTF-8                 
 tz       UTC                         
 date     2021-08-25                  

─ Packages ───────────────────────────────────────────────────────────────────────────────────────
 package     * version    date       lib source                                      
 assertthat    0.2.1      2019-03-21 [1] CRAN (R 4.1.0)                              
 cli           3.0.1      2021-07-17 [1] CRAN (R 4.1.0)                              
 curl        * 4.3.2      2021-06-23 [1] CRAN (R 4.1.0)                              
 evaluate      0.14       2019-05-28 [1] CRAN (R 4.1.0)                              
 highr         0.9        2021-04-16 [1] CRAN (R 4.1.0)                              
 knitr         1.33       2021-04-24 [1] CRAN (R 4.1.0)                              
 magrittr      2.0.1      2020-11-17 [1] CRAN (R 4.1.0)                              
 sandpaper     0.0.0.9046 2021-08-20 [1] https://carpentries.r-universe.dev (R 4.1.1)
 sessioninfo   1.1.1      2018-11-05 [1] CRAN (R 4.1.0)                              
 stringi       1.7.4      2021-08-12 [1] https://carpentries.r-universe.dev (R 4.1.0)
 stringr       1.4.0      2019-02-10 [1] CRAN (R 4.1.0)                              
 withr         2.4.2      2021-04-18 [1] CRAN (R 4.1.0)                              
 xfun          0.25       2021-08-06 [1] CRAN (R 4.1.0)                              

[1] /Users/runner/work/_temp/Library
[2] /Library/Frameworks/R.framework/Versions/4.1/Resources/library
```


