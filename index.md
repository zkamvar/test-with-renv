---
site: sandpaper::sandpaper_site
---

This is a test lesson for the package management of {sandpaper}. It is still 
experimental, but if you would like to try this out, you can use:

```r
install.packages("renv")
remotes::install_github("carpentries/sandpaper@package-management")

sandpaper::use_package_cache() # prompt for consent to use the package cache
```

This will build your old lessons the same way, but when a new lesson is created,
it will create a private library for your lesson and a record of what packages
are used in the lesson. You can find an example in [the introduction 
chapter](01-introduction.Rmd).

::: callout

## A note about your global ~/.Rprofile

There is currently a feature of {renv} that will include packages from your
global .Rprofile in the package cache for your lesson. While it will not include
these packages in the lockfile, if you have an .Rprofile file that uses other
packages, you might want to consider disabling it for now.

See <https://github.com/rstudio/renv/issues/821> for details.

:::


