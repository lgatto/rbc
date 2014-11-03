simple.md: simple.Rmd
		R --vanilla -e "library(knitr); knit('simple.Rmd')"

make.md: make.Rmd
		R --vanilla -e "library(knitr); knit('make.Rmd')"

all:
	make make.md
	make simple.md
