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

- See also [here](http://lgatto.github.io/2014-11-06-UZH/) for
  installation instructions.

### A note on `git` and OSX 10.8

Incompatibilities have been reported. To test if you are affected, do
the following in a terminal:

```sh
git --version ## should work
git init . ## may fail
```

Possible fixes:

- http://stackoverflow.com/questions/22920497/git-mountain-lion-dyld-lazy-symbol-binding-failed-symbol-not-found-str
- Try using the git-osx-installer 1.8.4.2 found here:
https://code.google.com/p/git-osx-installer/downloads/detail?name=git-1.8.4.2-intel-universal-snow-leopard.dmg&can=2&q=
- If it does not work or you get an error with git v1.8.4.2, the
second thing that helped was to install or update the command line
tools using the command `xcode-select --install`:
http://osxdaily.com/2014/02/12/install-command-line-tools-mac-os-x/
- https://openhatch.org/wiki/Open_Source_Comes_to_Campus/Curriculum/Laptop_setup/OSX_git

### More troubleshooting

https://github.com/swcarpentry/bc/wiki/Configuration-Problems-and-Solutions

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

| When          | What                                           |     |
|---------------|------------------------------------------------|-----|
| 8:30          | Setup and welcome                              | LG  |
| 9:00 - 10:30  | [Introduction, background](https://github.com/lgatto/rbc/raw/2014-11-06-Zurich/Roo/roo.pdf) | RS  |
|               | Break                                          |     |
| 11:00 - 12:30 | [OO programming](https://github.com/lgatto/rbc/raw/2014-11-06-Zurich/Roo/roo.pdf) | RS  |
|               | Lunch                                          |     |
| 14:00 - 15:30 | [Package development](https://github.com/lgatto/rbc/raw/2014-11-06-Zurich/RPackageDevelopment/rpd.pdf) | RS  |
|               | Break                                          |     |
| 16:00 - 16:30 | [Vectorisation](https://github.com/lgatto/rbc/raw/2014-11-06-Zurich/R-vectorisation/vectorisation.pdf) and [functional programming](https://github.com/lgatto/rbc/blob/2014-11-06-Zurich/R-functional-programming/functional-programming.pdf) | LG  |
| 16:30 - 16:45 | Intro to git/gitub (applications on day 2)     | LG  |
| 16:45 - 17:00 | Wrap up                                        | all |

### Day 2

| When          | What                                      |     |
|---------------|-------------------------------------------|-----|
| 9:00 - 9:15   | Refresher day 1 and intro day 2           | LG  |
| 9:15 - 10:00  | [debugging](https://github.com/lgatto/rbc/raw/2014-11-06-Zurich/R-debugging/debugging.pdf), [testing](https://github.com/lgatto/rbc/blob/2014-11-06-Zurich/R-debugging/testing.md) and [unit testing](https://github.com/lgatto/rbc/blob/2014-11-06-Zurich/R-debugging/unittesting.md)   | LG  |
| 10:00 - 10:30 | RR - [reproducible documents and vignettes](https://github.com/lgatto/rbc/blob/2014-11-06-Zurich/rr/simple.md) | LG  |
|               | Break                                     |     |
| 11:00 - 12:30 | RR - [Automation and `Makefiles`](https://github.com/lgatto/rbc/blob/2014-11-06-Zurich/rr/make.md) | LG  |
|               | Lunch                                     |     |
| 14:00 - 14:45 | Profiling and optimisation                | LG  |
| 14:45 - 15:30 | C/C++ and Rcpp                            | LG  |
|               | Break                                     |     |
| 16:00 - 16:40 | Parallel processing                       | LG  |
| 16:40 - 17:00 | Wrap up, feedback                         | all |


Some material from earlier (similar) courses is available at:
- Previous bootcamp: https://github.com/lgatto/rbc/tree/2014-01-07-CAM
- Various teaching material: https://github.com/lgatto/teachingmaterial

<!--

Comments:

- prepare concept maps

-->
