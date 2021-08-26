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


:::::::: callout

## Non-standard packages!

We can now include non-standard packages in our {sandpaper} sites and have them
be reproducible! Case in point: [the {cowsay} 
package](https://cran.r-project.org/package=cowsay) is not one of the imports
for sandpaper, but I can use it to generate random cat facts for my lesson

### Demo


```r
library("curl")
library("cowsay")
say("catfact", "cat")
```

```{.output}

 -------------- 
A queen (female cat) can begin mating when she is between 5 and 9 months old. 
 --------------
    \
      \
        \
            |\___/|
          ==) ^Y^ (==
            \  ^  /
             )=*=(
            /     \
            |     |
           /| | | |\
           \| | |_|/\
      jgs  //_// ___/
               \_)
  
```

### Try it yourself!

To try this out, install the development version of sandpaper with `remotes`:


```r
install.packages("renv")
remotes::install_github("carpentries/sandpaper@package-management")
```

Then, clone this repository and run `sandpaper::build_lesson()` inside the 
repository from your R console. Should this work, the dependencies will 
automatically install to a library specific to the lesson and the lesson will
render, regardless if you have {cowsay} previously installed.

:::


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
 date     2021-08-26                  

─ Packages ───────────────────────────────────────────────────────────────────────────────────────
 ! package     * version    date       lib source                                      
 R assertthat    0.2.1      <NA>       [?] <NA>                                        
 R callr         3.7.0      <NA>       [?] <NA>                                        
 P cli           3.0.1      2021-07-17 [?] CRAN (R 4.1.0)                              
 P cowsay      * 0.8.0      2020-02-06 [?] CRAN (R 4.1.0)                              
 P crayon        1.4.1      2021-02-08 [?] CRAN (R 4.1.0)                              
 P curl        * 4.3.2      2021-06-23 [?] CRAN (R 4.1.0)                              
 P evaluate      0.14       2019-05-28 [?] CRAN (R 4.1.0)                              
 P fortunes      1.5-4      2016-12-29 [?] CRAN (R 4.1.0)                              
 P highr         0.9        2021-04-16 [?] CRAN (R 4.1.0)                              
 P jsonlite      1.7.2      2020-12-09 [?] CRAN (R 4.1.0)                              
 P knitr         1.33       2021-04-24 [?] CRAN (R 4.1.0)                              
 P magrittr      2.0.1      2020-11-17 [?] CRAN (R 4.1.0)                              
 R processx      3.5.2      <NA>       [?] <NA>                                        
 R ps            1.6.0      <NA>       [?] <NA>                                        
 R R6            2.5.1      <NA>       [?] <NA>                                        
 P renv          0.14.0     2021-07-21 [?] CRAN (R 4.1.0)                              
 P rmsfact       0.0.3      2016-08-04 [?] CRAN (R 4.1.0)                              
 R sandpaper     0.0.0.9048 <NA>       [?] <NA>                                        
 P sessioninfo   1.1.1      2018-11-05 [?] CRAN (R 4.1.0)                              
 P stringi       1.7.4      2021-08-12 [?] https://carpentries.r-universe.dev (R 4.1.0)
 P stringr       1.4.0      2019-02-10 [?] CRAN (R 4.1.0)                              
 P withr         2.4.2      2021-04-18 [?] CRAN (R 4.1.0)                              
 P xfun          0.25       2021-08-06 [?] CRAN (R 4.1.0)                              

[1] /Users/runner/work/test-with-renv/test-with-renv/renv/profiles/packages/renv/library/R-4.1/x86_64-apple-darwin17.0
[2] /private/var/folders/24/8k48jl6d249_n_qfxwsl6xvm0000gn/T/RtmpGL2xzd/renv-system-library

 P ── Loaded and on-disk path mismatch.
 R ── Package was removed from disk.
```


