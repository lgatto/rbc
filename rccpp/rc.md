R and C++
====

This material is based on the *High performance functions with Rcpp*
chapter of the /Advanced R/ book by Hadley Wickham.

# Getting started

## Requirement

> R is interpreted; C++ is a compiled language.

We will focus on short simple code snippets using `Rcpp`:


```r
install.packages("Rcpp")
```
We need a C compiler:
- Rtools on Windows
- Xcode on Mac
- package manager on Linux


```r
library("Rcpp")
```

## Data types

> R is dynamically typed; C++ is statically typed.

| R         | Scalar | Vector          | Matrix          |
|-----------|--------|-----------------|-----------------|
| numeric   | double | NumericVector   | NumericMatrix   |
| integer   | int    | IntegerVector   | IntegerMatrix   |
| character | string | CharacterVector | CharacterMatrix |
| logical   | bool   | LogicalVector   | LogicalMatrix   | 


| R        | C++      |
|----------|----------|
| list     | List     |
| function | Function |

## Defining functions

In C++, we need to
- we don't assign the function body
- define input and output types
- explicitly return a value
- use `;`
- make `for` loops explicit
- call a method using `.` - `x.size()` to get the size (length) of `x`


```r
sumR <- function(x) {
  total <- 0
  for (i in seq_along(x)) {
    total <- total + x[i]
  }
  total
}
```

```
double sumC(NumericVector x) {
  int n = x.size();
  double total = 0;
  for(int i = 0; i < n; ++i) {
    total += x[i];
  }
  return total;
}'
```

## Compile and use in `R`

### Inline


```r
cppFunction('double sumC(NumericVector x) {
  int n = x.size();
  double total = 0;
  for(int i = 0; i < n; ++i) {
    total += x[i];
  }
  return total;
}')
sumC
```

```
## function (x) 
## .Primitive(".Call")(<pointer: 0x2b4f5c001d60>, x)
```

```r
sumC(c(1, 2, 1:4, rnorm(3)))
```

```
## [1] 13.16911
```

### Sourcing C++ code

The `./src/ex_sumC.cpp` file contains:

- include statements
- the export directive
- the C++ code
- as comment, R code that will be evaluated


```
#include <Rcpp.h>
using namespace Rcpp;

// [[Rcpp::export]]
double sumC(NumericVector x) {
  int n = x.size();
  double total = 0;
  for(int i = 0; i < n; ++i) {
    total += x[i];
  }
  return total;
}

/*** R
# Comparing with R
(x <- c(1, 3, rnorm(10)))
sumC(x)
sum(x)
*/
```

To compile the code and create the R wrapper, we use:


```r
sourceCpp("./src/ex_sumC.cpp")
```

```
## 
## > (x <- c(1, 3, rnorm(10)))
##  [1]  1.0000000  3.0000000 -1.4772674  0.6258872 -1.9313957  0.5776386
##  [7]  2.6125733  1.6164735  0.9670635  0.9105139 -1.1335419 -0.5785604
## 
## > sumC(x)
## [1] 6.189385
## 
## > sum(x)
## [1] 6.189385
```

## An example with a matrix


```
#include <Rcpp.h>
using namespace Rcpp;

// [[Rcpp::export]]
NumericVector rowSumsC(NumericMatrix x) {
  int nrow = x.nrow(), ncol = x.ncol();
  NumericVector out(nrow);

  for (int i = 0; i < nrow; i++) {
    double total = 0;
    for (int j = 0; j < ncol; j++) {
      total += x(i, j);
    }
    out[i] = total;
  }
  return out;
}
```

Note:
- The use of `()` instead of `[]`
- `.nrow` and `.ncol` to get the number of rows/cols

## An example with `if`/`else`


```r
signR <- function(x) {
  if (x > 0) {
    1
  } else if (x == 0) {
    0
  } else {
    -1
  }
}
```

```
int signC(int x) {
  if (x > 0) {
    return 1;
  } else if (x == 0) {
    return 0;
  } else {
    return -1;
  }
}
```

# Exercises

Get familiar with the syntax and write/test the `sumC` and `rowSumsC`
functions above.

Try and implement the following R functions.


```r
fibR <- function(n) {
    if (n == 0) return(0)
    if (n == 1) return(1)
    return( fibR(n - 1) + fibR(n - 2))
}

pdistR <- function(x, ys)
    sqrt( (x - ys) ^ 2 )

sety <- function(x, y) {
    x[x > 0] <- y
    x[x < 0] <- -y
    x
}
lgl_biggerY <- function(x, y) x > y

biggerY <- function(x, y) x[x > y]

foo <- function(x, y) ifelse(x < y, x*x, -(y*y))
```

# Rcpp sugar

/sugar/ (for syntactic sugar ) is a set of C++ functions that (mostly)
work and look like their R couterparts. Allows for example compact
vectorised expression. Looks like R with the C++ efficiency (see the
Rcpp-sugar vignette/paper).

- Vectorised arithmetic and logical operators: +, >, !, ...
- Functions: seq_len, seq, sapply, rnorm, abs, sum, ..

### Arithmetic and logical operators

`+ *, -, /, pow, <, <=, >, >=, ==, !=, !'

```
NumericVector pdistC2(double x, NumericVector ys) {
  return sqrt(pow((x - ys), 2));
}
```

### Logical summary functions

`any()` and `all()` with `.is_true()`, `.is_false()`, `.is_na()` (to
convert to `bool`).

```
bool any_naC(NumericVector x) {
  return is_true(any(is_na(x)));
}
```
### Vector views

`head(), tail(), rep_each(), rep_len(), rev(), seq_along(), seq_len()`

### Other useful functions

- Math functions: `abs(), acos(), asin(), atan(), beta(), ceil(),
  ceiling(), choose(), cos(), cosh(), digamma(), exp(), expm1(),
  factorial(), floor(), gamma(), lbeta(), lchoose(), lfactorial(),
  lgamma(), log(), log10(), log1p(), pentagamma(), psigamma(),
  round(), signif(), sin(), sinh(), sqrt(), tan(), tanh(),
  tetragamma(), trigamma(), trunc()`.

- Scalar summaries: `mean(), min(), max(), sum(), sd(), and (for
  vectors) var()`.

- Vector summaries: `cumsum(), diff(), pmin(), and pmax()`.

- Finding values: `match(), self_match(), which_max(), which_min()`.

- Dealing with duplicates: `duplicated(), unique()`.

- `d/q/p/r` for all standard distributions.

## Missing values

## An package with `Rcpp` code

## Standard Template Library
