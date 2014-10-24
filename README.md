Advanced R boot camp
=====

# Logistics

- Where: University of Zurich
- When: November 6th/7th 2014 (Thu/Fri)
- main page: http://lgatto.github.io/2014-11-06-UZH/
- Registration: https://www.eventbrite.com/e/zurich-software-carpentry-advanced-r-bootcamp-registration-12334106645

- Instructors: Laurent Gatto and Robert Stojnic (Cambridge).
- With help from Frank Pennekamp (Zurich), Peter Fields (Basel) and
  Jelena Aleksic (Cambridge).

- etherpad: https://etherpad.mozilla.org/2Idlzt0luX

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

The aim of the workshop is to provide a set of tools to enable a more
structured, efficient and systematic use of programming in
computational sciences. We will address the following points
throughout the course:

- R object-oriented programming: S3 and S4, S4 Reference Classes.
- R package development
- R documentation and roxygen.
- Functional programming, vectorisation
- Reproducible research and vignettes
- Debugging and unit testing. 
- Automating your pipelines with `Makefile`
- Parallelisation: `parallel` and `BiocParallel`.
- Code profiling and strategies for optimisation.
- Using C/C++ in R and the `Rcpp` package.
- Source code versioning using `git` and `github`.

Some of these topics will be addressed through the development of an R
package that applied object oriented programming. The main thread that
we will use is the definition and manipulations of generic and
biological sequences that will, eventually, materialise into a
[fully fledged package](http://cran.r-project.org/web/packages/sequences/). All
the content will be made available here.

### Day 1

| When          | What                       |
|---------------|----------------------------|
| 8:30          | Setup                      |
| 9:00 - 10:30  | Introduction               |
|               | Break                      |
| 11:00 - 12:30 | OO programming             |
|               | Lunch                      |
| 14:00 - 15:30 | Package development        |
|               | Break                      |
| 16:00 - 17:15 | Unit testing and debugging |
| 17:15 - 17:30 | Wrap up                    |

### Day 2

| When          | What                                      |
|---------------|-------------------------------------------|
| 9:00 - 9:45   | RR - reproducible documents and vignettes |
| 9:45 - 10:30  | RR - automation and Makefiles             |
|               | Break                                     |
| 11:00 - 11:45 | Vectorisation and functional programming  |
| 11:45 - 12:30 | Profiling and optimisation                |
|               | Lunch                                     |
| 14:00 - 14:45 | C/C++ and Rcpp                            |
| 14:45 - 15:30 | Parallel processing                       |
|               | Break                                     |
| 16:00 - 17:15 | git and github                            |
| 17:15 - 17:30 | Wrap up                                   |


Some material from earlier (similar) courses is available at:
- Previous bootcamp: https://github.com/lgatto/rbc/tree/2014-01-07-CAM
- Various teaching material: https://github.com/lgatto/teachingmaterial

<!--

Comments:

Mark: need a whiteboard

Robert:
- do we want sticky notes
- prepare concept maps

-->
