---
site: sandpaper::sandpaper_site
---

This is a test lesson for the package management of {sandpaper}. It is still 
experimental, but if you would like to try this out, you can use the following
commands.

```r
install.packages(c("renv", "sandpaper"), repos = "https://zkamvar.r-universe.dev/")

sandpaper::use_package_cache() # prompt for consent to use the package cache
```

This will build your old lessons the same way, but when a new lesson is created,
it will create a private library for your lesson and a record of what packages
are used in the lesson. You can find an example in [the introduction 
chapter](01-introduction.Rmd).

::: callout

## A note about your global ~/.Rprofile

There is currently a feature of {renv} that will include packages from your
global .Rprofile in the package cache for your lesson. This has been fixed on
the development version of renv (> 0.14), which you will get by running the
`install.packages()` command above.

See <https://github.com/rstudio/renv/issues/821> for details.

:::


