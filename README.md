Advanced R boot camp
=====

# Logistics

- Where: University of Zurich
- When: November 6th/7th 2014 (Thu/Fri)
- Registration: https://www.eventbrite.com/e/zurich-software-carpentry-advanced-r-bootcamp-registration-12334106645

- Instructors: Laurent Gatto and Robert Stojnic.

## Pre-requisites

- Active knowledge of `R`. We will assume that you are familiar with
  common data structures, general programming concepts and how to
  write functions.

- Familiarity with basic `shell`. 


## Setup

- A virtual machine, or 

- A laptop with a recent R (>= 3.1.1), including developer tools (for
  Windows, this means
  [Rtools](http://cran.r-project.org/bin/windows/Rtools/)). See
  [here](https://github.com/lgatto/TeachingMaterial/wiki) for
  installation details.

- To test your R installation, try the following

```r
## If you don't have devtools
install.packages("devtools")

library("devtools")
install_github("lgatto/sequences")
```

- If you do not have any favourite editor, have a go with
  [Rstudio](http://www.rstudio.com/products/rstudio/).

- Working `shell`, `make` and `git` installations. See the
  [setup section](http://sje30.github.io/2014-01-07-cam/) document for
  some hints. Windows has proved to be a bit temperamental. Don't
  hesitate to get in touch if you have issues with your installation.


## Programme

- R object-oriented programming: S3 and S4, S4 Reference Classes.
- R package development
- R documentation and roxygen.
- Functional programming, vectorisation
- Reproducible research and vignettes
- Automating your pipelines with `Makefile`
- Parallelisation: `parallel` and `BiocParallel`.
- Using C/C++ in R and the `Rcpp` package.
- Source code versioning using `git` and `github`.


Some material from earlier (similar) courses is available:
- Previous bootcamp: https://github.com/lgatto/rbc/
- Various teaching material: https://github.com/lgatto/teachingmaterial





