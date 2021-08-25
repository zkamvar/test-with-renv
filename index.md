---
site: sandpaper::sandpaper_site
---

This is a test lesson for the package management of {sandpaper}. It is still 
experimental, but if you would like to try this out, you can use:

```r
install.packages("renv")
remotes::install_github("carpentries/sandpaper@package-management")
```

This will build your old lessons the same way, but when a new lesson is created,
it will create a private library for your lesson and a record of what packages
are used in the lesson. You can find an example in [the introduction 
chapter](episodes/01-introduction.Rmd).


